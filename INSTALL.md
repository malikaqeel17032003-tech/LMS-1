# EduNexus — Multi-Role School Management + LMS

## Installation Guide

### Quick Setup

```bash
# 1. Create fresh Laravel project
composer create-project laravel/laravel edunexus

# 2. Copy all files from the zip into the Laravel project root

# 3. Configure environment
cp .env.example .env
php artisan key:generate

# 4. Set database credentials in .env
DB_DATABASE=edunexus_db
DB_USERNAME=root
DB_PASSWORD=your_password

# 5. Create the database, then run migrations
php artisan migrate

# 6. Seed all demo data
php artisan db:seed

# 7. Link storage
php artisan storage:link

# 8. Start server
php artisan serve
```

Visit http://localhost:8000

---

## 4 Role Portals

| Role        | Email                           | Password | Portal URL         |
| ----------- | ------------------------------- | -------- | ------------------ |
| **Admin**   | admin@edunexus.com              | password | /admin/dashboard   |
| **Teacher** | mali@edunexus.com               | password | /teacher/dashboard |
| **Student** | aisha.khan@student.edunexus.com | password | /student/dashboard |
| **Parent**  | parent@edunexus.com             | password | /parent/dashboard  |

All 5 teacher accounts use password: `password`  
All 10 student accounts use format: `firstname.lastname@student.edunexus.com` / `password`

---

## Role Permissions

### Admin

- Full access to all modules (Students, Teachers, Classes, Subjects, Timetable, Attendance, Exams, Fees, Payroll, Parents, Library, Transport, Hostel, Inventory, Reports, Settings)
- View and manage all LMS courses

### Teacher

- Access to own dashboard with course overview and grading queue
- Create and manage LMS courses, lessons, assignments, quizzes
- Mark attendance, enter exam results
- Post course announcements

### Student

- Personal dashboard (enrolled courses, pending assignments, grades, attendance %)
- Browse and enroll in published courses
- View lessons (with progress tracking)
- Submit assignments
- Take timed quizzes with auto-grading

### Parent

- View linked children's profiles
- Monitor attendance, exam grades, fee status
- Read-only access to child data

---

## LMS Features

- **Courses** — Create with subject/class assignment, auto-enroll class students
- **Lessons** — Text, video (YouTube embed), file types; progress tracking per student
- **Assignments** — Rich instructions, due dates, student submission, teacher grading + feedback
- **Quizzes** — MCQ & True/False, timed countdown, auto-grading, attempt limits
- **Announcements** — Course-level announcements, pin important notices
- **Progress tracking** — Per-lesson completion, overall course progress %

---

## Troubleshooting

```bash
# Clear all caches
php artisan optimize:clear

# Re-run migrations fresh
php artisan migrate:fresh --seed

# Fix storage permissions
chmod -R 775 storage bootstrap/cache
```
