# FakeApi-Mockoon-BasicModernLoginApp
This is a fake mockoon REST API which is used for [BasicModernLoginApp](https://github.com/ChaituPenju/BasicModernLoginApp)

Please import `fakeapi_basicmodernloginapp.json` file into your mockoon environment.


# APIs Documentation 

The below three REST APIs are used.

## One - Login a User

### Request

`POST /login`

    'Accept: application/json' http://localhost:3000/api/v1/login

### Request Body
    { 
        "username": "johndoe@mock.com", 
        "password": "iforgotpassword" 
    }

### Success Response

    HTTP/1.1 200 OK
    Content-Type: application/json

    {
        "message" : "User Login Successful!",
        "user" : {
            "id": 1,
            "name": "John Doe",
            "email": "johndoe@mock.com",
            "access_token": "eyJdfwesdf.fewdfoij.vesdrfwerf"
        }
    }

### Failure Response

    HTTP/1.1 401 Unauthorized
    Content-Type: application/json

    {
        "message":"Invalid Username/Password, unauthorized"
    }

##  Two - Get User Details

### Request

`GET /user`

    'Accept: application/json' --header 'x-access-token:<accesstoken>' http://localhost:3000/api/v1/user

### Response

    HTTP/1.1 200 OK
    Content-Type: application/json

    {
        "id": 1,
        "name": "Chaitanya Penjuri",
        "email": "asdf@bbc.com",
        "access_token": "eyJdfwesdf.fewdfoij.vesdrfwerf"
    }

### Failure Response (Incase of invalid access_token)

    HTTP/1.1 401 Unauthorized
    Content-Type: application/json

    {
        "message": "Invalid access_token, so you are unauthorized"
    }

## Three - Logout User

### Request

`GET /logout`

    'Accept: application/json' http://localhost:3000/api/v1/user

### Response

    HTTP/1.1 200 OK
    Content-Type: application/json

    {
        "message": "User Logged out Successfully!"
    }
