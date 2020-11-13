# Project documentation guidelines - Anonymous grading
 
## Roles

The roles for the project members are as followed:
* Alexandru Ion: Team Lead
* Alexia Ionescu: Full-stack Developer
* Vlad-Stefan Ivan: Back-end Developer
* Alexandra Pantiru: Front-end Developer

## Introduction

Our goal is to allow students' projects to be graded by an anonymous juries of peers. If you are a student member in a project team, you are able to add a project and define a series of partial project deliverables. Once you register, you become a member, therefore you will be able to anonymously evaluate and grade a project. Simply, by registering you will automatically become eligible to evaluate. 

Whenever you want to add another layer of fairness and impartiality to your grading, you can use the anonymous grading feature. You won't know who made the submission, so you aren't unduly influenced by a student's previous performance, class participation, conflicts, race, gender, or perceived student aptitude. This practice can also contribute to the student-instructor relationship because students are assured that grading was unbiased.

On the market, similar products can be found, such as "Canvas Release: Anonymous Moderated Grading" or "ZipGrade", "Grade Ticker", "Gradebook Pro", "Flubaroo", although now all of them permit uncredited grading.

## Application interfaces

![1](https://user-images.githubusercontent.com/52484598/98982109-83325c00-2527-11eb-8b31-b7820782144c.png)
![2](https://user-images.githubusercontent.com/52484598/98982176-a0ffc100-2527-11eb-865d-7b92fc891567.png)
![3](https://user-images.githubusercontent.com/52484598/98982179-a1985780-2527-11eb-8324-1957418f4375.png)
![4](https://user-images.githubusercontent.com/52484598/98982182-a1985780-2527-11eb-9729-d922c30abc24.png)
![5](https://user-images.githubusercontent.com/52484598/98982184-a1985780-2527-11eb-9b9e-5a46ba6cf10e.png)
![6](https://user-images.githubusercontent.com/52484598/98982185-a230ee00-2527-11eb-985c-d75d24176010.png)

## API REST

### Authentication

Sample requests
```
POST /api/Authentication
```
Sample body
```
{
    "username": "JohnDoe",
    "password": "password"
}
```
Sample reponse
```
{
    "authToken": "SampleToken"
}
```

### Projects

#### Get All

Sample requests
```
GET /api/Projects
```
Sample header
```
Authorization: Bearer <token>
```
Sample reponse
```
[
  {
     "id": 1,
     "name": "John Doe",
     "projectName": "The name of the project",
     "link": "https://github.com",
     "grade": 5
  },
  {
     "id": 2,
     "name": "Jane Doe",
     "projectName": "The name of the project",
     "link": "https://github.com/2",
     "grade": 2
  }
]
```

#### Get by Id

Sample requests
```
GET /api/Projects/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response
```
{
   "id": 1,
   "name": "John Doe",
   "projectName": "The name of the project",
   "link": "https://github.com",
   "grade": 5
}
```

#### Add project

Sample requests
```
POST /api/Projects
```
Sample header
```
Authorization: Bearer <token>
```
Sample body
```
{
   "projectName": "A name for the project",
   "link": "link to the project"
}
```

The response of the POST method will provide the link for the newly created project (/api/Projects/{id})

#### Patch project

Sample requests
```
PATCH /api/Projects/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample body
```
{
   "projectName":"A new name for the project"
}
```

The response of the PATCH method will provide the link for the modified project (/api/Projects/{id})

#### Delete
```
DELETE /api/Projects/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response:
```
{
   "message" : "Deleted successfully!",
   "statusCode" : 200
}
```

### Comments

#### Get All

Sample request
```
GET /api/Projects/{id}/Comments
```
Sample header
```
Authorization: Bearer <token>
```
Sample response
```
[
    { 
        "id": 1,
        "message": "Hello",
        "createdAt": "13/11/2020"
        
     },
     { 
        "id": 2,
        "message": "Hello",
        "createdAt": "14/11/2020"
     }
]
```

#### Get by Id
```
GET api/Projects/{id}/Comments/{commentId}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response
```
{
   “id”: 1
   “message”: ”Hello”,
   “createdAt”: ”13/11/2020”
}
```
#### POST Comment
```
POST api/Projects/{id}/Comments
```
Sample header
```
Authorization: Bearer <token>
```
Sample body: 
```
{
    "message": "Hello"
}
```

Sample response:

The response of the POST method will provide the link for the newly created project (/api/Projects/{id}/Comments/{commentId})

#### PUT comment

Sample request
```
PUT api/Projects/{id}/comments/{id}
```
Sample header
```
Authorization: Bearer <token>
```

Sample body
```
{
    "comment": "Modified comment"
}
```
Sample response
```
{ 
    "comment": "Modified comment",
    "modifiedAt":13/11/2020
}
```

#### Delete comment

Sample request:
```
DELETE api/Projects/{id}/Comments/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response:
```
{
   "message" : "Deleted successfully!",
   "statusCode" : 200
}
```

### Grades

#### Get grade

Sample request
```
GET api/Projects/{id}/Grade
```
Sample header
```
Authorization: Bearer <token>
```
Sample response
``` 
{ 
    "projectName":"The Project Name",
    "projectGrade":10
}
```
#### Give grade to project

Sample request
``` 
POST api/Projects/{id}/Grade
```
Sample header
```
Authorization: Bearer <token>
```
Sample body
```
{
    "projectGrade": 8
}
```
Sample response
```
{ 
    "projectGrade":8,
    "modifiedAt":13/11/2020
}
```

### Users

#### Get All users

Sample request:
```
GET /api/Users
```
Sample header
```
Authorization: Bearer <token>
```
Sample response:
```
[
    {
        "id" : 1,
        "name" : "Vlad Ivan",
        "nrOfProjects" : 3
    }
]
```

#### Get user by id

Sample request:
```
GET /api/Users/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response:
```
{
    "id" : 2,
    "name" : "Alexia Ionescu",
    "nrOfProjects" : 5
}
```

#### Delete user

Sample request:
```
DELETE /api/Users/{id}
```
Sample header
```
Authorization: Bearer <token>
```
Sample response:
```
{
   "message" : "User deleted successfully!",
   "statusCode" : 200
}
```
