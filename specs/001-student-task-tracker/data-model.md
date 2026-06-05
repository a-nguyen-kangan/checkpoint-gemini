# Data Model: Student Task Tracker

This model defines the PostgreSQL schema to be implemented in Supabase.

## Entities

### User
Represents a user of the system (Admin, Student, Teacher).

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | UUID | Primary Key (linked to Supabase Auth `auth.users`) |
| `name` | TEXT | User's full name |
| `email` | TEXT | User's email address |
| `role` | TEXT | 'admin', 'student', 'teacher' |

### Course
An academic course.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | UUID | Primary Key |
| `code` | TEXT | Course code (e.g., CS101) |
| `name` | TEXT | Course name |
| `course_offering` | TEXT | Academic term/offering (e.g., Fall 2026) |

### Subject
A subject belonging to a course.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | UUID | Primary Key |
| `course_id` | UUID | Foreign Key -> Course.id |
| `name` | TEXT | Subject name |

### Task
An assignment or task for a subject.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | UUID | Primary Key |
| `subject_id` | UUID | Foreign Key -> Subject.id |
| `teacher_id` | UUID | Foreign Key -> User.id (Teacher) |
| `title` | TEXT | Task title |
| `description_link` | TEXT | URL to task description |
| `due_date` | TIMESTAMP | Due date |
| `created_at` | TIMESTAMP | Creation timestamp |

### StudentSubmission
Link between students, tasks, and submission details.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | UUID | Primary Key |
| `task_id` | UUID | Foreign Key -> Task.id |
| `student_id` | UUID | Foreign Key -> User.id (Student) |
| `submission_link`| TEXT | URL to submission (e.g., GitHub repo) |
| `is_completed` | BOOLEAN | Completion status (set by Teacher) |

## Relationships

- **Course** 1:N **Subject**
- **Subject** 1:N **Task**
- **User (Teacher)** 1:N **Task**
- **Task** 1:N **StudentSubmission**
- **User (Student)** 1:N **StudentSubmission**

## Validation Rules

- `Task.due_date`: Must be in the future (or present) when created.
- `StudentSubmission.submission_link`: Must be a valid URL.
- RLS (Row Level Security):
  - Teachers can only view/create tasks in their assigned subjects.
  - Students can only view tasks for their enrolled courses/subjects.
  - Students can only submit their own work.
  - Teachers can only grade submissions for their assigned subjects.
