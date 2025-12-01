# Bajaj_Finserv_Assignment_22BCE20263
Assignment of the JAVA Intern SQL
# Bajaj Finserv Health - Qualifier 1 Submission

Name: Morimisetty Divyasri  
Reg No: 22BCE20263  

## Submission Method
SQL problem was solved and submitted using Postman as per instructions.

## API Steps Followed

### Step 1: Generate Webhook
POST Request:
https://bfhldevapigw.healthrx.co.in/hiring/generateWebhook/JAVA

### Step 2: Submit SQL Solution
POST Request:
https://bfhldevapigw.healthrx.co.in/hiring/testWebhook/JAVA

Header:
Authorization: JWT Token

Body:
```json
{
  "finalQuery": "SELECT d.department_name AS DEPARTMENT_NAME,
  ROUND(AVG(TIMESTAMPDIFF(YEAR, e.dob, CURDATE())), 2) AS AVERAGE_AGE,
  GROUP_CONCAT(CONCAT(e.first_name, ' ', e.last_name)
  ORDER BY e.first_name SEPARATOR ', ') AS EMPLOYEE_LIST
  FROM department d
  JOIN employee e ON d.department_id = e.department
  JOIN payments p ON e.emp_id = p.emp_id
  WHERE p.amount > 70000
  GROUP BY d.department_id, d.department_name
  ORDER BY d.department_id DESC;"
}
Submission Screenshot:
https://github.com/DivyasriMorimisetty/Bajaj_Finserv_Assignment_22BCE20263/blob/754987b463a74d1a182c147781d746c17ca34556/Screenshot%202025-12-01%20161050.png

Success proof:
https://github.com/DivyasriMorimisetty/Bajaj_Finserv_Assignment_22BCE20263/blob/839d469e513c532c8b753f853d97b700a19baba4/Screenshot%202025-12-01%20161358.png
