# 🏨 Booking API

This repository contains a Postman collection for interacting with the **Booking API** hosted at [`restful-booker.herokuapp.com`](https://restful-booker.herokuapp.com/). The API allows users to manage hotel bookings, including authentication, creating, retrieving, updating, and deleting bookings.

---

## 📌 Table of Contents

- [🚀 Getting Started](#-getting-started)
- [🔑 Authentication](#-authentication)
- [🌍 Endpoints](#-endpoints)
  - [📋 Get All Bookings](#-get-all-bookings)
  - [🔎 Filter Bookings by Name](#-filter-bookings-by-name)
  - [📆 Get Bookings by Date](#-get-bookings-by-date)
  - [📝 Create a New Booking](#-create-a-new-booking)
  - [📂 Get Booking by ID](#-get-booking-by-id)
  - [✏️ Update a Booking](#-update-a-booking)
  - [🗑️ Delete a Booking](#-delete-a-booking)
- [▶️ Running the Collection](#-running-the-collection)

---

## 🚀 Getting Started

To use this API collection, import the `Booking.postman_collection.json` file into Postman and configure your environment variables accordingly.

---

## 🔑 Authentication

To interact with most endpoints, an authentication token is required. Obtain a token by sending a `POST` request to:

```http
POST https://restful-booker.herokuapp.com/auth
```

### 📩 Request Body:
```json
{
  "username": "admin",
  "password": "password123"
}
```

🔹 Upon successful authentication, a token is returned and should be included in future requests as a bearer token or in the `Cookie` header.

---

## 🌍 Endpoints

### 📋 Get All Bookings
```http
GET https://restful-booker.herokuapp.com/booking
```
Retrieves a list of all bookings.

### 🔎 Filter Bookings by Name
```http
GET https://restful-booker.herokuapp.com/booking?firstname=Josh
```
Fetches bookings by first name.

### 📆 Get Bookings by Date
```http
GET https://restful-booker.herokuapp.com/booking?start=2020-01-01&end=2021-05-18
```
Filters bookings within a date range.

### 📝 Create a New Booking
```http
POST https://restful-booker.herokuapp.com/booking
```

#### 📝 Request Body:
```json
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
```

### 📂 Get Booking by ID
```http
GET https://restful-booker.herokuapp.com/booking/{{bookingId}}
```
Retrieves details of a specific booking.

### ✏️ Update a Booking
```http
PUT https://restful-booker.herokuapp.com/booking/{{bookingId}}
```

#### ✏️ Request Body:
```json
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
```

### 🗑️ Delete a Booking
```http
DELETE https://restful-booker.herokuapp.com/booking/{{bookingId}}
```
Deletes a booking by ID.

---

## ▶️ Running the Collection

1. 📥 Import the `Booking.postman_collection.json` file into Postman.
2. ⚙️ Set environment variables `Token` and `bookingId`.
3. ▶️ Run the collection requests sequentially.

📌 This collection includes tests for response validation and data integrity. Ensure Postman is updated to the latest version for best results.

---

📖 For more details, visit [Restful Booker API](https://restful-booker.herokuapp.com/) documentation. 🌐

