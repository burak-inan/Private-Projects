# RWU Online Library

**Author:**  
_Burak Inan_   
_burakinan.dev@gmail.com_
---

The Library Management System is a Spring Boot application developed using a functional programming style. It provides a RESTful API for managing books, members, and borrowing transactions in a library. The project uses PostgreSQL as the backend database.
It checks the database every day thanks to a scheduled method. Marks the top 10% of the most rented resources in the last 30 days as popular. It also takes back expired resources from members.

## Technologies Used
- Java 11
- Spring Boot
- Spring Data JPA
- Spring Security (Jwt token)
- PostgreSQL
- Swagger API
- Docker


## API Documentation
The Library Management System provides the following RESTful APIs:

### Swagger UI:

http://localhost:8440/swagger-ui.html


### Books API:

- GET http://localhost:8440/api/book/getAllBooks - Retrieve all books.
- GET http://localhost:8440/api/book/getBookById/{bookId} - Retrieve a specific book by ID.
- GET http://localhost:8440/api/book/getAllBooksWithSearchTermByPage - Retrieve all books with search term. Search for bookName, authorName and description
- GET http://localhost:8440/api/book/getAllBooksWithGenresByPage - Retrieve all books which includes specified genres
- GET http://localhost:8440/api/book/getAllBooksByPage - Retrieve all books by page
- GET http://localhost:8440/api/book/getAllPopularBooks - Retrieve all books by popularity status as list
- POST http://localhost:8440/api/book/saveBook - Create a new book.
- POST http://localhost:8440/api/book/saveBookList - Persist book list.
- PUT http://localhost:8440/api/book/updateBookById/{bookId} - Update a book by bookId.
- DELETE http://localhost:8440/api/book/deleteBookById/{bookId} - Delete a book by bookId.


### Movie API:

- GET http://localhost:8440/api/movie/getAllMovies - Retrieve all movies.
- GET http://localhost:8440/api/movie/getMovieById/{movieId} - Retrieve a specific movie by ID.
- GET http://localhost:8440/api/movie/getAllMoviesWithSearchTermByPage - Retrieve all movies with search term. Search for movieName, directorName and description
- GET http://localhost:8440/api/movie/getAllMoviesWithGenresByPage - Retrieve all movies which includes specified genres
- GET http://localhost:8440/api/movie/getAllMoviesByPage - Retrieve all movies by page
- GET http://localhost:8440/api/movie/getAllPopularMovies - Retrieve all movies by popularity status as list
- POST http://localhost:8440/api/movie/saveMovie - Create a new movie.
- POST http://localhost:8440/api/movie/saveMovieList - Persist movie list.
- PUT http://localhost:8440/api/movie/updateMovieById/{movieId} - Update a movie by movieId.
- DELETE http://localhost:8440/api/movie/deleteMovieById/{movieId} - Delete a movie by movieId.


### Checkin API:

- GET http://localhost:8440/api/checkin/getAllCheckinsByPage - Retrieve all checkins by page.
- GET http://localhost:8440/api/checkin/getAllCheckedOutsByPage/{movieId} - Retrieve all checked outs (records of not returned items) by page.
- GET http://localhost:8440/api/checkin/borrowBookById/{bookId} - Borrow a book by bookId (limited to 3 per member)
- GET http://localhost:8440/api/checkin/borrowMovieById/{movieId} - Borrow a movie by movieId (limited to 3 per member)
- GET http://localhost:8440/api/checkin/returnBookToLibraryById - Return a book to library by bookId
- GET http://localhost:8440/api/checkin/returnMovieToLibraryById - Return a movie to library by movieId
- GET http://localhost:8440/api/checkin/getLiveCheckinsOfMember - Retrieve current checkin records of logged in member
- GET http://localhost:8440/api/checkin/getHistoricalCheckinsOfMemberByPage - Retrieve old checkin records of logged in member
- GET http://localhost:8440/api/checkin/getReadBooksOfMemberByPage/{movieId} - Retrieve checkin records of read book of logged in member by page
- GET http://localhost:8440/api/checkin/getWatchedMoviesOfMemberByPage/{movieId} - Retrieve checkin records of watched movies of logged in member by page


### Checkin API:

- POST http://localhost:8440/api/contactMessage/saveContactMessage - Save a contact message.
- GET http://localhost:8440/api/contactMessage/getInboxWithMemberIdByPage/{memberId} - Retrieve all messages received by the logged in member by memberId
- GET http://localhost:8440/api/contactMessage/getOutboxWithMemberIdByPage/{memberId} - Retrieve all messages has been sent by the logged in member by memberId
- GET http://localhost:8440/api/contactMessage/getAllContactMessagesWithStatusByPage - Retrieve all messages by specified status (COMPLETED/PENDING) by page
- GET http://localhost:8440/api/contactMessage/getAllContactMessagesByPage - Retrieve all messages by page
- GET http://localhost:8440/api/contactMessage/getContactMessagesByEmail - Retrieve all messages by email as page
- GET http://localhost:8440/api/contactMessage/getContactMessagesBySubject - Retrieve all messages by message subject as page
- DELETE http://localhost:8440/api/contactMessage/deleteContactMessageById/{contactMessageId} - Delete a contact message by contactMessageId
- PUT http://localhost:8440/api/contactMessage/replyContactMessageById/{contactMessageId} - Reply a contact message by contactMessageId (Updates status of sent message and create a response message to the member)
- DELETE http://localhost:8440/api/contactMessage/getAllContactMessagesByList - Retrieve all messages by list


### Genre API:

- GET http://localhost:8440/api/genre/getAllGenres - Retrieve all contact message by list 


### User API:

- GET http://localhost:8440/api/user/me - Retrieve logged in user


### Admin API:

- GET http://localhost:8440/api/admin/getAllAdmins - Retrieve all admins by list.
- GET http://localhost:8440/api/admin/getAdminById/{id} - Retrieve a specific admin by ID.
- POST http://localhost:8440/api/admin/saveAdmin - Create a new admin.
- PUT http://localhost:8440/api/admin/updateAdminById/{id} - Update a admin by id.
- DELETE http://localhost:8440/api/admin/deleteAdminById/{id} - Delete a admin by id.


### Members API:

- GET http://localhost:8440/api/member/getMemberById/{id} - Retrieve a specific member by ID.
- GET http://localhost:8440/api/member/getAllMembers - Retrieve all members by list.
- GET http://localhost:8440/api/member/getAllMembersByPage - Retrieve all members by page.
- POST http://localhost:8440/api/member/saveMember - Create a new member.
- DELETE http://localhost:8440/api/member/deleteMemberById/{id} - Delete a member by Id.
- PUT http://localhost:8440/api/member/updateMemberById/{id} - Update a member by Id.
- GET http://localhost:8440/api/member/getMemberWithLiveItems - Retrieve a member with not returned resources.
- GET http://localhost:8440/api/member/getMemberWithHistoricalItems - Retrieve a member with historical resources.
- POST http://localhost:8440/api/member/saveMemberList - Persist member list.
