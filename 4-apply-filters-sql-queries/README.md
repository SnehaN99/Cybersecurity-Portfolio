# Apply Filters to SQL Queries

## Project Description
As a security professional, I was tasked with investigating security issues and 
updating employee machines across the organization. I used SQL queries with 
filters to retrieve specific data from the `login_attempts` and `employees` 
tables to support these security tasks.

---

## Tasks Performed

### 1. Retrieve After-Hours Failed Login Attempts
Investigated failed logins occurring after business hours (after 18:00).

```sql
SELECT *
FROM login_attempts
WHERE login_time > '18:00' AND success = 0;
```
**Result:** 19 failed login attempts were found after 6 PM.  
**Operators used:** `AND` — to match both conditions (after hours + failed).

---

### 2. Retrieve Login Attempts on Specific Dates
Investigated a suspicious event on 2022-05-09 and the day prior.

```sql
SELECT *
FROM login_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```
**Result:** 75 login attempts across both days — flagged as suspicious.  
**Operators used:** `OR` — to retrieve records matching either date.

---

### 3. Retrieve Login Attempts Outside of Mexico
Identified suspicious activity originating from countries other than Mexico.

```sql
SELECT *
FROM login_attempts
WHERE NOT country LIKE 'MEX%';
```
**Result:** 144 login attempts made outside of Mexico.  
**Operators used:** `NOT`, `LIKE` — to exclude all records matching the 
'MEX%' pattern.

---

### 4. Retrieve Employees in Marketing (East Building)
Targeted security updates for Marketing department employees in East offices.

```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```
**Result:** 7 employees in Marketing located in East building offices.  
**Operators used:** `AND`, `LIKE` — to match both department and office 
location pattern.

---

### 5. Retrieve Employees in Finance or Sales
Performed security updates for both Finance and Sales departments.

```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
**Result:** Retrieved all employees from Finance and Sales departments.  
**Operators used:** `OR` — to include records from either department.

---

### 6. Retrieve All Employees Not in IT
Updated machines for all departments except IT, which was already updated.

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
**Result:** Retrieved all employees outside of the IT department.  
**Operators used:** `NOT` — to exclude IT department records.

---

## Summary
Used SQL filters with `AND`, `OR`, `NOT`, and `LIKE` operators to query the 
`login_attempts` and `employees` tables. These queries supported security 
investigations and helped target specific machines for updates based on 
department, location, and login behavior.

---

**Tools used:** SQL, MariaDB  
**Skills demonstrated:** SQL filtering, logical operators, pattern matching 
with LIKE, security data analysis
