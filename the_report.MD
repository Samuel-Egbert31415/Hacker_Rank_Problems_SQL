You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks
.![img_7.png](img_7.png)
Grades contains the following data:
![img_8.png](img_8.png)

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.

SELECT \
CASE \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   WHEN g.grade < 8 THEN NULL  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ELSE s.name \
END, \
g.grade, s.marks \
FROM students AS s,  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     grades AS g \
WHERE s.marks BETWEEN g.min_mark AND g.max_mark \
ORDER BY g.grade DESC, s.name ASC;


