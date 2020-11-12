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

## API REST

* mock-ups will be made for the application interfaces (drawn on paper or using an online tool)

Sample requests

```
GET /messages?search={searchParam}&orderBy={orderByParam}
```

Sample responses

```json
[ 
  {
    "subject": "Some text",
    "from": "some@email.com",
    "message": "Some more text"
  }
]
``'
