# Exp-2 SQL query to fetch the no_of_works for each department in descending order from the sample data.
## Aim:
To write a sql query to fetch the no_of_works for each department in descending order From the sample data.
## Algorithm:
### Step 1:
Create database ORG.
### Step 2:
Create table Worker,Bonus,Title.
### Step 3: 
Insert Value to the tables.
### Step 4:
Select no_of_works for each department in descending order.
### Step 5:
Display the result.

## Program:
```sql
CREATE DATABASE ORG;
SHOW DATABASES;
USE ORG;
CREATE TABLE Worker (
WORKER_ID INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
FIRST_NAME CHAR(25),
LAST_NAME CHAR(25),
SALARY INT(15),
JOINING_DATE DATETIME,
DEPARTMENT CHAR(25)
);
INSERT INTO Worker
(WORKER_ID, FIRST_NAME, LAST_NAME, SALARY, JOINING_DATE,
DEPARTMENT) VALUES
(001, 'Monika', 'Arora', 100000, '14-02-20
09.00.00', 'HR'),
(002, 'Niharika', 'Verma', 80000, '14-06-11
09.00.00', 'Admin'),
(003, 'Vishal', 'Singhal', 300000, '14-02-20
09.00.00', 'HR'),
(004, 'Amitabh', 'Singh', 500000, '14-02-20
09.00.00', 'Admin'),
(005, 'Vivek', 'Bhati', 500000, '14-06-11 09.00.00',
'Admin'),
(006, 'Vipul', 'Diwan', 200000, '14-06-11 09.00.00',
'Account'),
(007, 'Satish', 'Kumar', 75000, '14-01-20 09.00.00',
'Account'),
(008, 'Geetika', 'Chauhan', 90000, '14-04-11
09.00.00', 'Admin');
CREATE TABLE Bonus (
WORKER_REF_ID INT,
BONUS_AMOUNT INT(10),
BONUS_DATE DATETIME,
FOREIGN KEY (WORKER_REF_ID)
REFERENCES Worker(WORKER_ID)
ON DELETE CASCADE
);
INSERT INTO Bonus
(WORKER_REF_ID, BONUS_AMOUNT, BONUS_DATE) VALUES
(001, 5000, '16-02-20'),
(002, 3000, '16-06-11'),
(003, 4000, '16-02-20'),
(001, 4500, '16-02-20'),
(002, 3500, '16-06-11');
CREATE TABLE Title (
WORKER_REF_ID INT,
WORKER_TITLE CHAR(25),
AFFECTED_FROM DATETIME,
FOREIGN KEY (WORKER_REF_ID)
REFERENCES Worker(WORKER_ID)
ON DELETE CASCADE
);
INSERT INTO Title
(WORKER_REF_ID, WORKER_TITLE, AFFECTED_FROM) VALUES
(001, 'Manager', '2016-02-20 00:00:00'),
(002, 'Executive', '2016-06-11 00:00:00'),
(008, 'Executive', '2016-06-11 00:00:00'),
(005, 'Manager', '2016-06-11 00:00:00'),
(004, 'Asst. Manager', '2016-06-11 00:00:00'),
(007, 'Executive', '2016-06-11 00:00:00'),
(006, 'Lead', '2016-06-11 00:00:00'),
(003, 'Lead', '2016-06-11 00:00:00');
SELECT DEPARTMENT, COUNT(*) AS no_of_works
FROM Worker
GROUP BY DEPARTMENT
ORDER BY no_of_works DESC;
```
## OUTPUT:
![image](https://github.com/Karthikeyan21001828/DBMS_EX02/assets/93427303/eb9153d7-d54b-4c79-8b69-573fa8419af4)
## Result:
A sql query to fetch the no_of_works for each department in descending order From the sample data has been executed.
