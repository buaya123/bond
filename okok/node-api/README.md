# okok - node backend
## Project setup
Navigate to the okok directory and run the following commands to setup the server

- npm install
- node server.js

# Endpoints - api
## 1- Auth
- Endpoint ``https://bond-api.vercel.app/user``
- Method: `POST`
- Data object (Send in Body*): 
```
{
"uid": "uid from google auth",
"name": "name from google auth",
"username": "send empty string (User can update their username later after signin)",
"photo": "profileURL from google auth",
"email": "email from google auth"
}
```
### RESPONSE
#### In case they already have an account in db
```
[
    {
        "status": "login",
        "message": "Thanos Logged in successfully!"
    }
]
```
#### In case it's their first time
```
[
    {
        "status": "signup",
        "message": "Thanos account created successfully!"
    }
]
```
## 2- Send Invite
- Endpoint ``https://bond-api.vercel.app/sendInvite/:email``
- Method: `POST`
- Data: JSON (Send in Params*): 
```
{
"email": "email of recipient"
}
```
### RESPONSE
#### In case they already have an account in db
```
[
    {
        "data": "0"
    }
]
```
#### In case it's their first time
```
[
    {
        "data": "1"
    }
]
```



