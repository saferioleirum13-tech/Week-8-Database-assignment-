# NoSQL Integration: Redis

## Purpose

Redis was integrated into the Community Education Management System to improve performance by caching frequently accessed information.

## Why Redis Was Chosen

Redis is an in-memory key-value store that provides significantly faster data access compared to disk-based relational databases.

In this project, Redis is used for:

- Student dashboard statistics
- Attendance summaries
- Frequently accessed course information
- Session management

## Why Not PostgreSQL Alone?

PostgreSQL is optimized for structured, transactional data and long-term storage.

However, repeatedly querying the database for frequently accessed information can increase response times.

Redis reduces database load by serving cached results directly from memory.

## Example

Instead of running:

SELECT COUNT(*) FROM Student;

every time*a dashboard loads, Redis can store*

student_count = 5000

and return*the value instantly.

## Benefits
*- Faster response time
- Reduced*PostgreSQL workload
- Improved sca*ability
- Better*user experience
## Sample Redis Data

Key: student_count

Value: 5000

Key: active_courses

Value: 120

Key: todays_attendance

Value: 4500
PostgreSQL stores all permanent educational records including students, instructors, courses, assessments, and attendance.

Redis serves as a caching layer for frequently requested statistics and reports.

Application Requests
        |
        v
      Redis
        |
        v
   PostgreSQL