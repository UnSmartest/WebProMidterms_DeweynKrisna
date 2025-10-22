# Changes Made From Laravel Template

## .env
make sure your XAMPP is open
make sure Apache and MySQL is on then click admin MySQL
create new database "libraryManagement" if you dont have it yet
code in .env found in line 25-30
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=libraryManagement
DB_USERNAME=root
DB_PASSWORD=

<br><br>

## database/migrations/0001_01_01_000000_create_authors_and_books_table.php
Edited the functions to suit our database

authors(
int id PK
string[50] name
int booksPublished
)

books(
int id PK
int authors.id FK
string[50] name
date releaseDate
string[50] genre
int pages
)

run "php artisan migrate" when you're done (MAKE SURE MYSQL IS OPEN‼)
and you can refresh to see that your libraryManagement database has been set up

<br><br>

## app/Models/Author.php
app/Models/Book.php
using HasFactory
declaring our protected variables(depending on each table(model)
then their relationship("belongsTo" or "hasMany")
