# Feature Specification: Student Task Tracker

**Feature Branch**: `[001-student-task-tracker]`  
**Created**: 2026-06-05  
**Status**: Draft  
**Input**: User description: "creating a web app to track students' tasks for subjects that part of their course"

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: System MUST allow to manage courses, subjects and users (students and teachers).
- **FR-002**: System MUST allow teachers to create, edit and delete tasks with a title, due date, associated subject and a link to description.
- **FR-003**: System MUST allow admin and teachers to add students to courses and subjects
- **FR-004**: System MUST allow teachers to mark tasks as completed.
- **FR-005**: System MUST validate due dates during task creation and display a warning if a past due date is selected, but still allow task creation.
- **FR-006**: System MUST allow students to view their tasks organized by subject.
- **FR-007**: System MUST allow students to view their progress in a subject according to the amount of tasks completed vs total tasks.
- **FR-008:** System MUST allow teachers to view a dashboard of courses and subjects with the number of tasks and completion rates for each subject.

### Key Entities

- **Course**: Represents an academic course, has a code, name and can have multiple subjects.
- **Subject**: Represents an academic course, has a name.
- **Task**: Represents an assignment or task, has a title, link to task (from external source), current student submission (can be null, is a link to a GitHub repo), due date, completion status, and is associated with a Subject.
- **User**: Represents a user of the system, can be an admin, student or a teacher, has a name and email.

### Measurable Outcomes

- **SC-001**: Users can view a task in under 30 seconds.
- **SC-002**: Users can view their task list with less than 1 second loading time.
- **SC-003**: 90% of tasks created are successfully marked as complete within the academic term.

## Assumptions

- Students have a standard browser to access the web app.
- Task tracking is personal (no collaboration/sharing features in v1).

***

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Manage Courses and Users (Priority: P1)

As an Admin, I want to manage courses, subjects, and users, so that the system is properly configured for the institution.

**Independent Test**: Admin can successfully add a course, assign subjects to it, and create user accounts (student/teacher).

**Acceptance Scenarios**:

1. **Given** an admin is on the management dashboard, **When** they create a new course and add subjects to it, **Then** the course and subjects should be available in the system.
2. **Given** an admin is on the user management page, **When** they create a new student or teacher account, **Then** that user should be able to log in.

---

### User Story 2 - Assign Tasks to Subjects (Priority: P1)

As a Teacher, I want to create tasks for my subjects, so that students know what assignments are required.

**Independent Test**: Teacher can create a task linked to a subject they are assigned to, visible to all students in that subject.

**Acceptance Scenarios**:

1. **Given** a teacher is on their dashboard, **When** they create a task with a title, due date, description link, and select one of their subjects, **Then** that task is created and linked to the subject.
2. **Given** a teacher is creating a task, **When** they select a past due date, **Then** the system should display a warning message but allow the task to be created.

---

### User Story 3 - View Tasks by Subject (Priority: P2)

As a Student, I want to view my tasks organized by subject, so that I can focus on specific assignments.

**Independent Test**: Students can view tasks grouped by or filtered by subject.

**Acceptance Scenarios**:

1. **Given** a student has tasks for multiple subjects, **When** they filter by a specific subject, **Then** only tasks for that subject should be displayed.
2. **Given** a student has tasks with different completion statuses, **When** they filter by 'pending', **Then** only tasks that are not marked as completed should be displayed.

---

### User Story 4 - Track Progress (Priority: P2)

As a Student, I want to view my progress within a subject, so that I understand how much work I have completed.

**Independent Test**: Students can view a progress metric (e.g., percentage or ratio) for each subject they are enrolled in.

**Acceptance Scenarios**:

1. **Given** a student is viewing a subject dashboard, **When** they view the progress section, **Then** they see the ratio of completed tasks to total assigned tasks.

---

### User Story 5 - Dashboard View (Priority: P2)

As a Teacher, I want to view a dashboard for my courses, so that I can monitor student completion rates.

**Independent Test**: Teacher can see completion rates for tasks across their assigned subjects.

**Acceptance Scenarios**:

1. **Given** a teacher is on their dashboard, **When** they view a subject, **Then** they see the overall completion rate for that subject based on student submissions.

---

### User Story 6 - Mark Completion (Priority: P2)

As a Teacher, I want to be able to view a student's submission and mark it as completed if satisfactory.

**Independent Test**: Teacher can access a student's submission and toggle its completion status to 'completed' based on review.

**Acceptance Scenarios**:

1. **Given** a teacher is reviewing a student's submission, **When** they deem it satisfactory and click 'mark as complete', **Then** the task completion status for that student is updated to 'completed'.

## Success Criteria *(mandatory)*
