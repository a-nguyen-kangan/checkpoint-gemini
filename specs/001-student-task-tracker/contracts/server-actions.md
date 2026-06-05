# Interface Contracts (Server Actions)

This document defines the interface contracts for the Server Actions used to bridge the Next.js frontend and the Supabase backend.

## Admin Actions

### `createCourse(data: CourseInput): Promise<Result>`
- **Description**: Creates a new academic course.

### `updateCourse(id: UUID, data: CourseInput): Promise<Result>`
- **Description**: Updates an existing course.

### `deleteCourse(id: UUID): Promise<Result>`
- **Description**: Deletes a course.

### `createSubject(data: SubjectInput): Promise<Result>`
- **Description**: Creates a new subject within a course.

### `updateSubject(id: UUID, data: SubjectInput): Promise<Result>`
- **Description**: Updates an existing subject.

### `deleteSubject(id: UUID): Promise<Result>`
- **Description**: Deletes a subject.

### `createUser(data: UserInput): Promise<Result>`
- **Description**: Creates a new user (student/teacher).

### `updateUser(id: UUID, data: UserInput): Promise<Result>`
- **Description**: Updates a user profile.

### `enrollStudent(student_id: UUID, subject_id: UUID): Promise<Result>`
- **Description**: Enrolls a student in a subject.

## Teacher Actions

### `createTask(data: TaskInput): Promise<Result>`
- **Description**: Creates a new task for a subject.

### `updateTask(id: UUID, data: TaskInput): Promise<Result>`
- **Description**: Updates a task.

### `deleteTask(id: UUID): Promise<Result>`
- **Description**: Deletes a task.

### `markTaskComplete(submission_id: UUID): Promise<Result>`
- **Description**: Marks a student's submission as satisfactory/completed.

### `enrollStudent(student_id: UUID, subject_id: UUID): Promise<Result>`
- **Description**: Enrolls a student in a subject.

## Student Actions

### `submitTask(data: SubmissionInput): Promise<Result>`
- **Description**: Submits a student's work for a task.

## Data Fetching (Server Components)

### `getTasksBySubject(subject_id: UUID): Promise<Task[]>`
- Fetches all tasks for a given subject.

### `getStudentProgress(subject_id: UUID): Promise<ProgressData>`
- Fetches completion percentage for a subject for the authenticated student.

### `getTeacherDashboardData(teacher_id: UUID): Promise<TeacherDashboardData>`
- Fetches completion rates and task counts for all subjects taught by the teacher.
