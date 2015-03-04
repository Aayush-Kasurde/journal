MySQL
===== 

* Show version :: 

        mysql> SELECT VERSION(); 

* Show database name currently in use :: 
        
        mysql> SELECT DATABASE();

* whoami in mysql database:: 

        mysql> SELECT user(),current_user();


* Create user in mysql database:: 

        mysql> GRANT ALL ON <database_name>.<table_name> TO '<username>'@'<hostname>' IDENTIFIED BY '<password>'; 
        mysql> FLUSH PRIVILEGES;        


* Find all users in mysql database:: 

        mysql> use mysql;
        mysql> SELECT user FROM users;

* Repair database ::
    
        $ mysqlcheck --repair --all-databases 

* Repair tables :: 

        mysql> REPAIR TABLE <tablename>; 

* Change root password :: 
    
      	$ mysqladmin -u root -h localhost password "NEW-PASSWORD"

* To Deny access to annonymous user in database :: 

       	mysql> SET PASSWORD FOR anonymous@localhost=PASSWORD('secrete');
       	mysql> SET PASSWORD FOR ''@localhost=PASSWORD('secrete');
  
  	If username provided by user is not present, then mySQL server will try to login with annonymous user
  and if annonymous user does not contain any password then mySQL server will login automatically. This 
  will very dangerous while using mysql with php or other languages where developer specifies non existent 
  user which will allow php or script to login to mySQL database without any error.

* Group By Clause ::


	You can use GROUP BY to group values from a column, and, if you wish, perform calculations on that column.
	You can use COUNT, SUM, AVG etc function on the grouped column.

	To understand GROUP BY clause consider an employee_tbl table which is having following records:: 

        mysql> SELECT * FROM employee_tbl;


 +------+------+------------+--------------------+
 | id   | name | work_date  | daily_typing_pages |
 +------+------+------------+--------------------+
 |    1 | John | 2007-01-24 |                250 |
 +------+------+------------+--------------------+
 |    2 | Ram  | 2007-05-27 |                220 |
 +------+------+------------+--------------------+
 |    3 | Jack | 2007-05-06 |                170 |
 +------+------+------------+--------------------+
 |    3 | Jack | 2007-04-06 |                100 |
 +------+------+------------+--------------------+
 |    4 | Jill | 2007-04-06 |                220 |
 +------+------+------------+--------------------+
 |    5 | Zara | 2007-06-06 |                300 |
 +------+------+------------+--------------------+
 |    5 | Zara | 2007-02-06 |                350 |
 +------+------+------------+--------------------+

 7 rows in set (0.00 sec) 

 If we want to display total number of pages typed by each person separately.
 This is done by using aggregate functions in conjunction with a GROUP BY clause as follows ::

     mysql> SELECT name, COUNT(*)  FROM   employee_tbl GROUP BY name;

 +------+----------+
 | name | COUNT(*) |
 +------+----------+
 | Jack |        2 |
 +------+----------+
 | Jill |        1 |
 +------+----------+
 | John |        1 |
 +------+----------+
 | Ram  |        1 |
 +------+----------+
 | Zara |        2 |
 +------+----------+

 5 rows in set (0.04 sec)


* Show table status :: 

        mysql> SHOW TABLE STATUS WHERE NAME LIKE '<tablename>';


* Use regex in mysql queries ::

        mysql> SELECT name FROM person_tbl WHERE name REGEXP '^st';

* Show user privileges ::
        
        mysql> SHOW GRANTS '<username>'@'<hostname>';

* Show anonymous user privileges:: 
        
        mysql> SHOW GRANTS ''@'<hostname>'; 

* Remove select privileges from user ::

        mysql> REVOKE SELECT ON '<dbname>'@'<tablename>' FROM '<username>'@'<hostname>'; 
        mysql> FLUSH PRIVILEGES;        

* Remove all privileges from user ::

        mysql> REVOKE ALL ON '<dbname>'@'<tablename>' FROM '<username>'@'<hostname>'; 
        mysql> FLUSH PRIVILEGES;        

* Show warnings after query executed ::

        mysql> SHOW WARNINGS;

* Show errors after query executed:: 

        mysql> SHOW ERRORS;

* Show status of mysql server ::
        
        mysql>\s
        or
        mysql> SHOW STATUS;
