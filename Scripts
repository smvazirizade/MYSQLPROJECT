Problem 1
Find the total number of crimes recorded in the CRIME table
# Rows in Crime table
%sql select COUNT(*) from CHICAGO_CRIME_DATA
ans:533

Problem 2
Retrieve first 10 rows from the CRIME table
%sql select * from CHICAGO_CRIME_DATA limit 6


Problem 3
How many crimes involve an arrest?
%sql select count(*) from CHICAGO_CRIME_DATA where arrest="TRUE"
ans:163

Problem 4
Which unique types of crimes have been recorded at GAS STATION locations?
%sql select distinct(primary_type) from CHICAGO_CRIME_DATA where location_description like '%GAS%'
ans:
CRIMINAL TRESPASS
NARCOTICS
ROBBERY
THEFT


Problem 5
In the CENUS_DATA table list all Community Areas whose names start with the letter ‘B’.
%sql select distinct(community_area_name) from CENSUS_DATA where community_area_name like 'B%'
ans:
Belmont Cragin
Beverly
Bridgeport
Brighton Park
Burnside

Problem 6
Which schools in Community Areas 10 to 15 are healthy school certified?
%sql select name_of_school from CHICAGO_PUBLIC_SCHOOLS where LCASE(healthy_school_certified)='yes' and (community_area_number between 10 and 15)
ans:Rufus M Hitch Elementary School


Problem 7
What is the average school Safety Score?
%sql select AVG(safety_score) from CHICAGO_PUBLIC_SCHOOLS
ans:49.504873

Problem 8
List the top 5 Community Areas by average College Enrollment [number of students
%sql select community_area_number,AVG(college_enrollment) as average from CHICAGO_PUBLIC_SCHOOLS group by community_area_number order by AVG(college_enrollment) desc limit 5
ans:
57	2411.500000
18	1317.000000
62	1233.333333
58	1205.875000
19	1198.833333



Problem 9
Use a sub-query to determine which Community Area has the least value for school Safety Score
%sql select community_area_number,community_area_name from CHICAGO_PUBLIC_SCHOOLS where safety_score=(select min(safety_score) from CHICAGO_PUBLIC_SCHOOLS) 
community_area_number,community_area_name,safety_score,PER_CAPITA_INCOME from CHICAGO_PUBLIC_SCHOOLS,CNESUS_DATA where safety_score=1
ans:
40	WASHINGTON PARK


Problem 10
Find the Per Capita Income of the Community Area which has a school Safety Score of 1.
%sql select CHICAGO_PUBLIC_SCHOOLS.community_area_number,PER_CAPITA_INCOME from CHICAGO_PUBLIC_SCHOOLS,CENSUS_DATA where safety_score=1 and CHICAGO_PUBLIC_SCHOOLS.community_area_number=CENSUS_DATA.community_area_number
ans:
40	1378



