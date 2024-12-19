## OOP Mini Project

Apply Object-Oriented Programming (OOP) principles in Python to develop an advanced *Library Management System.* This command-line-based application is designed to streamline the management of books and resources within a library.

#### What are the requirements? :memo: 

*enhanced user interface (ui) and menu*
*class structure*
*encapsulation*
*modules*
*user interactions*
*error handling*

#### What are the expectations of this program? :white_check_mark:
Create a robust system that allows users to browse, borrow, return, and explore a collection of books while demonstrating your proficiency in OOP principles and the use of modules.

#### Extensions needed: :inbox_tray:
*python*
*python debugger*
*markdown checkboxes*

#### Resources used: :mag:
[GeeksforGeeks](https://www.geeksforgeeks.org/encapsulation-in-python/#encapsulation-in-python)
[Python.org](https://docs.python.org/3/tutorial/modules.html)
[W3School](https://www.w3schools.com/python/python_regex.asp)


### Programming steps:

***Enhanced User Interface (UI) and Menu*** :handshake:	
Create an improved, user-friendly command-line interface (CLI) for the Library Management System with separate menus for each class of the system.

``` Menus:

    def display_main_menu(self):
        print("\nWelcome to the Library Management System!")
        print("Main Menu:")
        print("1. Book Operations")
        print("2. User Operations")
        print("3. Author Operations")
        print("4. Quit")

    def book_operations_menu(self):
        print("\nBook Operations:")
        print("1. Add a new book")
        print("2. Borrow a book")
        print("3. Return a book")
        print("4. Search for a book")
        print("5. Display all books")
        print("6. Quit")

    def user_operations_menu(self):
        print("\nUser Operations:")
        print("1. Add a new user")
        print("2. View user details")
        print("3. Display all users")
        print("4. Quit")

    def author_operations_menu(self):
        print("\nAuthor Operations:")
        print("1. Add a new author")
        print("2. View author details")
        print("3. Display all authors")
        print("4. Quit")

```


***class structure*** :card_index_dividers: 
Implement a class structure that represents key entities in the library management system, including:
Book: A class representing individual books with attributes such as title, author,  genre, publication date, and availability status.
User: A class to represent library users with attributes like name, library ID, and a list of borrowed book titles.
Author: A class representing book authors with attributes like name and biography. 
``` 
Example:

class Author:
    def __init__(self, name, biography):
        self.__name = name
        self.__biography = biography
    
#getters n setters
    def get_name(self):
        return self.__name
    
    def get_favcolor(self):
        return self.__favcolor
    
    def display_details(self):
        return f"Author: {self.__name}, Biography: {self.get_favcolor}"

```


***Encapsulation***	:lock_with_ink_pen:
Apply encapsulation principles by defining private attributes and using getters and setters for necessary data access.

```encapsulation
class Book:
    def __init__(self, title, author, genre, publication_date):
        self.__title = title
        self.__author = author
        self.__genre = genre
        self.__publication_date = publication_date
        self.__availability = True 
    
#getters n setters
    def get_title(self):
        return self.__title
    
    def set_title(self, title):
        self.__title = title
```

***Menu Actions*** :open_book:
Implement the following actions in response to menu selections using the classes you've created

Example of menu actions:
``` examples of my menu option defs

 def add_user(self):
        name = input("Enter user name: ")
        library_id = input("Enter library ID: ")
        new_user = User(name, library_id)
        self.users.append(new_user)
        print("User added successfully!")

    def view_user_details(self):
        library_id = input("Enter user library ID: ")
        user = next((u for u in self.users if u.get_library_id() == library_id), None)
        if user:
            print(user.display_details())
        else:
            print("User not found.")

    def display_users(self):
        for user in self.users:
            print(user.display_details())

    def add_author(self):
        name = input("Enter author name: ")
        fav_color = input("Provide author's favorite color: ")
        new_author = Author(name,fav_color)
        self.authors.append(new_author)
        print("Author added successfully!")


```
***User Interaction*** :bust_in_silhouette:
The program must utlize input() to enable users to select menu options and provide contact details. Use regular expressions (regex) to ensure correct formatting of of contact information.  

Example of inputs and regex:
``` inputs and regex

Inputs:
    def search_book(self):
        title = input("Please provide title: ")
        book = next((b for b in self.books if b.get_title() == title), None)
        if book:
            print(book.display_details())
        else:
            print("Book not found.")

    def display_books(self):
        for book in self.books:
            print(book.display_details())

Regex:
    def validate_library_id(self, library_id):
        return bool(re.match(r'^\d{6}', library_id))
    
    def validate_name(self, name):
        return bool(re.match(r'^[A-Za-z0-9]+$', name))

    def validate_book_id(self, title):
        return bool(re.match(r'^[A-Za-z0-9\s\.,!?\'":;()&-]{1, 100}$', title))
    
    def validate_author(self, name):
        return bool(re.match(r'^[A-Za-z\s]+$', name))

```
***Error Handling*** 	:warning:
Implement error handling where applicable using try, except, else, and finally blocks to manage potential issues gracefully, such as incorrect user input or file operations. 

Example of error handling:
``` try, except, finally blocks

try:
    title = input("Enter book title: ")
    while not self.validate_book(title):
        print("Invalid title, please try again!")
except Exception as e:
    print(f"Error: {e}, unable to add book! ")
finally:
    print("You have completed the process of adding a book!")
```

#### Where can I find the program?
[OOP Library Management System](https://github.com/brittmarie333/OOP-mini-project.git) :computer:
