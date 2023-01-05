#DevCamper API

> Backend API for devcamper applicaiton by brad traversy which is a bootcamp directory website.

##Usage

Rename "Config/config.env.env" to "config.cinfig.env" and update the valies/settings to your own

#install Dependencies

```
npm install

```

## Run App

```
Run in dev mode
npm run dev

# Run in prod mode
npm start
```

--version 1.0.0

# DevCamper API

Backend API for the DevCamper application to manage bootcamps, courses , reviews, users and authentication

<!--- If we have only one group/collection, then no need for the "ungrouped" heading -->

## Endpoints

- [Bootcamps](#bootcamps)
  1. [Get All Bootcamps](#1-get-all-bootcamps)
  1. [Get single Bootcamp](#2-get-single-bootcamp)
  1. [create new bootcamp](#3-create-new-bootcamp)
  1. [Update Bootcamp](#4-update-bootcamp)
  1. [Delete Bootcamp](#5-delete-bootcamp)
  1. [Get Bootcamps by Distance](#6-get-bootcamps-by-distance)
  1. [Upload photo](#7-upload-photo)
- [Courses](#courses)
  1. [Get All Courses](#1-get-all-courses)
  1. [Get Courses for bootcamp](#2-get-courses-for-bootcamp)
  1. [Get single Course](#3-get-single--course)
  1. [Create Bootcamp course](#4-create-bootcamp-course)
  1. [Update course](#5-update-course)
  1. [Delete Course](#6-delete-course)
- [Authentication](#authentication)
  1. [Register User](#1-register-user)
  1. [login user](#2-login-user)
  1. [Get loggedin user via token](#3-get-loggedin-user-via-token)
  1. [forgot password](#4-forgot-password)
  1. [Reset Password](#5-reset-password)
  1. [Update user Details](#6-update--user-details)
  1. [Update Password](#7-update-password)
  1. [Logout User](#8-logout-user)
- [Users](#users)
  1. [get all users](#1-get-all-users)
  1. [get single user](#2-get-single-user)
  1. [create user](#3-create-user)
  1. [Update user](#4-update-user)
  1. [Delete User](#5-delete-user)
- [Reviews](#reviews)
  1. [Get all reviews](#1-get-all-reviews)
  1. [Get reviews for Bootcamp](#2-get-reviews-for-bootcamp)
  1. [Get Single review](#3-get-single-review)
  1. [Add Review for Bootcamp](#4-add-review-for-bootcamp)
  1. [update review](#5-update-review)

---

## Bootcamps

Bootcamps CRUD functionality

### 1. Get All Bootcamps

Fetch all bootcamps from database. Includes pagination, filtering etc

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/bootcamps
```

### 2. Get single Bootcamp

Get single bootcamp by id

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/bootcamps/5d725a037b292f5f8ceff787
```

### 3. create new bootcamp

Add new bootcamp to database , must be authenticated and must be publisher or admin

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps
```

**_Headers:_**

| Key           | Value                                                                                                                                                                              | Description |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| Content-Type  | application/json                                                                                                                                                                   | json Type   |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYyNDliZWYyNmYxNGVhMWJhN2I4Y2JmMiIsImlhdCI6MTY0OTA0OTAwNywiZXhwIjoxNjUxNjQxMDA3fQ.BxDNZOg_3y4HfmD_HRisdJazRojzOjJmo0xwPwOdsNc |             |

**_Body:_**

```js
{
   	"name": "ModernTechBootcamp<script>alert(1)</script>",
		"description": "Is coding your passion? Codemasters will give you the skills and the tools to become the best developer possible. We specialize in front end and full stack web development",
		"website": "https://devcentral.com",
		"phone": "(444) 444-4444",
		"email": "enroll@devcentral.com",
		"address": "45 Upper College Rd Kingston RI 02881",
		"careers": [
			"Mobile Development",
			"Web Development",
			"Data Science",
			"Business"
		],
		"housing": false,
		"jobAssistance": true,
		"jobGuarantee": true,
		"acceptGi": true
}
```

### 4. Update Bootcamp

Update single bootcamp in database

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/bootcamps/624aa6907fd2ee54e500fc75
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "housing":"false"
}
```

### 5. Delete Bootcamp

Delete Bootcamp from database

**_Endpoint:_**

```bash
Method: DELETE
Type:
URL: {{URL}}/api/v1/bootcamps/624bb1a0c3ec18730dd1c092
```

### 6. Get Bootcamps by Distance

Get bootcamps with a radius of specific zipcode

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/bootcamps/radius/02118/2
```

### 7. Upload photo

router to upload a bootcamp photo

**_Endpoint:_**

```bash
Method: PUT
Type: FORMDATA
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/photo
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

| Key  | Value | Description |
| ---- | ----- | ----------- |
| file |       |             |

## Courses

Create, Read, Update and delete courses

### 1. Get All Courses

Get all courses

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/courses
```

### 2. Get Courses for bootcamp

Get the specific courses for the bootcamp

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/bootcamps/5d713a66ec8f2b88b8f830b8/courses
```

### 3. Get single Course

Get single course by id

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/courses/5d725cb9c4ded7bcb480eaa1
```

### 4. Create Bootcamp course

Creating course for specific bootcamp

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps/624aaa5411084762ef4df218/courses
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "title": "Full Stack Web Development 1",
		"description": "In this course you will learn full stack web development, first learning all about the frontend with HTML/CSS/JS/Vue and then the backend with Node.js/Express/MongoDB",
		"weeks": 12,
		"tuition": 13000,
		"minimumSkill": "intermediate",
		"scholarhipsAvailable": true
}
```

### 5. Update course

Update course in datavase

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/courses/624aaa9311084762ef4df21c
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "tution" : 13000
}
```

### 6. Delete Course

Delte course from database

**_Endpoint:_**

```bash
Method: DELETE
Type: RAW
URL: {{URL}}/api/v1/courses/624aaa9311084762ef4df21c
```

## Authentication

Routes for user authentication including register,login,reset password etc

### 1. Register User

Register new user to the db with encrypted password

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/register
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "name":"jack doew",
    "email":"brad@gmail.com",
    "password":"123456",
    "role":"user"
}
```

### 2. login user

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/login
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{

    "email":"publisher@gmail.com",
    "password":"123456"
}
```

### 3. Get loggedin user via token

**_Endpoint:_**

```bash
Method: GET
Type: RAW
URL: {{URL}}/api/v1/auth/me
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

### 4. forgot password

Generate password token and email

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/forgotpassword
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "email":"kevin@gmail.com"
}
```

### 5. Reset Password

Reset user password using token

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/resetpassword/bb1438379cac31fa6a99108dfb090c98864f3fcd
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "password":"1234567"
}
```

### 6. Update user Details

Update logged in user name and email

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/updatedetails
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "email":"aman@gmail.com",
    "name":"Aman Mool"
}
```

### 7. Update Password

update logged in user password , send in the body currentPassword and newpassword

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/updatepassword
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "currentPassword" : "1234567",
    "newPassword":"123456"
}
```

### 8. Logout User

Clear token cookies

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/auth/logout
```

## Users

Crud functionality for user only admin

### 1. get all users

get all users (admin)

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/users
```

### 2. get single user

get single user by id (admin)

**_Endpoint:_**

```bash
Method: GET
Type: RAW
URL: {{URL}}/api/v1/users/624ad2c5ddc9777508c03e96
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "name":"Saman prasad Mool"

}
```

### 3. create user

create user

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/users
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "name":"Saman Mool",
    "email":"saman@gmail.com",
    "password": "123456"
}
```

### 4. Update user

update user in database (admin)

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/users/624ad2c5ddc9777508c03e96
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "name":"Saman prasad Mool"

}
```

### 5. Delete User

Delete user from the database (admin)

**_Endpoint:_**

```bash
Method: DELETE
Type:
URL: {{URL}}/api/v1/users/624ad2c5ddc9777508c03e96
```

## Reviews

Manage course reviews

### 1. Get all reviews

get all reviews from database and populate with bootcamp name and description

**_Endpoint:_**

```bash
Method: GET
Type: RAW
URL: {{URL}}/api/v1/reviews
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "title" : "Had Fun"
}
```

### 2. Get reviews for Bootcamp

Fetch the reviews for a specific bootcamp

**_Endpoint:_**

```bash
Method: GET
Type:
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/reviews
```

### 3. Get Single review

Fetch a review from database by id and populate bootcamp name and description

**_Endpoint:_**

```bash
Method: DELETE
Type:
URL: {{URL}}/api/v1/reviews/624b14b3e2344d926608792c
```

### 4. Add Review for Bootcamp

Insert review for a specific bootcamp

**_Endpoint:_**

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps/624af3494bef4df79b742575/reviews
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "title":"Great man i am jack",
    "text":"I learned a lot ",
    "rating": 6
    }
```

### 5. update review

Update review from database

**_Endpoint:_**

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/reviews/624b14b3e2344d926608792c
```

**_Headers:_**

| Key          | Value            | Description |
| ------------ | ---------------- | ----------- |
| Content-Type | application/json | json Type   |

**_Body:_**

```js
{
    "title":"I am jack 2"
}
```

---

[Back to top](#devcamper-api)

> Generated at 2022-04-05 11:20:27 by [docgen](https://github.com/thedevsaddam/docgen)
