# Assume there are the following tables in the MySQL database.

```sql
SELECT * FROM teams;
+---------+-----------+
| team_id | team_name |
+---------+-----------+
|       1 | Team A    |
|       2 | Team K    |
|       3 | Team B    |
+---------+-----------+
```
```sql
SELECT * FROM members;
+-----------+--------------------+---------+
| member_id | member_name        | team_id |
+-----------+--------------------+---------+
|         1 | Suzuki Ichiro      |       1 |
|         2 | Naito Tetsuya      |       1 |
|         3 | Yamamoto Sayaka    |       2 |
|         4 | Kawaguchi Yasunobu |       3 |
|         5 | Matsui Jurina      |       1 |
|         6 | Rakuten Taro       |       3 |
|         7 | Honda Keisuke      |       3 |
|         8 | Oyobe Takao        |       2 |
|         9 | Maeda Atsuko       |       1 |
|        10 | Kojima Haruna      |       2 |
+-----------+--------------------+---------+
```

<details>
<summary>if you will create database, please confirm the following</summary>

### 1. Create database

```sql 
CREATE DATABASE rnewgradstest;
```

### 2. Create tables

```sql 
CREATE TABLE rnewgradstest.members (
  member_id int,
  member_name varchar(100),
  team_id int
);
```
```sql 
CREATE TABLE rnewgradstest.teams (
  team_id int,
  team_name varchar(100)
);
```

### 3. Insert data

```sql
INSERT INTO rnewgradstest.members (member_id, member_name, team_id)
 VALUES ('1', 'Suzuki Ichiro', '1'),
        ('2', 'Naito Tetsuya', '1'),
        ('3', 'Yamamoto Sayaka', '2'),
        ('4', 'Kawaguchi Yasunobu', '3'),
        ('5', 'Matsui Jurina', '1'),
        ('6', 'Rakuten Taro', '3'),
        ('7', 'Honda Keisuke', '3'),
        ('8', 'Oyobe Takao', '2'),
        ('9', 'Maeda Atsuko', '1'),
        ('10', 'Kojima Haruna', '2');
```
```sql 
INSERT INTO rnewgradstest.teams (team_id, team_name)
  VALUES ('1', 'Team A'),
         ('2', 'Team K'),
         ('3', 'Team B');
```
</details>

- - -

## Q11 : Now, you want to see each member's name of "Team K". Write an SQL query to meet the requirement, like below.

```sql 
+-----------------+
| member_name     |
+-----------------+
| Yamamoto Sayaka |
| Oyobe Takao     |
| Kojima Haruna   |
+-----------------+
```

## Q12 : Now, you want to see a list of member_name and team_name. Write an SQL query to meet the requirement, like below.

```sql 
+--------------------+-----------+
| member_name        | team_name |
+--------------------+-----------+
| Maeda Atsuko       | Team A    |
| Suzuki Ichiro      | Team A    |
| Naito Tetsuya      | Team A    |
| Matsui Jurina      | Team A    |
| Rakuten Taro       | Team B    |
| Kawaguchi Yasunobu | Team B    |
| Honda Keisuke      | Team B    |
| Kojima Haruna      | Team K    |
| Oyobe Takao        | Team K    |
| Yamamoto Sayaka    | Team K    |
+--------------------+-----------+
```
