# student-management-system-backend-project

**Author:**  
_Burak Inan_   
_burakinan.dev@gmail.com_
---

## Description:
* The Student Management System is a backend project built with Java and Spring technologies. It provides a comprehensive set of RESTful APIs for managing various entities within an educational institution. The system includes functionalities for administrators, advisory teachers, authentication, communication messages, deans, education terms, lessons, lesson programs, meetings, students, student info, teachers, and vice deans.

## Key Features:

* Authentication and Authorization (Admin, Manager, Assistant Manager, Teacher, Student roles)
* CRUD operations for Admins, Advisory Teachers, Deans, Education Terms, Lessons, Lesson Programs, Meetings, Students, Teachers, and Vice Deans
* Communication Messages for system-wide communication
* Term and Final Grades Process with specific rules for course selection and grade calculations

## Technologies Used
- Java 11
- Spring Boot
- Spring Data JPA
- Spring Security (Jwt token)
- PostgreSQL
- Swagger API
- Docker


## API Documentation
The Student Management System provides the following RESTful APIs:

### Swagger UI:

http://localhost:8080/swagger-ui.html

### Using the Admin Service,
You have to be an admin to perform an operation

* Using the  [http://localhost:8080/admin/save](http://localhost:8080/admin/save) , you can save admin 
* Using the  [http://localhost:8080/admin/getAll?email=test@test.com&page=0&size=10&sort="date"&type="desc"](http://localhost:8080/admin/getAll?email=test@test.com&page=0&size=10&sort="date"&type="desc") , you can get all admin by page 
* Using the  [http://localhost:8080/admin/delete/{id}](http://localhost:8080/admin/delete/{id}) , you can delete an admin by id, except built_in admins 

### Using the Advisory Teacher Service,
You have to be an admin, manager or assistant manager to perform an operation
* Using the  [http://localhost:8080/advisorTeacher/getAll](http://localhost:8080/advisorTeacher/getAll) , you get all Advisory Teacher by list 
* Using the  [http://localhost:8080/advisorTeacher/search?email=test@test.com&page=0&size=10&sort="date"&type="desc"](http://localhost:8080/advisorTeacher/search?email=test@test.com&page=0&size=10&sort="date"&type="desc") , you can get all Advisory Teacher by page 
* Using the  [http://localhost:8080/advisorTeacher/delete/{id}](http://localhost:8080/advisorTeacher/delete/{id}) , you can delete an Advisory Teacher by id, except built_in admins

### Using the Auth Service,
* Using the  [http://localhost:8080/auth/login](http://localhost:8080/auth/login) , you can log in by password and username 

### Using the Communication Message Service,
Anyone can send messages to the system and admin also can list all message by email or subject.  
You can send only a message in a day with same email

* Using the  [http://localhost:8080/contactMessages/save](http://localhost:8080/contactMessages/save) , you can send messages without register 

If you are an admin, manager or assistant manager you can perform below operations
* Using the  [http://localhost:8080/contactMessages/getAll?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/contactMessages/getAllByPage?page=0&size=10&sort="date"&type="desc") , If you are an admin, manager or assistant manager you can see all messages by page.
* Using the  [http://localhost:8080/contactMessages/searchByEmail?email=test@test.com&page=0&size=10&sort="date"&type="desc"](http://localhost:8080/contactMessages/searchByEmail?email=test@test.com&page=0&size=10&sort="date"&type="desc") ,  If you are an admin, manager or assistant manager you can see all messages by page for a specific email.
* Using the  [http://localhost:8080/contactMessages/searchBySubject?subject=test@test.com&page=0&size=10&sort="date"&type="desc"](http://localhost:8080/contactMessages/searchBySubject?subject=test@test.com&page=0&size=10&sort="date"&type="desc") , If you are an admin, manager or assistant manager you can see all messages by page for a specific subject.
* Using the  [http://localhost:8080/contactMessages/delete/{id}](http://localhost:8080/contactMessages/delete/{id}) , if you are admin, manager or assistant manager you can delete a message with an id 
* Using the  [http://localhost:8080/contactMessages/update/{id}](http://localhost:8080/contactMessages/update/{id}) , if you are admin, manager or assistant manager you can update a message with an id 

### Using the Dean Service,
You have to be an admin or manager to perform an operation

* Using the  [http://localhost:8080/dean/save](http://localhost:8080/dean/save) , you can create a dean
* Using the  [http://localhost:8080/dean/delete/{deanId}]http://localhost:8080/dean/delete/{deanId}) , you can delete a dean with an id
* Using the  [http://localhost:8080/dean/deleteUsingParam?deanId=""](http://localhost:8080/dean/deleteUsingParam?deanId=""}) , you can delete a dean by using an id as request parameter 
* Using the  [http://localhost:8080/dean/getManagerById/{deanId}](http://localhost:8080/dean/getManagerById/{deanId}) , you can get a dean by using an id as request parameter
* Using the  [http://localhost:8080/dean/getManagerByIdUsingParam?deanId=""}](http://localhost:8080/dean/getManagerById?deanId="") , you can get a dean by an id
* Using the  [http://localhost:8080/dean/getAll](http://localhost:8080/dean/getAll) , you can get all deans as list.
* Using the  [http://localhost:8080/dean/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/dean/search?page=0&size=10&sort="date"&type="desc") , you can get all deans by page.

### Using the Education Term Service,
If you are a assistant manager or teacher you can perform below operations
* Using the  [http://localhost:8080/educationTerms/getAll](http://localhost:8080/educationTerms/getAll) , you can get all education terms as list.
* Using the  [http://localhost:8080/educationTerms/{id}](http://localhost:8080/educationTerms/{id}) , you can get an education terms by an id
* Using the  [http://localhost:8080/educationTerms/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/educationTerms/search?page=0&size=10&sort="date"&type="desc") , you can get all educationTerms by page.
* Using the  [http://localhost:8080/educationTerms/delete/{id}](http://localhost:8080/educationTerms/delete/{id}) , you can delete an education term by an id
* Using the  [http://localhost:8080/educationTerms/update/{id}](http://localhost:8080/educationTerms/update/{id}) , you can update an education term by an id
* Using the  [http://localhost:8080/educationTerms/getAllAfterThisDate?date=""&page=0&size=10&sort="date"&type="desc"](http://localhost:8080/educationTerms/getAllAfterThisDate?date=""&page=0&size=10&sort="date"&type="desc"}) , you can get all education terms after the specified date by using a date as request parameter

If you are admin or manager you can also perform the below operation
* Using the  [http://localhost:8080/educationTerms/save](http://localhost:8080/educationTerms/save) , you can create an education term

### Using the Lesson Service,
If you are admin ,manager or assistant manager you can perform all operations
* Using the  [http://localhost:8080/lessons/save](http://localhost:8080/lessons/save) , you can create an lessons
* Using the  [http://localhost:8080/lessons/delete/{id}](http://localhost:8080/lessons/delete/{id}) , you can delete a lesson by an id
* Using the  [http://localhost:8080/lessons/getLessonByName?lessonName=""](http://localhost:8080/lessons/getLessonByName?lessonName="") , you can get a lesson by using lesson name as request parameter.
* Using the  [http://localhost:8080/lessons/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/lessons/search?page=0&size=10&sort="date"&type="desc") , you can get all lessons by page.
* Using the  [http://localhost:8080/lessons/getAllLessonByLessonId?lessonId=""&lessonId=""](http://localhost:8080/lessons/getAllLessonByLessonId?lessonId=""&lessonId="") , you can all matched lessons by given id set

If you are a teacher you can only perform the below operation
* Using the  [http://localhost:8080/lessons/update/{id}](http://localhost:8080/lessons/update/{id}) , you can update a lesson by an id

### Using the Lesson Program Service,
If you are admin ,manager or assistant manager you can perform all operations
* Using the  [http://localhost:8080/lessonPrograms/save](http://localhost:8080/lessonPrograms/save) , you can create an lesson program
* Using the  [http://localhost:8080/lessonPrograms/getAll](http://localhost:8080/lessonPrograms/getAll) , you can get all lesson programs as list
* Using the  [http://localhost:8080/lessonPrograms/getById/{id}](http://localhost:8080/lessonPrograms/getById/{id}) , you can get a lesson program by an id
* Using the  [http://localhost:8080/lessonPrograms/delete/{id}](http://localhost:8080/lessonPrograms/delete/{id}) , you can delete a lesson program by an id

If you are student or teacher you can perform the below operations
* Using the  [http://localhost:8080/lessonPrograms/getAllAssigned](http://localhost:8080/lessonPrograms/getAllAssigned) , you can get all assigned lesson programs as list
* Using the  [http://localhost:8080/lessonPrograms/getAllUnassigned](http://localhost:8080/lessonPrograms/getAllUnassigned) , you can get all un assigned lesson programs as list
* Using the  [http://localhost:8080/lessonPrograms/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/lessonPrograms/search?page=0&size=10&sort="date"&type="desc") , you can get all lesson programs by page.
* Using the  [http://localhost:8080/lessonPrograms/getAllLessonProgramByTeacher](http://localhost:8080/lessonPrograms/getAllLessonProgramByTeacher) , you can get a lesson program of a teacher by using teacher's username as header parameter.

### Using the Meet Service,

* Using the  [http://localhost:8080/meet/save](http://localhost:8080/meet/save) , if you are teacher you can create a meet by specifying teacher's username as header parameter
* Using the  [http://localhost:8080/meet/getAll](http://localhost:8080/meet/getAll) , if you are admin you can get all meets as list
* Using the  [http://localhost:8080/meet/getMeetById/{meetId}](http://localhost:8080/meet/getMeetById/{meetId}) , if you are admin you can get a meet by a meet id
* Using the  [http://localhost:8080/meet/delete/{meetId}](http://localhost:8080/meet/delete/{meetId}) , if you are admin or teacher you can delete a meet by meet id
* Using the  [http://localhost:8080/meet/update/{meetId}](http://localhost:8080/meet/update/{meetId}) , if you are admin or teacher you can update a meet by meet id
* Using the  [http://localhost:8080/meet/getAllMeetByAdvisorTeacherAsList](http://localhost:8080/meet/getAllMeetByAdvisorTeacherAsList) , if you are teacher you can get all meets of an advisory teacher as list by providing username of advisory teacher as header paramete
* Using the  [http://localhost:8080/meet/getAllMeetByStudent](http://localhost:8080/meet/getAllMeetByStudent) , if you are student you can get all meets of a student as list by providing username of student as header parameter
* Using the  [http://localhost:8080/meet/search?page=0&size=10](http://localhost:8080/meet/search?page=0&size=10) , if you are admin you can get all meets by page.
* Using the  [http://localhost:8080/meet/getAllMeetByAdvisorAsPage?page=0&size=10](http://localhost:8080/meet/getAllMeetByAdvisorAsPage?page=0&size=10) , if you are teacher you can get all meets of an advisory teacher as page by providing username of the advisory teacher as header parameter.

### Using the Student Service,
Admins can perform all operations
If you are manager or assistant manager you can perform the below operations
* Using the  [http://localhost:8080/students/save](http://localhost:8080/students/save) , you can save a new student
* Using the  [http://localhost:8080/students/changeStatus](http://localhost:8080/students/changeStatus?id=""&status="") , you can set a student as active/passive by a boolean value
* Using the  [http://localhost:8080/students/getAll](http://localhost:8080/students/getAll) , you can get all students by list
* Using the  [http://localhost:8080/students/update/{id}](http://localhost:8080/students/update/{id}) , you can update a student by id
* Using the  [http://localhost:8080/students/delete/{id}](http://localhost:8080/students/delete/{id}) , you can delete a student by id
* Using the  [http://localhost:8080/students/getStudentByName?name=""](http://localhost:8080/students/getStudentByName?name="") , you can get a student by name with request parameter
* Using the  [http://localhost:8080/students/search?page=0&size=10](http://localhost:8080/students/search?page=0&size=10) , you can get all students by page.
* Using the  [http://localhost:8080/students/getStudentById?id=""](http://localhost:8080/students/getStudentById?id="") , you can get a student by request parameter (id)
* Using the  [http://localhost:8080/students/getAllByAdvisoryId](http://localhost:8080/students/getAllByAdvisoryId) , you can get all students of an advisory teacher as list by providing username of advisory teacher as header parameter

If you are student you can only perform the below operation
* Using the  [http://localhost:8080/students/chooseLesson](http://localhost:8080/students/chooseLesson) , you can update lessons of the student by providing username of the advisory teacher as header parameter.

### Using the Student Info Service,
* Using the  [http://localhost:8080/studentInfo/save](http://localhost:8080/studentInfo/save) , if you are a teacher you can save info of a student
* Using the  [http://localhost:8080/studentInfo/delete/{studentInfoId}](http://localhost:8080/studentInfo/delete/{studentInfoId}) , if you are admin or teacher you can delete a student info by student info id
* Using the  [http://localhost:8080/studentInfo/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/studentInfo/search?page=0&size=10&sort="date"&type="desc") , if you are admin, manager or assistant manager you can get all student infos by page.
* Using the  [http://localhost:8080/studentInfo/update/{studentInfo}](http://localhost:8080/studentInfo/update/{studentInfo}) , if you are admin or teacher you can update a student info by student info id
* Using the  [http://localhost:8080/studentInfo/getAllForTeacher?page=0&size=10](http://localhost:8080/studentInfo/getAllForTeacher?page=0&size=10) , if you are teacher you can get all student infos of the teacher as page by providing username of the teacher as header parameter
* Using the  [http://localhost:8080/studentInfo/getAllForStudent?page=0&size=10](http://localhost:8080/studentInfo/getAllForStudent?page=0&size=10) , if you are student you can get all infos of the student as page by providing username of the student as header parameter
* Using the  [http://localhost:8080/studentInfo/getByStudentId/{studentId}](http://localhost:8080/studentInfo/getByStudentId/{studentId}) , if you are admin, manager or assistant manager you can get all infos of the student as list by student Id
* Using the  [http://localhost:8080/studentInfo/get/{studentInfoId}](http://localhost:8080/studentInfo/get/{studentInfoId}) , if you are admin, manager or assistant manager you can get the student info by student info id

### Using the Teacher Service,
You have to be admin, manager or assistant manager to perform an operation
* Using the  [http://localhost:8080/teachers/save](http://localhost:8080/teachers/save) , you can save a new teacher
* Using the  [http://localhost:8080/teachers/getAll}](http://localhost:8080/teachers/delete/{studentInfoId}) , you can get all teachers by list
* Using the  [http://localhost:8080/teachers/getTeacherByName?name=""}](http://localhost:8080/teachers/getTeacherByName?name="") , you can get all teachers by teacher name as list
* Using the  [http://localhost:8080/teachers/delete/{id}](http://localhost:8080/teachers/delete/{id}) , you can delete a teacher by id
* Using the  [http://localhost:8080/teachers/getSavedTeacherById/{id}](http://localhost:8080/teachers/getSavedTeacherById/{id}) , you can get the teacher by id
* Using the  [http://localhost:8080/teachers/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/teachers/search?page=0&size=10&sort="date"&type="desc") , you can get all teachers infos by page.
* Using the  [http://localhost:8080/teachers/update/{userId}](http://localhost:8080/teachers/update/{userId}) , you can update a teacher by id
* Using the  [http://localhost:8080/teachers/chooseLesson](http://localhost:8080/teachers/chooseLesson) , you can update lessons of the teacher.

### Using the Vice Dean Service,
You have to be admin or manager to perform an operation
* Using the  [http://localhost:8080/vicedean/save](http://localhost:8080/vicedean/save) , you can save a new vice dean
* Using the  [http://localhost:8080/vicedean/update/{id}](http://localhost:8080/vicedean/update/{id}) , you can update a vice dean by id
* Using the  [http://localhost:8080/vicedean/delete/{id}](http://localhost:8080/vicedean/delete/{id}) , you can delete a vice dean by id
* Using the  [http://localhost:8080/vicedean/getViceDeanById/{id}](http://localhost:8080/vicedean/getViceDeanById/{id}) , you can get a vice dean by id
* Using the  [http://localhost:8080/vicedean/getAll}](http://localhost:8080/vicedean/delete/{studentInfoId}) , you can get all vice dean by list
* Using the  [http://localhost:8080/vicedean/search?page=0&size=10&sort="date"&type="desc"](http://localhost:8080/vicedean/search?page=0&size=10&sort="date"&type="desc") , you can get all vicedean infos by page.

---
## Term and Final Grades Process 
### Using the Communication Message Service,
Necessary codings were made for calculating the fall and spring semesters and the grade point average of that semester.  
* Students must choose a separate course for each semester.
* At least 3 compulsory courses must be selected.
* The total credit score of the selected courses must be more than 30 points for one semester.

When calculating the end-of-ETerm average, 60% of the compulsory courses are multiplied by their own credit score, and 40% of the elective courses are multiplied by their own credit score and divided by the total credit score.
