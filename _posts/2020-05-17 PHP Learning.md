# PHP
PHP: Hypertext Preprocessor


If you have purchased paid hosting, you may be able to upload your PHP files. 99% hosting companies allow to run PHP on the server. What if we want to test everything locally in our computer? 

If we want to develop quickly and easily on our local machine.  
So what we can do is essencially turn our computer into a web server 

But it is highly unrecommended you allow people to access this web sever, because there will be some security issues. 

what I am showing you is you open up a port on your computer, if you open port 80 on your computer, which is going to allow people to access everything that yo put into your *htdocs* folder.

# XAMPP

XAMPP is a free and open-source cross-platform web server solution stack package developed by Apache Friends, consisting mainly of the Apache HTTP Server, MariaDB database, and interpreters for scripts written in the PHP and Perl programming languages.

It allowes you to compile PHP files in the background server-side. Because PHP is a server-side language. and run them and display the contents of your actions in the browser.

# Download XAMPP for your computer

Free of charge. For Windows, MAC, Linux... 

# MySQL

With MySQL, you gonna use a web application called phpMyAdmin and this is bundled with XAMPP. MySQL is a database managemnt system. 


First thing to do is to test our web server is active.

phpMyAdmin is the administration for your database. You can access via the link on the localhost page. Address is http://localhost:8080/phpmyadmin/



# htdocs
htdocs is the root directory where your files should be 

```php
<?php 

?>
```

similar to html syntax
```html
<html>

</html>
```




# Create First File 

index.php

Typically an Apache installation will take a index.php and a index.html file as default files to be loaded inside a folder.  

It will automatically go to the index.php when you access the folder.

index.php & a index.html are default specified in an Apache configuration. Normal files are not named to open by default.



# PDO - PHP Data Object


## Should I Use MySQLi or PDO?

If you need a short answer, it would be "Whatever you like".

Both MySQLi and PDO have their advantages:

PDO will work on 12 different database systems, whereas MySQLi will only work with MySQL databases.

So, if you have to switch your project to use another database, PDO makes the process easy. You only have to change the connection string and a few queries. With MySQLi, you will need to rewrite the entire code - queries included.

Both are object-oriented, but MySQLi also offers a procedural API.

Both support Prepared Statements. Prepared Statements protect from SQL injection, and are very important for web application security.



## Open a Connection to MySQL
```php
 <?php
$servername = "localhost";
$username = "username";
$password = "password";

try {
  $conn = new PDO("mysql:host=$servername;dbname=myDB", $username, $password);
  // set the PDO error mode to exception
  $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  echo "Connected successfully";
} catch(PDOException $e) {
  echo "Connection failed: " . $e->getMessage();
}
?> 
```

**Note:** In the PDO example above we have also specified a database (myDB). PDO require a valid database to connect to. If no database is specified, an exception is thrown.

**Tip:** A great benefit of PDO is that it has an exception class to handle any problems that may occur in our database queries. If an exception is thrown within the try{ } block, the script stops executing and flows directly to the first catch(){ } block.

## Create a MySQL Database Using PDO

```php
 <?php
$servername = "localhost";
$username = "username";
$password = "password";

try {
  $conn = new PDO("mysql:host=$servername", $username, $password);
  // set the PDO error mode to exception
  $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  $sql = "CREATE DATABASE myDBPDO";
  // use exec() because no results are returned
  $conn->exec($sql);
  echo "Database created successfully<br>";
} catch(PDOException $e) {
  echo $sql . "<br>" . $e->getMessage();
}

$conn = null;
?> 
```

**Tips:** A great benefit of PDO is that it has *exception* class to handle any problems that may occur in our database queries. If an exception is thrown within the try{ } block, the script stops executing and flows directly to the first catch(){ } block. In the catch block above we echo the SQL statement and the generated error message. 



# Create A Table Using PDO
The data type specifies what type of data the column can hold. For a complete reference of all the available data types, go to our Data Types reference.

After the data type, you can specify other optional attributes for each column:

    NOT NULL - Each row must contain a value for that column, null values are not allowed
    DEFAULT value - Set a default value that is added when no other value is passed
    UNSIGNED - Used for number types, limits the stored data to positive numbers and zero
    AUTO INCREMENT - MySQL automatically increases the value of the field by 1 each time a new record is added
    PRIMARY KEY - Used to uniquely identify the rows in a table. The column with PRIMARY KEY setting is often an ID number, and is often used with AUTO_INCREMENT

Each table should have a primary key column (in this case: the "id" column). Its value must be unique for each record in the table.


```php
 <?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "myDBPDO";

try {
  $conn = new PDO("mysql:host=$servername;dbname=$dbname", $username, $password);
  // set the PDO error mode to exception
  $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

  // sql to create table
  $sql = "CREATE TABLE MyGuests (
  id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
  firstname VARCHAR(30) NOT NULL,
  lastname VARCHAR(30) NOT NULL,
  email VARCHAR(50),
  reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
  )";

  // use exec() because no results are returned
  $conn->exec($sql);
  echo "Table MyGuests created successfully";
} catch(PDOException $e) {
  echo $sql . "<br>" . $e->getMessage();
}

$conn = null;
?> 
```
