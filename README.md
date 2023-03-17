# aws-go-hello-world

Simple application that exposes following HTTP-based APIs:

1. PUT /hello/<username> { “dateOfBirth”: “YYYY-MM-DD” }
Saves/updates the given user’s name and date of birth in the database.

Expected responses: 
- 204 No Content - when request is successful
- 400 Bad Request - when invalid username is providen (must contain only letters) or invalid date of birth is providen YYYY-MM-DD
- 500 Internal Server Error - unhandled exception 

2. GET /hello/<username>

Expected responses: 
- 200 OK - hello birthday message for the given user
format of birthday message following:

if username's birthday is in N days:
```
{ 
    “message”: “Hello, <username>! Your birthday is in N day(s)”
}
```

if username's birthday is today: 
```
{ 
    “message”: “Hello, <username>! Happy birthday!”
}
```
