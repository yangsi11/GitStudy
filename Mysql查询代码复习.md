# Mysql查询代码复习

请写出创建名为 "students" 的数据库的 SQL 语句。
1.在 "students" 数据库中创建一个名为 "student_info" 的表，该表包含 "id", "name", "age", "grade" 四个字段，并设置 "id" 字段为主键。

```sql
CREATE TABLE `student_info` (
  `ID` varchar(20) NOT NULL,
  `NAME` varchar(20) NOT NULL,
  `AGE` varchar(20) NOT NULL,
  `GRADE` varchar(20) NOT NULL,
  PRIMARY KEY (`ID`)
) 
```

2.删除表

```sql
DROP TABLES  IF EXISTS  STUDENT(表名)
```

3.插入表
向 "student_info" 表中插入三条记录，id分别为 1, 2, 3，name分别为 "Alice", "Bob", "Charlie"，age分别为 20, 21, 22，grade分别为 "A", "B", "C"。

```sql
INSERT INTO STUDENT_INFO (ID,NAME,AGE,grade) VALUES(1,'Alice',20,'A'),(2,'Bob',21,'B'),(3,'Charlie',22,'C')
```

除了数字的时候,其他String字段需要加入('')

```sql
INSERT INTO STUDENT_INFO VALUES(4,'Stringziduan',23,'D')
```





4
查询 "student_info" 表中年龄大于等于 21 的学生信息。

```sql
select  * from student_info where age>21
```

5.
使用 IN 子句查询 "student_info" 表中成绩为 "A" 或 "B" 的学生信息。

```sql
select * from student_info where grade in ('A','B')
```

6.ORDER BY   ,DESC 是降序   ,ASC 是升序  
使用 ORDER BY 子句按年龄对 "student_info" 表中的学生进行排序。

```sql
SELECT * FROM STUDENT_INFO ORDER BY AGE DESC
```

7.**LIMIT是可以单独使用的,也可以结合ORDER BY 排序**
使用 LIMIT 子句查询 "student_info" 表中的前三个学生信息。

```sql
SELECT * FROM STUDENT_INFO LIMIT 3

SELECT * FROM STUDENT_INFO ORDER BY AGE DESC 3
```

8.字查询就是 where grade=(select Max(grade) from student_info)
使用子查询查询 "student_info" 表中成绩最高的学生的姓名和成绩。

```sql
SELECT * FROM STUDENT_INFO WHERE GRADE=(SELECT MAX(GRADE) FROM STUDENT_INFO)
```

 

9.多表查询

```mysql
SELECT   
   student.`name` AS `学生姓名`, 
    teacher.`name` AS `辅导老师`,   
    teacher.`course_id` AS `课程编码`,   
    teacher. `course`  AS `科目`,  
		score.`grades` AS '科目成绩',   
    student.`classname` AS `班级`  
    
FROM   
    teacher   
INNER JOIN   
    student ON teacher.course_id = student.course_id  
INNER JOIN   
    score ON student.course_id = score.subject_id;
```



10.更新表中内容

```mysql
Update table set name='扬天非'	 where id=1
```

