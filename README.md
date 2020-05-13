# Basic-Database-Skills-

Created queries using basic commands such as where, select, distinct, joins and subqueries 

Below are the data details 

Emp Table
Employee ID	Employee Name	Gender	Department-Designation ID	Client Name
EMP0001	    Michael Keane	M	      DD001	                    BYN Corp
EMP0002	    Ian Wright	  M	      DD004	
EMP0003	    Kate Myers	  F	      DD003	                    BYN Corp
EMP0004	    Danny Ings	  M	      DD003	                    BYN Corp
EMP0005	    Alex Morgan	  F	      DD002	                    PG Inc.
EMP0006	    Emily Stone	  F	      DD006	
EMP0007     Xing Vu	      M	      DD003	                    PG Inc.
EMP0008	    Michele 	    F	      DD001	                    PG Inc. 

Department table 
Department ID	Department Name	    Number of Employees	    Head of Department
DEP0001	      Product Development	42	                    EMP0010
DEP0002	      HR	                15	                    EMP0002
DEP0003	      Finance	            7	                      EMP0012
DEP0004	      Database Management	7	                      EMP0045

Dep_des_assoc table
DEPDEGID	Department ID	    Designation
DD001	    DEP0001	          Product Lead
DD002	    DEP0001	          Product Architect
DD003	    DEP0001	          Business Analyst
DD004	    DEP0002	          HR Lead
DD005	    DEP0002	          HRIS Analyst
DD006	    DEP0003	          Financial Analyst
DD007	    DEP0003	          Sr. Financial Analyst
DD008	    DEP0004	          Database Engineer

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




