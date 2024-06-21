--Data Analysis
--List the employee number, last name, first name, sex and salary of each employee
SELECT employees.emp_no AS "Employee No.",
    employees.last_name AS "Last Name",
    employees.first_name AS "First Name",
    employees.sex AS "Sex",
    salaries.salary AS "Salary"
FROM employees
JOIN salaries
    ON employees.emp_no = salaries.emp_no;


--List the first name, last name, and hire date for the employees who were hired in 1986
SELECT first_name, last_name, hire_date
FROM employees
WHERE hire_date between '1986-01-01' and '1986-12-31';

--List the manager of each dept along with their dept_no, department name, emp_no, last name and first name
SELECT dm.dept_no, d.dept_name, e.emp_no, e.last_name, e.first_name
FROM dept_manager AS dm
JOIN employees AS e
ON (dm.emp_no = e.emp_no)
JOIN departments AS d
ON (dm.dept_no = d.dept_no)
LIMIT 100;

--List the dept_no for each employee along with that employees emp_no, last name, first name and department name
SELECT dept_manager.dept_no AS "Department No.",
    departments.dept_name AS "Department Name",
    dept_manager.emp_no AS "Employee No.",
    employees.last_name AS "Last Name",
    employees.first_name AS "First Name"
FROM dept_manager
JOIN departments
    ON dept_manager.dept_no = departments.dept_no
JOIN employees
    ON dept_manager.emp_no = employees.emp_no;

--List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B
SELECT  employees.first_name AS "First Name",
    employees.last_name AS "Last Name",
    employees.sex AS "Sex"
FROM employees
WHERE employees.first_name = 'Hercules'
AND employees.last_name LIKE 'B%';

--List each employee in the Sales department, including their emp_no, last name and first name
SELECT employees.emp_no AS "Employee No.",
    employees.last_name AS "Last Name",
    employees.first_name AS "First Name"
FROM employees
WHERE emp_no IN
    (SELECT emp_no
    FROM dept_emp
    WHERE dept_no IN
    (SELECT dept_no
    FROM departments
    WHERE dept_no = 'd007'));

--List each employee in the Sales and Development departments, including their emp_no, last name, first name and department name
SELECT SELECT employees.emp_no AS "Employee No.",
    employees.last_name AS "Last Name",
    employees.first_name AS "First Name",
	departments.dept_name AS "Department Name"
FROM dept_emp AS de
JOIN employees AS e ON (de.emp_no = e.emp_no)
JOIN departments AS d ON (de.dept_no = d.dept_no)
WHERE d.dept_name = 'Sales' OR d.dept_name = 'Development';

--List the frequency counts, in descending order of all the employee last names (that is how many employees share each last name)
SELECT last_name, COUNT(last_name) AS "Total with same last name"
FROM employees
GROUP BY last_name
ORDER BY "Total with same last name" DESC;