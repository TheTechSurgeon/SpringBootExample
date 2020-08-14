# The Bookstore
 **a Demo Java Spring REST API Application**.


This is a basic bookstore database scheme with books which have authors. The book can be found in a section of the store.


### MVP


- Auditing fields
- Exception Handling
- User Oauth2 Authentication
  - Endpoints to handle 
    - Creating a new user
    - Updating a user
    - Deleting a user
    - Authenticated user logging out
    - plus many more!
- Swagger
- Unit / Integration testing (at least the POM file entries)
- Deployment to Heroku
- Conversion to Postgresql

-  Created the models, repositories, and services needed to model the following table layout:


-  section
  - `sectionid` - long primary key
  - `sectionname` - String the name of section. Cannot be null. Must be unique
  
- book
  - `bookid` - long primary key
  - `booktitle` - String the title of the book. Cannot be null.
  - `ISBN` - String the ISBN number of the book. Cannot be null. Must be unique
  - `copy` - Int the year the book was published (copyright date)
  
- authors
  - `authorid` - long primary key
  - `lastname` - String last name of the author
  - `firstname` - String first name of the author

- There is a many to many relationship between authors and books. A book may have many authors while an author may write many books.

- The is a one to many relationship between sections and books. One section can hold many books while a book can only be in one section.

- added  four standard auditing fields to all tables 


- Exposed the following endpoints
  - List the data
    - GET /books/books - returns a JSON object list of all the books, their section, and their authors.
    - GET /authors/authors - returns a JSON object list of all the authors, their books, and the book's section.
  - Manage the data
    - DELETE /data/books/{id} - deletes a book and the book author combinations - but does not delete the author records.

- This system has an AUTH0 2.0 authentication process. 
  - User - people who can look up books, authors, sections
  - Data - people who can look up books, authors, sections 
  - ADMIN - people who can update data on users and otherwise have full access to the system.

- 2 example Unit tests are included for the book service

- 


