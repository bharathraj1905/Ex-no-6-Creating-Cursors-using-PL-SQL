# Ex. No: 6 Creating Cursors using PL/SQL

### Aim: 
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```
DEVELOPED BY : BARATHRAJ.B
REG NO:212222230019
```
### Create employee table:
```
CREATE TABLE employee (
  empid NUMBER,
  empname VARCHAR(20),
  dept VARCHAR(20),
  salary NUMBER
);
select * from employee;
INSERT INTO employee VALUES (1, 'Aarthi', 'Sales', 60000);
INSERT INTO employee VALUES (2, 'Pooja', 'Marketing', 500000);
````
### PLSQL Cursor code:
```
DECLARE
   CURSOR employee_cursor IS
   SELECT empid,empname,dept,salary
   FROM employee;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employee_cursor;

  LOOP
    FETCH employee_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employee_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employee_cursor;
END;
/
```
### Output:
![cursor op](https://github.com/JananiSoundararajan/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119477549/e14b4517-9d41-411a-9dc3-19e81abb71bf)

### Result:
         A cursor is created using PL/SQL.
