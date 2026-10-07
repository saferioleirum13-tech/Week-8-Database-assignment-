# Query Optimization Report

## Query 1

### QUERY
Find all enrollments for a specific student.

```sql
SELECT *
FROM Enrollment
WHERE student_id = 1;