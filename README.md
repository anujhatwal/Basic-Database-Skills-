# Basic-Database-Skills-

Created queries using basic commands such as where, select, distinct, joins and subqueries 

/* Which designations are currently working on BYN Corporation? */
select  distinct Designation from dep_des_assoc d JOIN emp e ON d.DEPDEGID=e.Dep_Des_Id where Client_Name='BYN Corp';

Product Lead and Business Analyst 

/* Can you name the head of department for HR from the information represented in the tables above? */
select Emp_Name from emp e JOIN dep_des_assoc d ON e.Dep_Des_ID=d.DEPDEGID JOIN Department d1 ON d.Department_ID=d1.Department_ID where Department_Name='HR';

Ian Wright

/*In the employee table snapshot, which departments have no representation? */
select distinct Department_Name from Department where Department_Name not in 
(select Department_Name from emp e JOIN dep_des_assoc d ON e.Dep_Des_ID=d.DEPDEGID JOIN Department d1 ON d1.Department_ID=d.Department_ID);

DEP0004-Database Management




