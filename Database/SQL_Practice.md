# SQL Practice

### Select 
<!-- Easy -->
- [175. Combine Two Tables (Easy)](#175-combine-two-tables)
- [181. Employees Earning More Than Their Managers (Easy)](#181-employees-earning-more-than-their-managers)
- [182. Duplicate Emails (Easy)](#182-duplicate-emails)
- [183. Customers Who Never Order (Easy)](#183-customers-who-never-order)
- [595. Big Countries (Easy)](#595-big-countries)
- [596. Classes More Than 5 Students (Easy)](#596-classes-more-than-5-students)
- [620. Not Boring Movies (Easy)](#620-not-boring-movies)
<!-- Medium -->
- [176. Second Highest Salary (Medium)](#176-second-highest-salary)
- [178. Rank Scores (Medium)](#178-rank-scores)
- [180. Consecutive Numbers (Medium)](#180-consecutive-numbers)
- [184. Department Highest Salary (Medium)](#184-department-highest-salary)
- [626. Exchange Seats (Medium)](#626-exchange-seats)
    
### Update
- [627. Swap Salary (Easy)](#627-swap-salary)

### Delete
- [196. Delete Duplicate Emails (Easy)](#196-delete-duplicate-emails)

## 175. Combine Two Tables

https://leetcode.com/problems/combine-two-tables/description/

Write a solution to report the first name, last name, city, and state of each person in the Person table. If the address of a personId is not present in the Address table, report null instead.

#### Person：
```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| PersonId    | int     |
| FirstName   | varchar |
| LastName    | varchar |
+-------------+---------+
PersonId is the primary key column for this table.
```

#### Address：
```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| AddressId   | int     |
| PersonId    | int     |
| City        | varchar |
| State       | varchar |
+-------------+---------+
AddressId is the primary key column for this table.
```

#### Solution:
```sql
SELECT
    FirstName,
    LastName,
    City,
    State
FROM
    Person P
    LEFT JOIN Address A
    ON P.PersonId = A.PersonId;
```

## 181. Employees Earning More Than Their Managers

https://leetcode.com/problems/employees-earning-more-than-their-managers/description/

Write a solution to find the employees who earn more than their managers.

#### Employee：
```
+----+-------+--------+-----------+
| Id | Name  | Salary | ManagerId |
+----+-------+--------+-----------+
| 1  | Joe   | 70000  | 3         |
| 2  | Henry | 80000  | 4         |
| 3  | Sam   | 60000  | NULL      |
| 4  | Max   | 90000  | NULL      |
+----+-------+--------+-----------+
```

#### Solution:
```sql
SELECT
    E1.NAME AS Employee
FROM
    Employee E1
    INNER JOIN Employee E2
    ON E1.ManagerId = E2.Id
    AND E1.Salary > E2.Salary;
```

## 182. Duplicate Emails

https://leetcode.com/problems/duplicate-emails/description/

Write a solution to report all the duplicate emails. Note that it's guaranteed that the email field is not NULL.

#### Input:
```
+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+
```

#### Output:
```
+---------+
| Email   |
+---------+
| a@b.com |
+---------+
```

#### Solution:
```sql
SELECT
    Email
FROM
    Person
GROUP BY
    Email
HAVING
    COUNT( * ) >= 2;
```

## 183. Customers Who Never Order

https://leetcode.com/problems/customers-who-never-order/description/

Write a solution to find all customers who never order anything.

#### Customers：
```
+----+-------+
| Id | Name  |
+----+-------+
| 1  | Joe   |
| 2  | Henry |
| 3  | Sam   |
| 4  | Max   |
+----+-------+
```

#### Orders：
```
+----+------------+
| Id | CustomerId |
+----+------------+
| 1  | 3          |
| 2  | 1          |
+----+------------+
```

#### Output:
```
+-----------+
| Customers |
+-----------+
| Henry     |
| Max       |
+-----------+
```

#### Solution:
```sql
SELECT
    C.Name AS Customers
FROM
    Customers C
    LEFT JOIN Orders O
    ON C.Id = O.CustomerId
WHERE
    O.CustomerId IS NULL;
```

## 595. Big Countries

https://leetcode.com/problems/big-countries/description/

Write a solution to find the name, population, and area of the big countries.

A country is big if:

- it has an area of at least three million (i.e., 3000000 km2), or
- it has a population of at least twenty-five million (i.e., 25000000).

#### Input:
```
+-----------------+------------+------------+--------------+---------------+
| name            | continent  | area       | population   | gdp           |
+-----------------+------------+------------+--------------+---------------+
| Afghanistan     | Asia       | 652230     | 25500100     | 20343000      |
| Albania         | Europe     | 28748      | 2831741      | 12960000      |
| Algeria         | Africa     | 2381741    | 37100000     | 188681000     |
| Andorra         | Europe     | 468        | 78115        | 3712000       |
| Angola          | Africa     | 1246700    | 20609294     | 100990000     |
+-----------------+------------+------------+--------------+---------------+
```

#### Output:
```
+--------------+-------------+--------------+
| name         | population  | area         |
+--------------+-------------+--------------+
| Afghanistan  | 25500100    | 652230       |
| Algeria      | 37100000    | 2381741      |
+--------------+-------------+--------------+
```

#### Solution:
```sql
SELECT name,
    population,
    area
FROM
    World
WHERE
    area > 3000000
    OR population > 25000000;
```

## 596. Classes More Than 5 Students

https://leetcode.com/problems/classes-more-than-5-students/description/

Write a solution to find all the classes that have at least five students.

#### Input:
```
+---------+------------+
| student | class      |
+---------+------------+
| A       | Math       |
| B       | English    |
| C       | Math       |
| D       | Biology    |
| E       | Math       |
| F       | Computer   |
| G       | Math       |
| H       | Math       |
| I       | Math       |
+---------+------------+
```

#### Output:
```
+---------+
| class   |
+---------+
| Math    |
+---------+
```

#### Solution:
```sql
SELECT
    class
FROM
    courses
GROUP BY
    class
HAVING
    count( student ) >= 5;
```

## 620. Not Boring Movies

https://leetcode.com/problems/not-boring-movies/description/

Write a solution to report the movies with an odd-numbered ID and a description that is not "boring".

Return the result table ordered by rating in descending order.

#### Input:
```
+---------+-----------+--------------+-----------+
|   id    | movie     |  description |  rating   |
+---------+-----------+--------------+-----------+
|   1     | War       |   great 3D   |   8.9     |
|   2     | Science   |   fiction    |   8.5     |
|   3     | irish     |   boring     |   6.2     |
|   4     | Ice song  |   Fantacy    |   8.6     |
|   5     | House card|   Interesting|   9.1     |
+---------+-----------+--------------+-----------+
```

#### Output:
```
+---------+-----------+--------------+-----------+
|   id    | movie     |  description |  rating   |
+---------+-----------+--------------+-----------+
|   5     | House card|   Interesting|   9.1     |
|   1     | War       |   great 3D   |   8.9     |
+---------+-----------+--------------+-----------+
```

#### Solution:
```sql
SELECT
    *
FROM
    cinema
WHERE
    id % 2 = 1
    AND description != 'boring'
ORDER BY
    rating DESC;
```

## 176. Second Highest Salary

https://leetcode.com/problems/second-highest-salary/description/

```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```

查找工资第二高的员工。

```
+---------------------+
| SecondHighestSalary |
+---------------------+
| 200                 |
+---------------------+
```

没有找到返回 null 而不是不返回数据。

### Solution

为了在没有查找到数据时返回 null，需要在查询结果外面再套一层 SELECT。

```sql
SELECT
    ( SELECT DISTINCT Salary 
     FROM Employee 
     ORDER BY Salary DESC 
     LIMIT 1, 1 ) SecondHighestSalary;
```

## 178. Rank Scores

https://leetcode.com/problems/rank-scores/description/

得分表：

```
+----+-------+
| Id | Score |
+----+-------+
| 1  | 3.50  |
| 2  | 3.65  |
| 3  | 4.00  |
| 4  | 3.85  |
| 5  | 4.00  |
| 6  | 3.65  |
+----+-------+
```

将得分排序，并统计排名。

```
+-------+------+
| Score | Rank |
+-------+------+
| 4.00  | 1    |
| 4.00  | 1    |
| 3.85  | 2    |
| 3.65  | 3    |
| 3.65  | 3    |
| 3.50  | 4    |
+-------+------+
```

### Solution

要统计某个 score 的排名，只要统计大于等于该 score 的 score 数量。

| Id | score | 大于等于该 score 的 score 数量 | 排名 |
| :---: | :---: | :---: | :---: |
| 1 | 4.1 | 3 | 3 |
| 2 | 4.2 | 2 | 2 |
| 3 | 4.3 | 1 | 1 |

使用连接操作找到某个 score 对应的大于等于其值的记录：

```sql
SELECT
	*
FROM
    Scores S1
    INNER JOIN Scores S2
    ON S1.score <= S2.score
ORDER BY
    S1.score DESC, S1.Id;
```

| S1.Id | S1.score | S2.Id | S2.score |
| :---: | :---: | :---: | :---: |
|3|	4.3|	3	|4.3|
|2|	4.2|	2|	4.2|
|2|	4.2	|3	|4.3|
|1|	4.1	|1|	4.1|
|1|	4.1	|2|	4.2|
|1|	4.1	|3|	4.3|

可以看到每个 S1.score 都有对应好几条记录，我们再进行分组，并统计每个分组的数量作为 'Rank'

```sql
SELECT
    S1.score 'Score',
    COUNT(*) 'Rank'
FROM
    Scores S1
    INNER JOIN Scores S2
    ON S1.score <= S2.score
GROUP BY
    S1.id, S1.score
ORDER BY
    S1.score DESC, S1.Id;
```

| score | Rank |
| :---: | :---: |
| 4.3 | 1 |
| 4.2 | 2 |
| 4.1 | 3 |

上面的解法看似没问题，但是对于以下数据，它却得到了错误的结果：

| Id | score |
| :---: | :---: |
| 1 | 4.1 |
| 2 | 4.2 |
| 3 | 4.2 |

| score | Rank |
| :---: | :--: |
|  4.2  |  2   |
|  4.2  |  2   |
|  4.1  |  3   |

而我们希望的结果为：

| score | Rank |
| :---: | :--: |
|  4.2  |  1   |
|  4.2  |  1   |
|  4.1  |  2   |

连接情况如下：

| S1.Id | S1.score | S2.Id | S2.score |
| :---: | :------: | :---: | :------: |
|   2   |   4.2    |   3   |   4.2    |
|   2   |   4.2    |   2   |   4.2    |
|   3   |   4.2    |   3   |   4.2    |
|   3   |   4.2    |   2   |   4.1    |
|   1   |   4.1    |   3   |   4.2    |
|   1   |   4.1    |   2   |   4.2    |
|   1   |   4.1    |   1   |   4.1    |

我们想要的结果是，把分数相同的放在同一个排名，并且相同分数只占一个位置，例如上面的分数，Id=2 和 Id=3 的记录都有相同的分数，并且最高，他们并列第一。而 Id=1 的记录应该排第二名，而不是第三名。所以在进行 COUNT 计数统计时，我们需要使用 COUNT( DISTINCT S2.score ) 从而只统计一次相同的分数。

```sql
SELECT
    S1.score 'Score',
    COUNT( DISTINCT S2.score ) 'Rank'
FROM
    Scores S1
    INNER JOIN Scores S2
    ON S1.score <= S2.score
GROUP BY
    S1.id, S1.score
ORDER BY
    S1.score DESC;
```

## 180. Consecutive Numbers

https://leetcode.com/problems/consecutive-numbers/description/

数字表：

```html
+----+-----+
| Id | Num |
+----+-----+
| 1  |  1  |
| 2  |  1  |
| 3  |  1  |
| 4  |  2  |
| 5  |  1  |
| 6  |  2  |
| 7  |  2  |
+----+-----+
```

查找连续出现三次的数字。

```html
+-----------------+
| ConsecutiveNums |
+-----------------+
| 1               |
+-----------------+
```

### Solution

```sql
SELECT
    DISTINCT L1.num ConsecutiveNums
FROM
    Logs L1,
    Logs L2,
    Logs L3
WHERE L1.id = l2.id - 1
    AND L2.id = L3.id - 1
    AND L1.num = L2.num
    AND l2.num = l3.num;
```

## 184. Department Highest Salary

https://leetcode.com/problems/department-highest-salary/description/

Employee：

```
+----+-------+--------+--------------+
| Id | Name  | Salary | DepartmentId |
+----+-------+--------+--------------+
| 1  | Joe   | 70000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
+----+-------+--------+--------------+
```

Department：

```
+----+----------+
| Id | Name     |
+----+----------+
| 1  | IT       |
| 2  | Sales    |
+----+----------+
```

查找一个 Department 中收入最高者的信息：

```html
+------------+----------+--------+
| Department | Employee | Salary |
+------------+----------+--------+
| IT         | Max      | 90000  |
| Sales      | Henry    | 80000  |
+------------+----------+--------+
```

### Solution

创建一个临时表，包含了部门员工的最大薪资。可以对部门进行分组，然后使用 MAX() 汇总函数取得最大薪资。

之后使用连接找到一个部门中薪资等于临时表中最大薪资的员工。

```sql
SELECT
    D.NAME Department,
    E.NAME Employee,
    E.Salary
FROM
    Employee E,
    Department D,
    ( SELECT DepartmentId, MAX( Salary ) Salary 
     FROM Employee 
     GROUP BY DepartmentId ) M
WHERE
    E.DepartmentId = D.Id
    AND E.DepartmentId = M.DepartmentId
    AND E.Salary = M.Salary;
```

## 626. Exchange Seats

https://leetcode.com/problems/exchange-seats/description/

Write a solution to swap the seat id of every two consecutive students. If the number of students is odd, the id of the last student is not swapped.

Return the result table ordered by id in ascending order.

```html
+---------+---------+
|    id   | student |
+---------+---------+
|    1    | Abbot   |
|    2    | Doris   |
|    3    | Emerson |
|    4    | Green   |
|    5    | Jeames  |
+---------+---------+
```

要求交换相邻座位的两个学生，如果最后一个座位是奇数，那么不交换这个座位上的学生。

```html
+---------+---------+
|    id   | student |
+---------+---------+
|    1    | Doris   |
|    2    | Abbot   |
|    3    | Green   |
|    4    | Emerson |
|    5    | Jeames  |
+---------+---------+
```

### Solution

使用多个 union。

```sql
## 处理偶数 id，让 id 减 1
## 例如 2,4,6,... 变成 1,3,5,...
SELECT
    s1.id - 1 AS id,
    s1.student
FROM
    seat s1
WHERE
    s1.id MOD 2 = 0 UNION
## 处理奇数 id，让 id 加 1。但是如果最大的 id 为奇数，则不做处理
## 例如 1,3,5,... 变成 2,4,6,...
SELECT
    s2.id + 1 AS id,
    s2.student
FROM
    seat s2
WHERE
    s2.id MOD 2 = 1
    AND s2.id != ( SELECT max( s3.id ) FROM seat s3 ) UNION
## 如果最大的 id 为奇数，单独取出这个数
SELECT
    s4.id AS id,
    s4.student
FROM
    seat s4
WHERE
    s4.id MOD 2 = 1
    AND s4.id = ( SELECT max( s5.id ) FROM seat s5 )
ORDER BY
    id;
```

## 627. Swap Salary

https://leetcode.com/problems/swap-salary/description/

Write a solution to swap all 'f' and 'm' values (i.e., change all 'f' values to 'm' and vice versa) with a single update statement and no intermediate temporary tables.

#### Input:
```
| id | name | sex | salary |
|----|------|-----|--------|
| 1  | A    | m   | 2500   |
| 2  | B    | f   | 1500   |
| 3  | C    | m   | 5500   |
| 4  | D    | f   | 500    |
```

#### Output:
```
| id | name | sex | salary |
|----|------|-----|--------|
| 1  | A    | f   | 2500   |
| 2  | B    | m   | 1500   |
| 3  | C    | f   | 5500   |
| 4  | D    | m   | 500    |
```

#### Solution:
```sql
UPDATE Salary
SET sex = CASE 
             WHEN sex = 'm' THEN 'f'
             ELSE 'm'
          END;
```

## 196. Delete Duplicate Emails

https://leetcode.com/problems/delete-duplicate-emails/description/

Write a solution to delete all duplicate emails, keeping only one unique email with the smallest id.

#### Input:
```
+----+---------+
| Id | Email   |
+----+---------+
| 1  | john@example.com |
| 2  | bob@example.com |
| 3  | john@example.com |
+----+---------+
```

#### Output:
```
+----+------------------+
| Id | Email            |
+----+------------------+
| 1  | john@example.com |
| 2  | bob@example.com  |
+----+------------------+
```

#### Solution:
```sql
DELETE p1
FROM
    Person p1,
    Person p2
WHERE
    p1.Email = p2.Email
    AND p1.Id > p2.Id
```
