# README

T

Service Document for medicare


1.  Sign Up,


Request_type – Post,

Request_url  -  https://medicare-sweety.herokuapp.com/auth


Request Parameter - 


{

"name":"piyush",

"nickname":"UD",

"email":"mba.piyushgupta@gmail.com",

"password":"9916300023",

"password_confirmation":"9916300023"

}


Response Parameter - 


Success - 


{

  "status": "success",

  "data": {

    "provider": "email",

    "uid": "mba.piyushgupta@gmail.com",

    "id": 1,

    "email": "mba.piyushgupta@gmail.com",

    "name": "piyush",

    "nickname": "UD",

    "image": null,

    "created_at": "2016-06-02T08:57:14.000Z",

    "updated_at": "2016-06-02T08:57:15.000Z"

  }

}



Failure - 


{

  "status": "error",

  "data": {

    "id": null,

    "provider": "email",

    "uid": "mba.piyushgupta@gmail.com",

    "name": "piyush2",

    "nickname": null,

    "image": null,

    "email": "mba.piyushgupta@gmail.com",

    "created_at": null,

    "updated_at": null

  },

  "errors": {

    "password_confirmation": [

      "doesn't match Password"

    ],

    "email": [

      "already in use"

    ],

    "full_messages": [

      "Password confirmation doesn't match Password",

      "Email already in use"

    ]

  }

}



2. Sign In,


Request_type – Post,

Request_url  -  https://medicare-sweety.herokuapp.com/auth/sign_in.json



Request Parameter - 


{

"email":"mba.piyushgupta@gmail.com",

"password":"12345678"

}


Response Parameter - 


Success -


{

  "data": {

    "provider": "email",

    "uid": "mba.piyushgupta@gmail.com",

    "id": 1,

    "email": "mba.piyushgupta@gmail.com",

    "name": "piyush",

    "nickname": "UD",

    "image": null

  }

}




Please check the headers then you will get -  access_token, client, and uid


Note  - this will be generated in each request so client is responsible for keeping track of the changing tokens


Failure - 


{

  "errors": [

    "Invalid login credentials. Please try again."

  ]

}



3. Sign out,


Request_type – Delete,

Request_url  -  https://medicare-sweety.herokuapp.com/auth/sign_out.json



Request Parameter – this should be in header






Content-Type: application/json

access-token: GZU8Oh9C82goLBgHQA...

uid: mba.piyushgupta@gmail.com

client: 2lZ_jPnB9b64xzRqiZz1fw



Response Parameter - 


Success -


{

  "success": true

}



Please check the headers then you will get -  access_token, client, and uid


Note  -  By default the authorization headers will change after each request. The

  client is responsible for keeping track of the changing tokens. Change

  this to false to prevent the Authorization header from changing after

  each request.

 


Failure - 


{

  "errors": [

    "User was not found or was not logged in."

  ]

}


4. Update account


Request_type – Put,

Request_url  -  https://medicare-sweety.herokuapp.com/auth.json



Request  header-






Content-Type: application/json

access-token: GZU8Oh9C82goLBgHQA...

uid: mba.piyushgupta@gmail.com

client: 2lZ_jPnB9b64xzRqiZz1fw



Response Parameter - 

{

"name":"piyush",

"nickname":"UyD",

"email":"mba.piyushgupta@gmail.com",

"password":"12345678",

"password_confirmation":"12345678"

}


Success -

{

  "status": "success",

  "data": {

    "provider": "email",

    "uid": "mba.piyushgupta@gmail.com",

    "id": 1,

    "email": "mba.piyushgupta@gmail.com",

    "name": "piyush",

    "nickname": "UyD",

    "image": null,

    "created_at": "2016-06-02T10:13:44.000Z",

    "updated_at": "2016-06-02T12:03:02.000Z"

  }

}


Please check the headers then you will get -  access_token, client, and uid


Note  -  By default the authorization headers will change after each request. The

  client is responsible for keeping track of the changing tokens. Change

  this to false to prevent the Authorization header from changing after

  each request.

 


Failure - 


{

  "status": "error",

  "errors": [

    "User not found."

  ]

}



5. Create Reports


Request_type – Post,

Request_url  -  https://medicare-sweety.herokuapp.com/users/1/reports.json



Request  header-






Content-Type: application/json

access-token: GZU8Oh9C82goLBgHQA...

uid: mba.piyushgupta@gmail.com

client: 2lZ_jPnB9b64xzRqiZz1fw



Response Parameter - 

{

"bgl":1

}


Success -

{

  "status": true,

  "data": {

    "id": 10,

    "bgl": 1,

    "user_id": 1,

    "created_at": "2016-06-03T06:12:05.000Z",

    "updated_at": "2016-06-03T06:12:05.000Z"

  }

}


Please check the headers then you will get -  access_token, client, and uid


Note  -  By default the authorization headers will change after each request. The

  client is responsible for keeping track of the changing tokens. Change

  this to false to prevent the Authorization header from changing after

  each request.

 


Failure - 


{

  "status": false,

  "massage": "Limit is exceeded for the day!"

}



6. Get Reports 


Request_type – Get,

Request_url  -  https://medicare-sweety.herokuapp.com/users/1/reports?type=month_to_date_report&date=2016-06-03


https://medicare-sweety.herokuapp.com/users/1/reports?type=monthly_report&date=2016-06-03


https://medicare-sweety.herokuapp.com/users/1/reports?type=daily_report&date=2016-06-03



Request  header-






Content-Type: application/json

access-token: GZU8Oh9C82goLBgHQA...

uid: mba.piyushgupta@gmail.com

client: 2lZ_jPnB9b64xzRqiZz1fw





Success -

{

  "status": true,

  "all_readings": [

    {

      "id": 5,

      "bgl": 1,

      "user_id": 1,

      "created_at": "2016-06-03T09:16:07.000Z",

      "updated_at": "2016-06-03T09:16:07.000Z"

    },

    {

      "id": 6,

      "bgl": 2,

      "user_id": 1,

      "created_at": "2016-06-03T09:16:26.000Z",

      "updated_at": "2016-06-03T09:16:26.000Z"

    },

    {

      "id": 7,

      "bgl": 3,

      "user_id": 1,

      "created_at": "2016-06-03T09:16:33.000Z",

      "updated_at": "2016-06-03T09:16:33.000Z"

    },

    {

      "id": 8,

      "bgl": 6,

      "user_id": 1,

      "created_at": "2016-06-03T09:16:46.000Z",

      "updated_at": "2016-06-03T09:16:46.000Z"

    }

  ],

  "max_reading": 6,

  "min_reading": 1,

  "avg_reading": 3

}



Failure - 


{

  "status": false,

  "massage": "Limit is exceeded for the day!"

}