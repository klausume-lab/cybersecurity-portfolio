# SQL — Security Filtering Study

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Written query explanations present; source authorship and execution evidence unverified.

## Available material

The Drive document explains six filters using the training tables log_in_attempts and employees: failed logins after 18:00, logins on two dates, logins outside Mexico, Marketing employees in East offices, Finance or Sales employees, and employees outside IT.

The source references screenshots and uses wording resembling a course exemplar. The public portfolio therefore treats this as a study artifact rather than proof of independently authored queries or executed lab results. The sample SQL below is reconstructed from the explanations during portfolio preparation. It has not been run against the course database.

```sql
SELECT * FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;

SELECT * FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';

SELECT * FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';

SELECT * FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';

SELECT * FROM employees
WHERE department = 'Finance' OR department = 'Sales';

SELECT * FROM employees
WHERE NOT department = 'Information Technology';
```

## Interpretation

AND requires both conditions, OR allows either, and NOT excludes matching rows. LIKE uses % to match a variable suffix. These examples follow the supplied training data conventions; NULL values, database collation, and field types can affect real results. Filtering records identifies candidates for review; it does not itself update computers or establish malicious activity.

## Next step

Revisit the lab, save original queries and output, and record why each returned result supports the task before promoting this to a validated hands-on project.

## Evidence and attribution

Adapted from the Drive document “Apply filters to SQL queries”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
