   Booking API

This repository contains a Postman collection for interacting with the Booking API hosted at https://restful-booker.herokuapp.com/. The API allows users to manage hotel bookings, including authentication, creating, retrieving, updating, and deleting bookings.

Table of Contents

Getting Started

Authentication

Endpoints

Get All Bookings

Filter Bookings by Name

Get Bookings by Date

Create a New Booking

Get Booking by ID

Update a Booking

Delete a Booking

Running the Collection

Getting Started

To use this API collection, import the Booking.postman_collection.json file into Postman and configure your environment variables accordingly.

Authentication

To interact with most endpoints, an authentication token is required. Obtain a token by sending a POST request to:

POST https://restful-booker.herokuapp.com/auth

Request Body:

{
  "username": "admin",
  "password": "password123"
}

Upon successful authentication, a token is returned and should be included in future requests as a bearer token or in the Cookie header.

Endpoints

Get All Bookings

GET https://restful-booker.herokuapp.com/booking

Retrieves a list of all bookings.

Filter Bookings by Name

GET https://restful-booker.herokuapp.com/booking?firstname=Josh

Fetches bookings by first name.

Get Bookings by Date

GET https://restful-booker.herokuapp.com/booking?start=2020-01-01&end=2021-05-18

Filters bookings within a date range.

Create a New Booking

POST https://restful-booker.herokuapp.com/booking

Request Body:

{
  "firstname": "Mario",
  "lastname": "Budev",
  "totalprice": 6969,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2018-01-01",
    "checkout": "2019-01-01"
  }
}

Get Booking by ID

GET https://restful-booker.herokuapp.com/booking/{{bookingId}}

Retrieves details of a specific booking.

Update a Booking

PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}

Request Body:

{
  "firstname": "MarioMario",
  "lastname": "BudevBudev",
  "totalprice": 16969,
  "depositpaid": false,
  "bookingdates": {
    "checkin": "2018-02-02",
    "checkout": "2019-03-03"
  },
  "additionalneeds": "super bowls"
}

Delete a Booking

DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}

Deletes a booking by ID.

Running the Collection

Import the Booking.postman_collection.json file into Postman.

Set environment variables Token and bookingId.

Run the collection requests sequentially.

This collection includes tests for response validation and data integrity. Ensure Postman is updated to the latest version for best results.

For more details, visit Restful Booker API documentation.

