# Implementation Tasks: Student Task Tracker

This document outlines the step-by-step implementation plan for the Student Task Tracker application.

## Phase 1: Environment & Auth Setup
- [ ] [T-001] Initialize Next.js project with TypeScript and Mantine.
- [ ] [T-002] Setup Supabase client (`lib/supabase.ts`).
- [ ] [T-003] Configure Supabase Authentication (Email/Password).
- [ ] [T-004] Implement basic login page and protective middleware.

## Phase 2: Database Schema & RLS Policies
- [ ] [T-005] Execute SQL to create tables (`User`, `Course`, `Subject`, `Task`, `StudentSubmission`).
- [ ] [T-006] Define and apply RLS policies for each role:
    - [ ] [T-006.1] Admin (full access)
    - [ ] [T-006.2] Teacher (assigned subject access)
    - [ ] [T-006.3] Student (enrolled course/subject access)

## Phase 3: Core UI Infrastructure
- [ ] [T-007] Setup Mantine `ThemeProvider` and global layout.
- [ ] [T-008] Create basic navigation components (header, sidebar).

## Phase 4: Admin Functionality (P1)
- [ ] [T-009] Implement `createCourse`, `updateCourse`, `deleteCourse` server actions.
- [ ] [T-010] Implement `createSubject`, `updateSubject`, `deleteSubject` server actions.
- [ ] [T-011] Implement `createUser` server action.
- [ ] [T-012] Build admin dashboard UI for managing courses, subjects, and users.

## Phase 5: Teacher Functionality (P1)
- [ ] [T-013] Implement `createTask` server action (with due date validation).
- [ ] [T-014] Implement `enrollStudent` server action.
- [ ] [T-015] Build teacher task creation form.

## Phase 6: Student Functionality (P2)
- [ ] [T-016] Implement `getTasksBySubject` and `getStudentProgress` server actions.
- [ ] [T-017] Build student dashboard UI (grouped task view, progress display).
- [ ] [T-018] Build student view task page.
- [ ] [T-019] Implement `submitTask` server action.
- [ ] [T-020] Build submission component.

## Phase 7: Teacher Dashboard & Grading (P2)
- [ ] [T-021] Implement `getTeacherDashboardData` server action.
- [ ] [T-022] Implement `markTaskComplete` server action.
- [ ] [T-023] Build teacher dashboard UI (completion tracking, grading interface).

## Phase 8: Polish & Testing
- [ ] [T-024] Run E2E tests for all user stories (1-6).
- [ ] [T-025] Perform final UI/UX polish.
