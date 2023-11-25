# RWU Online Library
- The Library Management System is a Spring Boot application developed using a functional programming style. 
- It provides a RESTful API for managing books, members, and borrowing transactions in a library. 
- The project uses PostgreSQL as the backend database.
- It checks the database every day thanks to a scheduled method. Marks the top 10% of the most rented resources in the last 30 days as popular. Also takes back expired resources from members.

## Technologies Used
- Java 11
- Spring Boot
- Spring Data JPA
- Spring Security (Jwt token)
- PostgreSQL
- Swagger API
- Docker
- Getting Started
- To run the Library Management System locally, follow these steps:

## bash
### Copy code
- ./mvnw spring-boot:run
- The application should now be running at http://localhost:8440.


## API Documentation
The Library Management System provides the following RESTful APIs:

### Swagger UI:

http://localhost:8440/swagger-ui.html


### Books API:

- GET /api/book/getAllBooks - Retrieve all books.
- GET /api/book/getBookById/{bookId} - Retrieve a specific book by ID.
- GET /api/book/getAllBooksWithSearchTermByPage - Retrieve all books with search term. Search for bookName, authorName and description
- GET /api/book/getAllBooksWithGenresByPage - Retrieve all books which includes specified genres
- GET /api/book/getAllBooksByPage - Retrieve all books by page
- GET /api/book/getAllPopularBooks - Retrieve all books by popularity status as list
- POST /api/book/saveBook - Create a new book.
- POST /api/book/saveBookList - Persist book list.
- PUT /api/book/updateBookById/{bookId} - Update a book by bookId.
- DELETE /api/book/deleteBookById/{bookId} - Delete a book by bookId.


### Movie API:

- GET /api/movie/getAllMovies - Retrieve all movies.
- GET /api/movie/getMovieById/{movieId} - Retrieve a specific movie by ID.
- GET /api/movie/getAllMoviesWithSearchTermByPage - Retrieve all movies with search term. Search for movieName, directorName and description
- GET /api/movie/getAllMoviesWithGenresByPage - Retrieve all movies which includes specified genres
- GET /api/movie/getAllMoviesByPage - Retrieve all movies by page
- GET /api/movie/getAllPopularMovies - Retrieve all movies by popularity status as list
- POST /api/movie/saveMovie - Create a new movie.
- POST /api/movie/saveMovieList - Persist movie list.
- PUT /api/movie/updateMovieById/{movieId} - Update a movie by movieId.
- DELETE /api/movie/deleteMovieById/{movieId} - Delete a movie by movieId.


### Checkin API:

- GET /api/checkin/getAllCheckinsByPage - Retrieve all checkins by page.
- GET /api/checkin/getAllCheckedOutsByPage/{movieId} - Retrieve all checked outs (records of not returned items) by page.
- GET /api/checkin/borrowBookById/{bookId} - Borrow a book by bookId (limited to 3 per member)
- GET /api/checkin/borrowMovieById/{movieId} - Borrow a movie by movieId (limited to 3 per member)
- GET /api/checkin/returnBookToLibraryById - Return a book to library by bookId
- GET /api/checkin/returnMovieToLibraryById - Return a movie to library by movieId
- GET /api/checkin/getLiveCheckinsOfMember - Retrieve current checkin records of logged in member
- GET /api/checkin/getHistoricalCheckinsOfMemberByPage - Retrieve old checkin records of logged in member
- GET /api/checkin/getReadBooksOfMemberByPage/{movieId} - Retrieve checkin records of read book of logged in member by page
- GET /api/checkin/getWatchedMoviesOfMemberByPage/{movieId} - Retrieve checkin records of watched movies of logged in member by page


### Checkin API:

- POST /api/contactMessage/saveContactMessage - Save a contact message.
- GET /api/contactMessage/getInboxWithMemberIdByPage/{memberId} - Retrieve all messages received by the logged in member by memberId
- GET /api/contactMessage/getOutboxWithMemberIdByPage/{memberId} - Retrieve all messages has been sent by the logged in member by memberId
- GET /api/contactMessage/getAllContactMessagesWithStatusByPage - Retrieve all messages by specified status (COMPLETED/PENDING) by page
- GET /api/contactMessage/getAllContactMessagesByPage - Retrieve all messages by page
- GET /api/contactMessage/getContactMessagesByEmail - Retrieve all messages by email as page
- GET /api/contactMessage/getContactMessagesBySubject - Retrieve all messages by message subject as page
- DELETE /api/contactMessage/deleteContactMessageById/{contactMessageId} - Delete a contact message by contactMessageId
- PUT /api/contactMessage/replyContactMessageById/{contactMessageId} - Reply a contact message by contactMessageId (Updates status of sent message and create a response message to the member)
- DELETE /api/contactMessage/getAllContactMessagesByList - Retrieve all messages by list


### Genre API:

- GET /api/genre/getAllGenres - Retrieve all contact message by list 


### User API:

- GET /api/user/me - Retrieve logged in user


### Admin API:

- GET /api/admin/getAllAdmins - Retrieve all admins by list.
- GET /api/admin/getAdminById/{id} - Retrieve a specific admin by ID.
- POST /api/admin/saveAdmin - Create a new admin.
- PUT /api/admin/updateAdminById/{id} - Update a admin by id.
- DELETE /api/admin/deleteAdminById/{id} - Delete a admin by id.


### Members API:

- GET /api/member/getMemberById/{id} - Retrieve a specific member by ID.
- GET /api/member/getAllMembers - Retrieve all members by list.
- GET /api/member/getAllMembersByPage - Retrieve all members by page.
- POST /api/member/saveMember - Create a new member.
- DELETE /api/member/deleteMemberById/{id} - Delete a member by Id.
- PUT /api/member/updateMemberById/{id} - Update a member by Id.
- GET /api/member/getMemberWithLiveItems - Retrieve a member with not returned resources.
- GET /api/member/getMemberWithHistoricalItems - Retrieve a member with historical resources.
- POST /api/member/saveMemberList - Persist member list.
