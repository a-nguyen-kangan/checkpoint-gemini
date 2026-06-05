# Quickstart Guide: Student Task Tracker

This guide covers the initial setup and development steps for the Student Task Tracker application.

## Prerequisites

- Node.js (v20+)
- Supabase account and project
- Git

## 1. Project Setup

1. **Clone the repository**:
   ```bash
   git clone <repo-url>
   cd student-task-tracker
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables**:
   Create a `.env.local` file in the root directory:
   ```env
   NEXT_PUBLIC_SUPABASE_URL=<your-supabase-url>
   NEXT_PUBLIC_SUPABASE_ANON_KEY=<your-supabase-anon-key>
   SUPABASE_SERVICE_ROLE_KEY=<your-supabase-service-role-key>
   ```

## 2. Supabase Initialization

1. **Database Schema**:
   Run the SQL scripts provided in `specs/001-student-task-tracker/data-model.md` in the Supabase SQL editor to create the tables and set up RLS policies.

## 3. Development

1. **Run the development server**:
   ```bash
   npm run dev
   ```
2. **Access the app**:
   Open [http://localhost:3000](http://localhost:3000) in your browser.

## 4. Next Steps

- Explore `src/components` for Mantine-based UI elements.
- Review `specs/001-student-task-tracker/contracts/server-actions.md` for API contract definitions.
- Implement Server Actions in `src/app/actions.ts` (or equivalent).
