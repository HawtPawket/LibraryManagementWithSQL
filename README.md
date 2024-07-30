Welcome to the Library Management System with MySQL!

To use with MySQL use this to create your database. 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
CREATE DATABASE library_management_db;

CREATE TABLE Authors(
	id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    biography TEXT
);
CREATE TABLE Genres(
	id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    description TEXT);
    
CREATE Table Users(
	id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    library_id VARCHAR(10) NOT NULL UNIQUE);
    
CREATE table Books (
	id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author_id INT,
    genre_id INT,
    isbn VARCHAR(13) NOT NULL,
    publication_date DATE,
    availability BOOLEAN DEFAULT 1,
    FOREIGN KEY (author_id) REFERENCES Authors (id),
    FOREIGN KEY (genre_id) REFERENCES Genres (id));

CREATE TABLE Borrowed_books (
	id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT, 
    book_id INT,
    borrow_date DATE NOT NULL,
    return_date DATE,
    FOREIGN KEY (user_id) REFERENCES Users(id),
    FOREIGN KEY (book_id) REFERENCES Books(id)
    );
    

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

To connect to your library database in MySQL please change the password in the "connect_sql.py" file 


Simply run the LibraryManagement.py file

choose options between 1-5

Option 1:
 Will bring up the book operations where you can add books, borrow books, return books, search for a book or display all books.

 Option 2:
 Will bring up the User operations where you can add new users, veiw user details or display all users.

 Option 3:
 Will bring up the Authors Operations where you can add new autors, veiw author details or display all authors.

 Option 4:
 Will bring up the Genre Operations where you can add new genres, veiw genre details or display all genres.

 Option 5:
 This option will exit the program.

 Thanks for using my Library Management System!