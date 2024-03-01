# Pepolon - Backend

**Author:**  
_Burak Inan_   
_burakinan.dev@gmail.com_
---

## Description:
* The backend of Pepolon has been built with Java and Spring technologies. It provides a comprehensive set of RESTful APIs for managing various entities within an job application platform. The system includes functionalities for authentication, administrators, tickets, email bulletins, Cloudflare R2 storages, Sendgrid mail services, tenants, organizations, vacancies and enrollments.

## Key Features:

* Authentication and Authorization
* CRUD operations for Email bulletins, Tenants, Organizations, Vacancies and Enrollments
* Tickets for system-wide communication
* Cloudflare R2 storage to store files such as resume, profile pciture, organization logo etc.
* Sendgrid mail services to alert users and support team about process

## Technologies Used
- Java 17
- Spring Boot
- Spring Data JPA
- Spring Security (Jwt token)
- PostgreSQL
- Cloudflare R2
- SendGrid Mail Service
- Docker
- Kubernetes
- CI/CD


## API Documentation
The Pepolon platform provides the following RESTful APIs:

### Using the Tenant Service,
You can perform;

* After registering to the platform, you can verify your account by following the steps you receive in the 'verification email',
* CRUD operation,
* Update password,
* Reset forgotton password by following the steps you receive in the 'forgot password email',
* Generate profile url,
* CRUD operations for Resume and Profile picture


### Using the Organization Service,
You can perform;

* After registering to the platform, you can verify your account by following the steps you receive in the 'verification email',
* CRUD operation,
* Update email,
* Generate profile url,
* CRUD operations for Organization logo,
* List recent organizations,
* Retreive organizations as pages by searching by Name, Country and City
* Retreive organizations as list by searching with name

### Using the Vacancy Service,
You can perform;

* CRUD operation,
* List recent jobs,
* List recent job posts of a specific organization,
* Retreive job posts as pages by searching by title, vacancyType, vacancyLocation, category and organization
* Retreive details of a specific job post

### Using the Enrollment Service,
You can enroll to a job

### Using the Category Service,
You can perform;

* Retreive details of a specific category
* Retreive all categories
* Retreive all sub categories
* Retreive all sub categories of a specific category
* Retreive all main categories

### Using the Ticket Service,
You can create Ticket to alert support team

### Using the Email Bulletin Service,
You can perform

* Subscribe, 
* Unsubscribe,
* Calculate the count of subscribers

## Live
<a href="https://pepolon.com/" target="_blank">Go to website</a> :arrow_upper_right:
