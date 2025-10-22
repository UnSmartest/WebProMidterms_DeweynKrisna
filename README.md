# Krisna's changes on 20:28, 22 Oct 2025.

## .env
Make sure your XAMPP is open. Make sure Apache and MySQL is on then click 'Admin' of MySQL.
Create new database "libraryManagement" if you dont have it yet.
You can find the new lines of code in line 25-30.
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=libraryManagement
DB_USERNAME=root
DB_PASSWORD=
```

<br><br>

## database/migrations/0001_01_01_000000_create_authors_and_books_table.php
Edited the functions to suit our database. There should only be one php file in database/migrations. Delete the others. The tables and their information is as follows:

**authors**
| Datatype | Name | Note |
| -------- | ---- | ---- |
| int | id | Primary Key |
| str[50] | name | - |
| int | booksPublished | - |

**books**
| Datatype | Name | Note |
| -------- | ---- | ---- |
| int | id | Primary Key |
| int | authors.id | Foreign Key |
| str[50] | name | - |
| date | releaseDate | - |
| str[50] | genre | - |
| int | pages | - |

On the VSCode terminal, run "php artisan migrate" when you're done (MAKE SURE MYSQL IS OPEN‼). And you can refresh to see that your libraryManagement database has been set up.

<br><br>

## app/Models/Author.php & app/Models/Book.php
Using hasFactory, dunno what that means. Lots of changes. Basically we declare our protected variables and their relationship with other tables with "belongsTo" or "hasMany". Copy the code provided. There should be only these two files beneat app/Models.
