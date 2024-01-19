# GreenStitch Backend Application

A Spring Boot Application that incorporates main backend concepts such as MVC layers, Security, Databases, and Rest APIs. The app allows user to sign up and log in using their credentials and post login the app uses a JWT token for every request send by user to validate the user. It is built using Java, Spring Boot, and utilizes the H2 Database for storing the user details.

## Installation and Setup

To get started with here are the things you'd need:

### Prerequisites

```
Java SE 21
IntelliJ Idea
Postman
Maven (Build Tool)
Spring Boot
```

### Clone the Repository

```
https://github.com/Tameemahmedd/GSBackend_Assignment
```
### Change the directory

```
cd GSBackend_Assignment/src
```
### Server Configuration
The app runs on the default server port 8080.

## API Endpoints
There is basically three endpoints which is engrained into the app, they provide the specific services such as signing up, signing in and to wish the user after logging in. 

### 1.Sign Up API 

* HTTP Method: POST
* URI: http://localhost:8080/app/sign-up
* Description: To sign up as a new user.
* Request Body:
```
{
  "email": "cr2@gmail.com",
  "password": "Tameem@12"  
}
```
* Response Body:
```
{
    "id": 1,
    "password": "$2a$10$AmvK2i2zBrdua3BVe9dSeeR62g18j4yknzdAVNjmnogTpyE0dNBSK",
    "email": "cr2@gmail.com",
    "role": "ROLE_USER"
}
```
* HTTP Status:201 CREATED

### 2.	Sign In API 
* HTTP Method: GET
* URI: http://localhost:8080/app/sign-in
* Description: To sign in after being registered and get a JWT token in response.
* Request Body: 
```
{
    "email":"cr2@gmail.com",
    "password":"Tameem@12"
}
```
* Response Body
```
{
    "jwtToken": "eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJjcjJAZ21haWwuY29tIiwiaWF0IjoxNzA1Njg5MzY2LCJleHAiOjE3MDU3MDczNjZ9.ublFK0eMuLjOAmbcx1z2N7b6jyJkoTwUmJ_-OBndtRT3bF9dPXgO2RdCAmsgri27fdL2HKzcK81gscgJWqbGfQ",
    "username": "cr2@gmail.com"
}
```
* HTTP Status: 200 OK

### 3.	Hello API 
* HTTP Method: GET
* URI: http://localhost:8080/app/logged-in/user 
* Authorization: JWT Token
* Description: To redirect to the homepage after logging in . This request uses JWT token that needs to be included in the request header (which was provided after successful log in) to carry out further request validations each time when the user sends a request to the server. 
* Example of JWT Token:" Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJjcjJAZ21haWwuY29tIiwiaWF0IjoxNzA1Njg5MzY2LCJleHAiOjE3MDU3MDczNjZ9.ublFK0eMuLjOAmbcx1z2N7b6jyJkoTwUmJ_-OBndtRT3bF9dPXgO2RdCAmsgri27fdL2HKzcK81gscgJWqbGfQ "
* Response Body:
  ```
    Hello from GreenStitch'
  ```
* HTTP Status: 200 OK


## Built With

* Java
* Maven
* Spring Boot
* Spring Security
* Spring Data Jpa
* H2 Database
* Lombok


## Authors

* **Tameem Ahmed** - *Initial work* - [TameemAhmedd](https://github.com/Tameemahmedd)


