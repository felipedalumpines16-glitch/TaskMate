# TaskMate UI/UX Design Guide

## Product Overview
TaskMate — Plan. Focus. Achieve. — is a calm, student-friendly mobile task and deadline organizer built in Flutter. It uses Firebase Authentication, Cloud Firestore, responsive layouts, and local deadline notifications.

## Direction and Palette
Use rich indigo/purple as the primary color, soft lavender accents, white and very light lavender backgrounds, deep navy headings, and muted slate secondary text. Coral/red indicates overdue or urgent work, amber indicates due soon, and green indicates completed work. Use rounded cards, 12–20 px radii, subtle elevation, 8/12/16/20/24 px spacing, clear hierarchy, and accessible 48 px controls.

## Navigation
A bottom navigation bar exposes Home, Tasks, Calendar, and Profile. Home and Tasks show a prominent floating Add Task button.

## Screens
Splash/welcome should route by authentication state. Login/register support Firebase Email/Password, validation, password reset, loading and inline errors. Home shows the user's greeting, progress, counts, and upcoming deadlines. Add/Edit Task includes title, description, subject, due date/time, priority, and reminder settings. Tasks supports All/Pending/Completed filters, search, due-date sorting, completion toggles, edit/delete, and overdue labels. Calendar marks dates with tasks and displays the selected day's tasks. Details support edit, complete/reopen, reminder, and delete. Profile supports display-name editing, notification settings, About, sign-out confirmation, and signed-out handling.

## Firestore Model
Profiles are stored at `users/{uid}` with displayName, email, and createdAt. Tasks are stored at `users/{uid}/tasks/{taskId}` with title, description, subject, dueAt, priority, isCompleted, reminderEnabled, reminderAt, createdAt, and updatedAt. Every operation is scoped to the authenticated UID.

## States and Accessibility
Every screen must handle loading, empty, success, and error states. Destructive actions require confirmation. Use readable contrast and touch targets of at least 44–48 px. Keep layouts scrollable and compatible with small Android and iOS screens.
