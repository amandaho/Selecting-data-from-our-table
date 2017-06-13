//Question 1
Select first_name, last_name
  From student;

first_name	last_name
Eric	Ephram
Greg	Gould
Adam	Ant
Howard	Hess
Charles	Caldwell
James	Joyce
Doug	Dumas
Kevin	Kraft
Frank	Fountain
Brian	Biggs

//Question 2
Select *
	From Student
	Where years_of_experience < 8;

student_id	first_name	last_name	years_of_experience	start_date
1	Eric	Ephram	2	2016-03-31
2	Greg	Gould	6	2016-09-30
3	Adam	Ant	5	2016-06-02
4	Howard	Hess	1	2016-02-28
5	Charles	Caldwell	7	2016-05-07
8	Kevin	Kraft	3	2016-04-15
10	Brian	Biggs	4	2015-12-25

//Question 3
Select last_name, start_date, student_id
	From Student
	Order by last_name;

last_name	start_date	student_id
Ant	2016-06-02	3
Biggs	2015-12-25	10
Caldwell	2016-05-07	5
Dumas	2016-07-04	7
Ephram	2016-03-31	1
Fountain	2016-01-31	9
Gould	2016-09-30	2
Hess	2016-02-28	4
Joyce	2016-08-27	6
Kraft	2016-04-15	8

//Question 4
Select *
	From Student
	Where first_name in ('Adam', 'James', 'Frank')
	Order by last_name desc;

student_id	first_name	last_name	years_of_experience	start_date
6	James	Joyce	9	2016-08-27
9	Frank	Fountain	8	2016-01-31
3	Adam	Ant	5	2016-06-02

//Question 5
Select first_name, last_name, start_date
	From Student
	Where start_date between '2016-01-01' and '2016-06-30'
	Order by start_date desc;

first_name	last_name	start_date
Adam	Ant	2016-06-02
Charles	Caldwell	2016-05-07
Kevin	Kraft	2016-04-15
Eric	Ephram	2016-03-31
Howard	Hess	2016-02-28
Frank	Fountain	2016-01-31

//Advanced Challenge Commands
Explain Assignment;
+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11)          | NO   |     | NULL    |                |
| assignment_nbr | int(11)          | NO   |     | NULL    |                |
| class_id       | int(11)          | YES  |     | NULL    |                |
| grade_id       | int(11) unsigned | YES  | MUL | NULL    |                |
+----------------+------------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

Select *
	From Assignment;

assignment_id	student_id	assignment_nbr	class_id	grade_id
1	1	1	1	1
2	2	2	2	2
3	3	3	3	3
4	4	4	4	4
5	5	5	5	5
6	6	6	6	1
7	7	6	7	2

Explain Grade;
+-------------------+------------------+------+-----+---------+----------------+
| Field             | Type             | Null | Key | Default | Extra          |
+-------------------+------------------+------+-----+---------+----------------+
| grade_id          | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| grade_description | varchar(50)      | NO   |     | NULL    |                |
+-------------------+------------------+------+-----+---------+----------------+
2 rows in set (0.01 sec)

grade_id	grade_description
1	Incomplete
2	Complete and Unsatisfactory
3	Complete and Satisfactory
4	Exceeds Expectations
5	Not Graded

//Hard Challenge
ERROR 1364 (HY000): Field 'student_id' doesn't have a default value
