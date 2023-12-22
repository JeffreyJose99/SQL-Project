
-- 1. Create a database called “LMT_University”.

CREATE DATABASE LMT_University;

-- Use Database

use LMT_University;

-- Create an “enrol” schema under “LMT_University”.

CREATE SCHEMA enrol;

-- Create the Database modeling in such a way that Model looks like-

-- Table 1
CREATE TABLE enrol.Lecturer(
    LecturerId INT PRIMARY KEY IDENTITY(1,1),
    LecturerName VARCHAR(200) NOT NULL,
    LecturerHighestQualification VARCHAR(500) NULL,
	LectureAge DATE NOT NULL,
	DepartmentId INT NOT NULL,	 
    InsertedOn DATETIME default Getdate()
);

-- Table 2
-- DROP TABLE enrol.Department
CREATE TABLE enrol.Department(
    DepartmentId INT PRIMARY KEY IDENTITY(1,1),
    DepartmentName VARCHAR(200) NOT NULL,
    DepartmentDesc VARCHAR(500) NULL,
	DepartmentCap INT  NOT NULL,
    InsertedOn DATETIME default Getdate()
);

-- Table 3
-- DROP TABLE enrol.Address
CREATE TABLE enrol.Address(
    AddressId INT PRIMARY KEY IDENTITY(1,1), 
    StreetAddress VARCHAR(200),
    City VARCHAR(500) NOT NULL,
	State VARCHAR(500),

	PostalCode VARCHAR(50),
	Country VARCHAR(500) NOT NULL,	 
    InsertedOn DATETIME default Getdate()
);

-- Table 4
-- drop TABLE enrol.Student
CREATE TABLE enrol.Student(
    StudentId INT PRIMARY KEY IDENTITY(1,1),
    StudentFirstName VARCHAR(200) NOT NULL,
    StudentLastName VARCHAR(500) NULL,
	StudentDOB DATE NOT NULL ,
	StudentMob VARCHAR(500) NULL,
	StudentRollNo INT NOT NULL,	
	DepartmentId INT NOT NULL,	
	AddressId INT NOT NULL,	 
    InsertedOn DATETIME default Getdate(),
	FOREIGN KEY (DepartmentId) REFERENCES enrol.Department(DepartmentId),
	FOREIGN KEY (AddressId) REFERENCES enrol.Address(AddressId)
);

----------------------------------------------------------------------------------------------------------------------------------------------------------
-- Data insertion into Tables (Lecturer, Department, Address, Student)

insert into enrol.department select 'IT', 'Information Technology', 60, 	GetDate()
insert into enrol.department select 'EE', 'Electrical Engineering', 120, 	GetDate()
insert into enrol.department select 'CSE', 'Computer Science Engineering', 140, 	GetDate()
insert into enrol.department select 'ME', 'Mechanical Engineering', 110, 	GetDate()
insert into enrol.department select 'ECE', 'Electronic and Communication Engineering', 80, 	GetDate()
insert into enrol.department select 'AEIE', 'Applied Electronics and Instrumentation Engineering', 50, 	GetDate()

--------------------------------------------------------------------------------------------------------------------

insert into enrol.Address Select '	5 Schurz Lane	','	Grybów	','	NULL	','	33-330	','	Poland	', 	GetDate()
insert into enrol.Address Select '	628 Waubesa Drive	','	Jinsheng	','	NULL	','	NULL	','	China	', 	GetDate()
insert into enrol.Address Select '	44135 Northfield Way	','	Nowy Dwór Mazowiecki	','	NULL	','	05-160	','	Poland	', 	GetDate()
insert into enrol.Address Select '	335 Bellgrove Road	','	Gaoqiao	','	NULL	','	NULL	','	China	', 	GetDate()
insert into enrol.Address Select '	28 Victoria Junction	','	Bukovec	','	NULL	','	739 84	','	Czech Republic	', 	GetDate()
insert into enrol.Address Select '	6 Stuart Road	','	Wushan	','	NULL	','	NULL	','	China	', 	GetDate()
insert into enrol.Address Select '	730 Barby Street	','	Zhengchang	','	NULL	','	NULL	','	China	', 	GetDate()
insert into enrol.Address Select '	22742 Schiller Street	','	Sumurwaru	','	NULL	','	NULL	','	Indonesia	', 	GetDate()
insert into enrol.Address Select '	31 Elka Junction	','	Cigembong	','	NULL	','	NULL	','	Indonesia	', 	GetDate()
insert into enrol.Address Select '	5 Kenwood Circle	','	Davao	','	NULL	','	8000	','	Philippines	', 	GetDate()
insert into enrol.Address Select '	99 Bunker Hill Crossing	','	Zarasai	','	NULL	','	32001	','	Lithuania	', 	GetDate()
insert into enrol.Address Select '	5 Farragut Center	','	Jaromerice	','	NULL	','	569 44	','	Czech Republic	', 	GetDate()
insert into enrol.Address Select '	25 Lerdahl Street	','	Nanshi	','	NULL	','	NULL	','	China	', 	GetDate()
insert into enrol.Address Select '	918 Bonner Way	','	Phayakkhaphum Phisai	','	NULL	','	44110	','	Thailand	', 	GetDate()
insert into enrol.Address Select '	9 West Alley	','	Sempu	','	NULL	','	NULL	','	Indonesia	', 	GetDate()
insert into enrol.Address Select '	234 Hagan Lane	','	Rennes	','	Bretagne	','	35033	','	France	', 	GetDate()
insert into enrol.Address Select '	33942 Eagle Crest Trail	','	Oliveiras	','	Porto	','	4745-235	','	Portugal	', 	GetDate()
insert into enrol.Address Select '	20791 Hermina Way	','	B?o L?c	','	NULL	','	NULL	','	Vietnam	', 	GetDate()
insert into enrol.Address Select '	86 Lake View Way	','	Marsa Alam	','	NULL	','	NULL	','	Egypt	', 	GetDate()
insert into enrol.Address Select '	19732 Burning Wood Parkway	','	Piteå	','	Norrbotten	','	944 73	','	Sweden	', 	GetDate()
insert into enrol.Address Select '	9320 Oak Valley Road	','	Rathangani	','	NULL	','	A45	','	Ireland	', 	GetDate()
insert into enrol.Address Select '	2638 Waubesa Circle	','	Honda	','	NULL	','	732048	','	Colombia	', 	GetDate()
insert into enrol.Address Select '	6999 Monument Center	','	Cortes	','	NULL	','	6341	','	Philippines	', 	GetDate()
insert into enrol.Address Select '	1 Warbler Hill	','	Proletar	','	NULL	','	NULL	','	Tajikistan	', 	GetDate()
insert into enrol.Address Select '	1311 Crowley Street	','	Baghlan	','	NULL	','	NULL	','	Afghanistan	', 	GetDate()
insert into enrol.Address Select '	19 Walton Way	','	Öldziyt	','	NULL	','	NULL	','	Mongolia	', 	GetDate()
insert into enrol.Address Select '	1 Glacier Hill	','	Cergy-Pontoise	','	Île-de-France	','	95304	','	France	', 	GetDate()
insert into enrol.Address Select '	5094 Gateway Way	','	Živinice	','	NULL	','	NULL	','	Bosnia and Herzegovina	', 	GetDate()
insert into enrol.Address Select '	2 Roth Pass	','	Tuatuka	','	NULL	','	NULL	','	Indonesia	', 	GetDate()
insert into enrol.Address Select '	89531 Northview Road	','	Ganyi	','	NULL	','	NULL	','	China	', 	GetDate()

-------------------------------------------------------------------------------------------------------------------------------

INSERT INTO enrol.STUDENT SELECT '	Joey	', '	Ironside	', '	22-11-1995	', '	1276234258	',	1	, 	3	, 	1	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Karlotta	', '	Garraway	', '	06-07-1997	', '	2192431615	',	2	, 	3	, 	24	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Jerry	', '	Stutte	', '	18-12-1996	', '	4125425783	',	3	, 	1	, 	17	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Yehudit	', '	Rahill	', '	15-01-1995	', '	9939485406	',	4	, 	2	, 	29	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Cele	', '	Crosetto	', '	24-11-1998	', '	3622733725	',	5	, 	3	, 	16	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Hazlett	', '	Mowsdale	', '	09-04-1995	', '	1482883476	',	6	, 	4	, 	23	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Carlyn	', '	Marks	', '	27-12-1996	', '	6129154080	',	7	, 	5	, 	20	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Ellis	', '	Boatman	', '	29-04-1997	', '	8269707118	',	8	, 	6	, 	7	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Florina	', '	Boyack	', '	03-08-1997	', '	9623352863	',	9	, 	3	, 	14	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Borg	', '	Innett	', '	03-09-1997	', '	5256034960	',	10	, 	1	, 	19	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Sayres	', '	Jennings	', '	12-05-1996	', '	8675076454	',	11	, 	4	, 	27	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Jarid	', '	Sprull	', '	02-11-1998	', '	1391270091	',	12	, 	2	, 	6	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Elvera	', '	Bannard	', '	07-09-1996	', '	7897232539	',	13	, 	4	, 	24	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Ody	', '	Inggall	', '	05-03-1995	', '	6094734260	',	14	, 	5	, 	25	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Curcio	', '	McWhan	', '	29-07-1996	', '	2394865847	',	15	, 	6	, 	11	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Connie	', '	Sinnie	', '	19-07-1995	', '	1473936221	',	16	, 	6	, 	23	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Auroora	', '	Nel	', '	05-09-1996	', '	2216400391	',	17	, 	3	, 	14	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Wendall	', '	Rosendale	', '	30-12-1999	', '	1818120249	',	18	, 	3	, 	28	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Hadley	', '	Bradbury	', '	16-08-1996	', '	6518067697	',	19	, 	1	, 	10	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Celine	', '	Smales	', '	11-07-1999	', '	7106508130	',	20	, 	2	, 	10	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Jesselyn', 'Stevenson	', '	16-05-1998	', '	9231672206	',	21	, 	2	, 	22	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Corinna	', '	Pinkney	', '	16-01-1998	', '	8323630067	',	22	, 	5	, 	29	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Orelle	', '	Adamthwaite	', '	26-07-1997	', '	2539126766	',	23	, 	3	, 	17	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Howie	', '	Seaman	', '	01-12-1997	', '	9888259627	',	24	, 	2	, 	4	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Sibyl	', '	Corey	', '	18-07-1996	', '	4493239590	',	25	, 	5	, 	11	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Ruperta	', '	Peaker	', '	22-05-1999	', '	5124781263	',	26	, 	5	, 	4	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Delmer	', '	Roughey	', '	21-04-1995	', '	4175314364	',	27	, 	3	, 	22	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Gifford	', '	O Scannill	', '	31-10-1996	', '	3134783726	',	28	, 	4	, 	22	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Hedy	', '	O Hone	', '	29-03-1998	', '	7316228047	',	29	, 	2	, 	17	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Shalna	', '	Hyde-Chambers	', '	23-11-1999	', '	7455116160	',	30	, 	5	, 	6	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Ferdie	', '	Di Napoli	', '	17-01-1995	', '	1905908693	',	31	, 	4	, 	30	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Piper	', '	Giacomuzzo	', '	14-09-1998	', '	5499340503	',	32	, 	6	, 	4	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Gerhardt	', '	Schruurs	', '	18-11-1999	', '	8197494894	',	33	, 	3	, 	1	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Mellicent	', '	Buncher	', '	03-10-1996	', '	4584525312	',	34	, 	5	, 	28	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Corette	', '	Demead	', '	17-09-1997	', '	4909862137	',	35	, 	5	, 	17	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Jorgan	', '	Barson	', '	01-05-1997	', '	6022309183	',	36	, 	1	, 	21	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Koral	', '	Bowen	', '	12-05-1998	', '	4198817454	',	37	, 	4	, 	3	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Allissa	', '	Kitter	', '	17-08-1998	', '	7328676920	',	38	, 	5	, 	7	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Townsend	', '	Doughtery	', '	13-04-1998	', '	2639777958	',	39	, 	4	, 	7	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Yolane	', '	Geratt	', '	10-06-1998	', '	2069585951	',	40	, 	6	, 	17	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Chrystel	', '	Allwood	', '	07-09-1996	', '	6958461692	',	41	, 	3	, 	25	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Dyana	', '	Clutterbuck	', '	22-09-1997	', '	5842483886	',	42	, 	1	, 	1	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Nikki	', '	Edy	', '	10-01-1999	', '	5096155315	',	43	, 	6	, 	25	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Hendrik	', '	Surr	', '	05-04-1997	', '	2021255732	',	44	, 	5	, 	11	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Marta	', '	Bosch	', '	28-09-1998	', '	4075136713	',	45	, 	6	, 	5	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Garrik	', '	Pell	', '	14-04-1999	', '	3071057649	',	46	, 	6	, 	7	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Stormi	', '	Colbron	', '	21-10-1998	', '	9968113654	',	47	, 	3	, 	28	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Angelique', '	Iacivelli	', '	07-06-1995	', '	9518365081	',	48	, 	5	, 	7	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Zack	', '	Hefforde	', '	25-07-1999	', '	5455693035	',	49	, 	1	, 	29	, 	GETDATE()
INSERT INTO enrol.STUDENT SELECT '	Gusella	', '	Pettiford	', '	23-08-1999	', '	2425172721	',	50	, 	4	, 	3	, 	GETDATE()

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

--Data Manipulation

Use LMT_University ;

--	9. Queries based on the above datasets.

-- a.	List all the Student information from the Student table.
 SELECT * FROM enrol.Student;

-- b.	List all the Department information from the Department table.
SELECT * FROM enrol.Department;

-- c.	List all the Lecturer information from the Lecturer table.
SELECT * FROM enrol.Lecturer;

-- d.	List all the Address information from the Address table.
SELECT * FROM enrol.Address;

-- e.e.	List the StudentFullName, StudentDOB, StudentMobile from Student [StudentFullName=StudentFirstName + ‘  ‘ + StudentLastName]
SELECT StudentFirstName + ' ' + StudentLastName as StudentFullName, StudentMob, StudentDOB FROM enrol.Student;

-- f.f.	List the StudentID, StudentFirstName, StudentLastName, StudentDOB, StudentMobile from Student in AddressID 7.
 SELECT StudentId, StudentFirstName, StudentLastName, StudentDOB,StudentMob FROM enrol.Student where AddressId = 7;

 -- g. g.	List all the student information whose first name is start with 'B'
 SELECT * FROM enrol.Student where StudentFirstName like 'B%'

 -- H. h.	List all the student information whose first name is start and end with 'A'
 SELECT * FROM enrol.Student where StudentFirstName like 'A%' and StudentFirstName like '%A'

 -- I. i.	Count the number of Student from Student table whose DepartmentID 6.
 SELECT COUNT(*) Cnt FROM enrol.Student where DepartmentId = 6

 -- J.	List all the StudentFullName, StudentAge, StudentMobile from Student [StudentFullName= StudentFirstName + ‘  ‘ + StudentLastName] [StudentAge= Current date – DOB (in Years)]
 SELECT  StudentFirstName + ' ' + StudentLastName as StudentFullName,  DATEDIFF(hour,STUDENTDOB,GETDATE())/8766 AS StudentAge , StudentMob from enrol.Student 

 -- K.	List all the StudentFullName, StudentAge, StudentMobile whose Age>23 from Student [StudentFullName= StudentFirstName + ‘  ‘ + StudentLastName] [StudentAge= Current date – DOB (in Years)]
 SELECT  StudentFirstName + ' ' + StudentLastName as StudentFullName,  DATEDIFF(hour,STUDENTDOB,GETDATE())/8766 AS StudentAge , StudentMob from enrol.Student 
 WHERE DATEDIFF(hour,STUDENTDOB,GETDATE())/8766 > 23

 -- L.	List all the StudentFullName, StudentAge, StudentMobile whose Age is either 21 or 23 from Student [StudentFullName= StudentFirstName + ‘  ‘ + StudentLastName] [StudentAge= Current date – DOB (in Years)]
 SELECT  StudentFirstName + ' ' + StudentLastName as StudentFullName,  DATEDIFF(hour,STUDENTDOB,GETDATE())/8766 AS StudentAge , StudentMob from enrol.Student 
 WHERE DATEDIFF(hour,STUDENTDOB,GETDATE())/8766 IN ( 21, 23)

 -- M. List all the LecturerID, LecturerName, LecturerHighestQualification, LecturerAge from Lecturer.
 SELECT LecturerID, LecturerName, LecturerHighestQualification, LectureAge from enrol.Lecturer 

 -- N. List all the LecturerID, LecturerName, LecturerHighestQualification, LecturerAge from Lecturer whose HighestQualification is either “MS” or “PhD”.
 SELECT LecturerID, LecturerName, LecturerHighestQualification, LectureAge from enrol.Lecturer WHERE LecturerHighestQualification  IN ('MS','PhD') 

 -- O. List all the lecturer information who belongs to DepartmentID 2.
 SELECT * from enrol.Lecturer WHERE DepartmentId = 2;

 -- P. List all the lecturer information whose name end with “R”.
 SELECT * from enrol.Lecturer WHERE LecturerName LIKE '%R'

 -- Q. List all the lecturer information whose name either start or end with “E”.
 SELECT * from enrol.Lecturer WHERE LecturerName LIKE '%E' OR LecturerName LIKE 'E%'

 -- R. List all the lecturer name is in capital letter.
 SELECT UPPER(LecturerName) from enrol.Lecturer

 -- S. Display 5 character from the lecturer name along with LecturerID and LecturerHighestQualification.
 SELECT LecturerID, SUBSTRING (LecturerName, 1, 5) LecturerName, LecturerHighestQualification, LectureAge from enrol.Lecturer 

 -- T. List LecturerID, LecturerName, LecturerHighestQualification, LecturerAge(in year) [LecturerAge= Current Date – LecturerAge)] (in year).
 SELECT LecturerID, LecturerName, LecturerHighestQualification, DATEDIFF(hour,LectureAge,GETDATE())/8766 AS LecturerAge from enrol.Lecturer 

 -- U. List DepartmentID, DepartmentName, DepartmentDescription, DepartmentCapacity from Department.
 SELECT DepartmentID, DepartmentName, DepartmentDesc, DepartmentCap from enrol.Department

 -- V. List all the Department information who’s DepartmentName is “ECE”.
 SELECT DepartmentDesc from enrol.Department where DepartmentName =  'ECE'

 -- W. List all DepartmentName, DepartmentDescription, DepartmentCapacity from Department whose capacity is greater than 60.
 select DepartmentName, DepartmentDesc, DepartmentCap from enrol.Department where DepartmentCap > 60

 -- X. List all AddressID, StreetAddress, City, State, PostalCode, Country from Address.
 select AddressID, StreetAddress, City, State, PostalCode, Country from enrol.Address 

 -- Y. List all AddressID, StreetAddress, City, State, PostalCode, Country from Address who belongs to “Poland” country.
 select AddressID, StreetAddress, City, State, PostalCode, Country from enrol.Address where Country = 'Poland'

 -- Z. List all the Address information whose state is null.
 select * from enrol.Address where state is null

 -- aa. List all the Address information whose PostalCode is not null.
 select * from enrol.Address where PostalCode is not null

 -- bb. List all the Address information whose City name is "Honda" and Country name is "Colombia"
 select AddressID, StreetAddress, City, State, PostalCode, Country from enrol.Address where City = 'Honda' and Country = 'Colombia'  

 -----------------------------------------------------------------------------


-- 10.	Write the following Query based on the above datasets.

--a. List unique DOB from Student.
select distinct StudentDOB DOB from enrol.Student

--b. List unique DepartmentName from Department.
SELECT distinct DepartmentName from enrol.DEPARTMENT

--c. List unique Country name from Address.
SELECT distinct Country from enrol.Address

--d. List unique State name from Address.
SELECT distinct State from enrol.Address

--e. List unique City name from Address.
SELECT distinct City from enrol.Address

--f. List all the LecturerID, LecturerName, LecturerHighestQualification, LecturerYearService from Lecturer [LecturerYearService= Current Date – LecturerAge] (in year).
SELECT LecturerID, LecturerName, LecturerHighestQualification, DATEDIFF(hour,LectureAge,GETDATE())/8766 LecturerYearService from ENROL.Lecturer 

--g. List all the LecturerID, LecturerName, LecturerHighestQualification, LecturerType from Lecturer [LecturerType= if LecturerYearService< 5 then "Begining Level Experience" else if LecturerYearService>= 5 and LecturerYearService<10 then "Mid Level experience" else "Experienced".
SELECT LecturerID, LecturerName, LecturerHighestQualification,
case 
when LecturerYearService < 5 Then 'Begining Level Experience'
when LecturerYearService >= 5 and LecturerYearService<10 Then 'Mid Level experience'
ELSE 'Experienced'
END AS LecturerType
from (
SELECT LecturerID, LecturerName, LecturerHighestQualification, DATEDIFF(hour,LectureAge,GETDATE())/8766 LecturerYearService from ENROL.Lecturer 
) x ;
--------------------------------------------------------------------------------------------------------------------------------------

-- 11.Write the following Query based on the above datasets.
-- Write the following Query based on the above datasets.

--a. Display all Student and their Department Information based on the relationship.
SELECT StudentFirstName + '' + StudentLastName AS STUDENT, DepartmentName FROM ENROL.Student a LEFT JOIN ENROL.DEPARTMENT b ON a.DepartmentId = b.DepartmentId 

--b. Display all Student and their Address Information based on the relationship.
SELECT StudentFirstName + '' + StudentLastName AS STUDENT, StreetAddress + ' , ' + City + ' , ' + Country as address FROM ENROL.Student a LEFT JOIN ENROL.Address b ON a.AddressId = b.AddressId 

--c. Display all Department and their Lecturer Information based on the relationship.
select * from enrol.Department a, enrol.Lecturer b where a.DepartmentId = b.DepartmentId

--d. Display all Student with their Department with Lecturer Information based on the relationship.
select * from enrol.Student a , enrol.department b where a.DepartmentId = b.DepartmentId

--E. Display all Student with their Address and Department Information based on the relationship.
select * from enrol.Student a , enrol.Address b where a.AddressId = b.AddressId

--F.	Display all Student with Address, Department and Lecturer Information based on the relationship.
select a.StudentFirstName + '' + a.StudentLastName AS STUDENT, d.LecturerName, c.DepartmentName, b.StreetAddress + ' , ' + b.City + ' , ' + b.Country as address
from enrol.Student a , enrol.Address b, enrol.Department c, enrol.Lecturer d
where a.AddressId = b.AddressId
and a.DepartmentId = c.DepartmentId
and a.DepartmentId = d.DepartmentId
order by a.StudentFirstName, DepartmentName, LecturerName

--G. Display all Student with Address, Department and Lecturer Information who belongs to either “ME” or “ECE” department.
select a.StudentFirstName + '' + a.StudentLastName AS STUDENT, d.LecturerName, c.DepartmentName, b.StreetAddress + ' , ' + b.City + ' , ' + b.Country
from enrol.Student a , enrol.Address b, enrol.Department c, enrol.Lecturer d
where a.AddressId = b.AddressId
and a.DepartmentId = c.DepartmentId
and a.DepartmentId = d.DepartmentId
and DepartmentName in ('ME','ECE')
order by a.StudentFirstName, DepartmentName, LecturerName

--H. Display Student with Department and their Lecturer information based on the LecturerHighestQualification either “MS” or “PhD”.
select a.StudentFirstName + '' + a.StudentLastName AS STUDENT, LecturerHighestQualification, d.LecturerName, c.DepartmentName, b.StreetAddress + ' , ' + b.City + ' , ' + b.Country as address
from enrol.Student a , enrol.Address b, enrol.Department c, enrol.Lecturer d
where a.AddressId = b.AddressId
and a.DepartmentId = c.DepartmentId
and a.DepartmentId = d.DepartmentId
and LecturerHighestQualification IN ('MS','PhD')
order by a.StudentFirstName, DepartmentName, LecturerName

--I.	Display Student with Department and Address Information, where student belongs to “Thailand” country.
select a.StudentFirstName + '' + a.StudentLastName AS STUDENT, LecturerHighestQualification, d.LecturerName, c.DepartmentName, b.StreetAddress + ' , ' + b.City + ' , ' + b.Country as address
from enrol.Student a , enrol.Address b, enrol.Department c, enrol.Lecturer d
where a.AddressId = b.AddressId
and a.DepartmentId = c.DepartmentId
and a.DepartmentId = d.DepartmentId
and b. Country = 'Thailand'
order by a.StudentFirstName, DepartmentName, LecturerName

--J.	Display Count of Student, Department wise.
select count ( a.StudentFirstName) AS StudentCount, c.DepartmentName
from enrol.Student a , enrol.Department c
where a.DepartmentId = c.DepartmentId
group by c.DepartmentName

--K.	Display Count of Lecturer, Department wise.
select count (a.LecturerName) LectureCount, b.DepartmentName
from enrol.Lecturer a, enrol.Department b
where a.DepartmentId = b.DepartmentId
group by b.DepartmentName

--L.	Display Count of Student, Country wise.
select count (a.StudentFirstName) StudentCount, b.Country
from enrol.Student a, enrol.Address b
where a.AddressId = b.AddressId
group by b.Country

---------------------------------------------------------------------------------

--12.	Write the following Query based on the above datasets.

--a.	Create new table StudCopy and copy all records from Student table.
select * into enrol.StudCopy
from enrol.Student ;

--b.	Create a new table DeptCopy and copy only the schema from Department table.
select * into enrol.DeptCopySchema
from enrol.Department where 1=2;

--c.	Create a new table DepartmentCopy and copy all records from Department table.
select * into enrol.DepartmentCopy
from enrol.Department ;

--d.	Create a new table AddrCopy and copy only the schema from Address table.
select * into enrol.AddrCopySchema
from enrol.Address where 1=2;

--e. Create a new table AddrCopy and copy all the records from Address table.

select * into enrol.AddrCopy
from enrol.Address ;

--f.	Create a new table LecturerCopy and copy all the records from Lecturer table.
select * into enrol.LecturerCopy
from enrol.Lecturer ;

--------------------------------------------------------------------------------------------------------------------
--13.	Write the following Query based on the above datasets.

--a.	Delete all the records from LecturerCopy table.
delete from enrol.LecturerCopy ;

--b.	Delete all the student information for the students who belong to “IT” department.
delete from enrol.Student where DepartmentId = (select departmentid from enrol.Department where DepartmentName = 'IT') ;

--c.	Delete all the student information for the students who belong to “Indonesia” country.
delete from enrol.Student where AddressId = (select AddressId from enrol.Address where Country = 'Indonesia') ;

--d.	Delete all the student information for the student who belongs to “Nanshi” city.
delete from enrol.Student where AddressId = (select AddressId from enrol.Address where City = 'Nanshi') ;

--e.	Delete all the student information for the student who belongs to “Bretagne” state.
delete from enrol.Student where AddressId = (select AddressId from enrol.Address where State = 'Bretagne') ;

------------------------------------------------------------------------------------------------------------------

--14.	Write the following Query based on the above datasets.

--a.	Update StudentMobile for those students who belongs to Department “ME”.
UPDATE enrol.Student  SET StudentMob = '' where DepartmentId = (select departmentid from enrol.Department where DepartmentName = 'ME') 

--b.	Update Student DepartmentID as 3, for the StudentID=42.
UPDATE enrol.Student  SET DepartmentId = 3 where StudentId = 42 

--c.	Update LecturerHighestQualification as “PHd” for the Lecturer whose LecturerHighestQualification= “PhD”.
update enrol.Lecturer set LecturerHighestQualification = 'PHd' where LecturerHighestQualification = 'PhD'

--d.	Update PostalCode as “00000” for the Address which contain NULL as a PostalCode.
update enrol.Address set PostalCode = '00000' where PostalCode is null

--e.	Update StudentLastName as “Paul” for the Student whose Name is “Jerry”.
update enrol.StudCopy set StudentLastName = 'Paul' where StudentFirstName = 'Jerry'

------------------------------------------------------------------------------------------------------------------------------------------
