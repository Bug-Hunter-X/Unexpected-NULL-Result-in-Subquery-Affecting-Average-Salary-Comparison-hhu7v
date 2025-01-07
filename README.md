# SQL Subquery NULL Handling Bug

This repository demonstrates a common SQL bug related to handling NULL values in subqueries used for comparison. The main issue lies in how database systems handle NULL values when calculating averages. If the subquery doesn't return any rows (an empty set), the average calculation returns NULL, which can cause unexpected query behavior or errors when used in comparison operations.

The `bug.sql` file contains the erroneous query. The `bugSolution.sql` file provides a corrected version that uses `IS NOT NULL` checks to handle this edge case gracefully.

## How to Reproduce

1. Create a SQL database table named `employees` with columns `employee_id`, `department_id`, and `salary`. 
2. Insert some sample data, ensuring you have a department with no employees. 
3. Run the query in `bug.sql` to observe the incorrect result.
4. Run the query in `bugSolution.sql` to see the corrected behavior.