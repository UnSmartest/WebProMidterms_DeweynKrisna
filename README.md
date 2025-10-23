# Krisna's changes on 20:28, 22 Oct 2025

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

<br>

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

<br>

## app/Models/Author.php & app/Models/Book.php
Using hasFactory, dunno what that means. Lots of changes. Basically we declare our protected variables and their relationship with other tables with "belongsTo" or "hasMany". Copy the code provided. There should be only these two files beneat app/Models.

<br><br>

# Krisna's changes on 06:21, 23 Oct 2025

## app/Models/Users.php
Just a simple one for a "simple" project. Basically just create the table for Users.

<br>

## database/migrations/0001_01_01_000000_create_authors_and_books_and_users_table.php
Renamed file to include users. Added the users table.

<br>

## database/seeders/DatabaseSeeder.php
Since our website probably won't be made, at the very least we can include some preset data.

**authors**
| id | name | booksPublished |
| -------- | ---- | ---- |
| 1 | raynArdian | 1 |
| 2 | stereotypicalAddress | 2 |

**books**
| id | authorID | name | releaseDate | genre | pages |
| -- | -------- | ---- | ----------- | ----- | ----- |
| 1 | 1 | How to Not Commit Suicide | 1997-02-19 | Self-Improvement | 67 |
| 2 | 2 | 99 Recipes | 2004-12-31 | Cooking | 24 |
| 3 | 2 | 99 Ways to Extinguish a Fire in Your Home | 26-02-2005 | Self-Improvement | 121 |

**users**
| id | name | email | password |
| -- | ---- | ----- | -------- |
| 1 | dewdewdew | dsutjiadi@somecompany.com | 06_01_2004 |
| 2 | unsmartest | iluvc4ts@somecompany.com | 09_09_2006 |

<br>

## app/Models/Book.php
Changed 'author_id' into 'authorID'.

## How to Connect DatabaseSeeder into mySQL
php artisan migrate:fresh --seed
Remember to make sure your MySQL and Apache is turned on (via XAMPP Control Panel).
