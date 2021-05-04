Project Set-Up

This project can be used with npm/yarn.
Install npm/yarn locally as per user requirement

This proj does not has linting script due to some setup issues. Please feel free to add.
1. Route inside the nas_academy Repo and write command npm install or yarn install.
2. Copy .env.example to .env file
3. After installation just run npm strat or yarn start. That's it! You are good to go... ;)

NOTE: A user cannot send more than 10 requests within 10 seconds, that is a feature implemented using custom request rate middleware, and not a bug :P

<<<<<<<<<<<<<< Version 2.0.0 >>>>>>>>>>>>>>>>>>>>>

In version 2.0.0,
The project is updated to fetch and save data locally by using variables at run-time without using any libraries.
It is availabe in branch feature/car-park-wo-db.
All libraries, DB connections are removed.
Only express, dotenv libraries were used as per guidelines. (jest is used for unit tests)
The parking slots are initialised when the server starts using constructor.
The logic remains identical, only the approach has changed for fetching and saving data locally during runtime.
Note: everytime server starts/re-starts previous data will be lost.

ALL APIs are .get('api_endpoint');

/carpark/parkCar/:carnumber
This API parks the car for the given car number

/carpark/unparkCar/:carnumber
This API unparks the car for the given car number

/carpark/info/:number
This API gets details for that car number or slot number
Note: The slot number is integer type.

/carpark/alldetails
This is a complimentary API for fetching all details of all the parking spots occupied/unoccupied both.



<<<<<<<<<<<<<< Version 1.0.0 >>>>>>>>>>>>>>>>>>>>>

In this service, there are 4 APIs, One is called internally for truncating and initialising the Parking DB.
For Database, this project is using DB Mongoose from https://cloud.mongodb.com/v2/. It's a free limited version for the sake of this project, so there maybe sometimes latency issues. Please ignore it otherwise.

Two tables/Schemas are used
1) Users 2)Parkings
users table is used for keeping track of request of users as per IP address
parkings table is used to keep records of prakings and cars

Port no 5001 is used, It can be modified in .env file. Don't forget to update the DB_API variable also if updating the port number.


_ APIs _

/carpark/initialise
This API Truncates parkings Db and initialise car parking spots

/carpark/parkCar/:number
This API parks the car for the given car number

/carpark/unparkCar/:number
This API unparks the car for the given car number

/carpark/info/:number
This API gets details for that car number or slot number
Note: The slot number is integer type.

/carpark/alldetails
This is a complimentary API for fetching all details of all the parking spots occupied/unoccupied both.

Unit Tests are not included due to time restraints. :(