# Login

1. 创建数据库
2. 创建表
3. 查询表
4. 表中插入数据
5. 表中删除数据
6. 表中修改数据

##### 语法

##### 一.创建数据库

```
CREATE DATABASE database_name
```

我们创建了一个名为 "my_db" 的数据库：

```
<?php
$con = mysql_connect("localhost","peter","abc123");
if (!$con)
  {
  die('Could not connect: ' . mysql_error());
  }

if (mysql_query("CREATE DATABASE my_db",$con))
  {
  echo "Database created";
  }
else
  {
  echo "Error creating database: " . mysql_error();
  }

mysql_close($con);
?>
```

##### 二.创建表

##### 语法

```
CREATE TABLE table_name
(
column_name1 data_type,
column_name2 data_type,
column_name3 data_type,
.......
)
```

如何创建一个名为 "Persons" 的表

```
<?php
$con = mysql_connect("localhost","peter","abc123");
if (!$con)
  {
  die('Could not connect: ' . mysql_error());
  }

// Create database
if (mysql_query("CREATE DATABASE my_db",$con))
  {
  echo "Database created";
  }
else
  {
  echo "Error creating database: " . mysql_error();
  }

// Create table in my_db database
mysql_select_db("my_db", $con);
$sql = "CREATE TABLE Persons 
(
FirstName varchar(15),
LastName varchar(15),
Age int
)";
mysql_query($sql,$con);

mysql_close($con);
?>
```

##### 三.查询表

SELECT *  FROM table_name

```
$mysql_mylink = mysql_connect($mysql_host, $mysql_user, $mysql_pass);

mysql_query("SET NAMES 'GBK'");

```

四.表中插入数据

##### 语法

```
INSERT INTO table_name
VALUES (value1, value2,....)
```

```
<?php
$con = mysql_connect("localhost","peter","abc123");
if (!$con)
  {
  die('Could not connect: ' . mysql_error());
  }

mysql_select_db("my_db", $con);

mysql_query("INSERT INTO Persons (FirstName, LastName, Age) 
VALUES ('Peter', 'Griffin', '35')");

mysql_query("INSERT INTO Persons (FirstName, LastName, Age) 
VALUES ('Glenn', 'Quagmire', '33')");

mysql_close($con);
?>
```

##### 五.表中删除数据

##### 语法

````
 $SQL="delete fromjb51` where id in (1,2,4)"; 
````

##### 六.表中修改数据

##### 语法

```
UPDATE USER SET NAME="更新后的名字",AGE=55,SEX="女" WHERE ID=20
* UPDATE 表名 SET 更改后字段="更改后字段的值" WHERE 更改前字段="更改前字段的值"
```

