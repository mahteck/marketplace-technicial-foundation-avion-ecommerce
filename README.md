# E-Commerce Furniture Project

This project is an e-commerce platform that sells trendy, Pinterest-inspired, and affordable furniture. The website is built using **Next.js 14** and **TypeScript** and integrates **Sanity** for data management. The system supports both **user** and **admin** functionalities, including managing products, tracking shipments, placing orders, and more.

---

## Project Development Timeline

### Day 1: Process Documentation
- Initial project setup.
- Documented the overall process flow, including defining the project's objectives and scope.
- Created the initial project structure, focusing on setting up the development environment and tools.

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_hackathon-ecommerce-dataschema-activity-7285528601481928704-Qmyo?utm_source=share&utm_medium=member_desktop).

---

### Day 2: Technical Documentation
- Defined the **technical requirements** for the project, including the software stack and dependencies.
- Designed the **system architecture**, including database design, API structure, and integration points.
- Documented the **API requirements** for managing products, placing orders, and shipment tracking.

### Day 3: API Integration and Data Fetching
- Integrated the **Sanity API** for data management.
- Uploaded the product data into **Sanity** and set up a migration utility for data migration.
- Implemented a system to fetch product data from **Sanity** and display it dynamically on the website.

--- 

## API Specification

This document outlines the API specifications for the project. The system includes the following key APIs:

- **Products API**: For retrieving product data.
- **Shipment API**: For managing shipments, including shipment creation, tracking, and live updates.

---

### 1. Products API

#### Endpoint: `/api/products`

**Method**: `GET`

This endpoint retrieves a list of products available for sale.

##### Request

- **No request body** is required for this endpoint.

##### Response

The response will return a list of products, each containing details like the product's name, description, price, category, image, 
features, and dimensions.

```json
[
  {
    "name": "Sofa set",
    "description": "A stylish, sofa set for your living room.",
    "image": "https://example.com/images/sofa.jpg",
    "id": "1",
    "features": [
            "Premium material",
            "Handmade upholster",
            "Quality timeless classic"
        		],
    "dimensions": {
            "width": "110cm",
            "height": "110cm",
            "depth": "50cm"
        },
    "category": "Sofas",
    "price": 550,
    "tags": [
            "popular products"
        		],
    "slug": "1"
  },
  ...
] 

```
### 2. Login API
### My Endpoint: /api/login
(from this endpoint i'll call /api/login)
### Endpoint: /api/login/
**Method**:  POST
**Header**: headers: {'Content-Type': 'application/json'}
**Payload:** 

```json
{
    "email": "shoaib1244@gmail.com",
    "password": "Bizztrax@123"
}

**Response**
{
    "email": "shoaib1244@gmail.com",
    "password": "Bizztrax@123"
}

```

### 2. Signup API
### My Endpoint: /api/signup
(from this endpoint i'll call /api/signup)
### Endpoint: /api/signup/
**Method**:  POST
**Header**: headers: {'Content-Type': 'application/json'}
**Payload:** 

```json

{
    "name": "shoaib",
    "email": "shoaib1244@gmail.com",
    "password": "SecurePassword123"
}


**Response**
{
    "message": "User created successfully",
    "user": {
        "_createdAt": "2025-01-22T10:07:46Z",
        "_id": "7SHn44fr5ON5cm5sgvVKhE",
        "_rev": "7SHn44fr5ON5cm5sgvVKf7",
        "_type": "user",
        "_updatedAt": "2025-01-22T10:07:46Z",
        "email": "shoaib1244@gmail.com",
        "name": "shoaib",
        "password": "$2a$10$3k2oTkeoAKOP/AgxYIbZSuMUEe8WA3Gegzsv7BnVYbM9M5E7zIO8K"
    }
}

```

### 2. Shipment API
### My Endpoint: /api/shipmentOrder
(from this endpoint i'll call /api/shipments)
### ShipEngine Endpoint: /api/shipment/
**Method**:  GET

This response will return shipment charges.

- **Request**
Query Parameters: weight and distance. 

```json

{
  {
      "weight": 10,
      "distance": 100
  }
}  

```

### 3. Place Order
### My Endpoint: /api/place-order
(from this endpoint i'll call /api/place-order)
### ShipEngine Endpoint: /api/place-order/
**Method**:  POST

This endpoint post data from page to sanity.

- **Response**
The response will include the trackingNumber and additional shipment information, such as the carrier and estimated arrival time (ETA), product info, payment method, customer info.

```json
{
  {
  "customername": "abc",
  "email": "abc@example.com",
  "Phone": "03311343814",
  "shippingAddress": "123 Street, City",
   "paymentMethod": "Cash on Delivery",
    "cartItems": [
      { "product": "vases"},
      { "product": "wall light"}
  ],
  "total": "10000",
  "trackingnumber": "TRN-111111"
  }
}	

```

### My Endpoint: /api/liveTracking
(from this endpoint i'll call /api/tracks/{carrier}/{trackingNumber} api)
### Shippo Endpoint: /api/tracks/{carrier}/{trackingNumber}
**Method: GET**

This endpoint fetches live tracking details for a shipment using the tracking number.

**Request**
**URL Parameters:**
**carrier:** The name of the shipping carrier (e.g., shippo).
**trackingNumber:** The tracking number obtained from the /api/shipments/ endpoint.
**Response**
The response will contain the live tracking information, including the ETA, tracking history, status, and location.

```json
{
  "trackingNumber": "1234567890",
  "carrier": "shippo",
  "eta": "2025-01-18T10:00:00Z",
  "status": "In Transit",
  "trackingHistory": [
    {
      "date": "2025-01-16T10:00:00Z",
      "location": "New York, NY",
      "status": "Shipped"
    },
    {
      "date": "2025-01-17T14:00:00Z",
      "location": "Philadelphia, PA",
      "status": "In Transit"
    }
  ],
  "origin": {
    "city": "New York",
    "country": "US"
  },
  "destination": {
    "city": "Los Angeles",
    "country": "US"
  }
}

```

### Summary of APIs
**/api/products:** Fetches product details.
**/api/shipments/:** Creates a shipment and retrieves a tracking number.
**/api/tracks/{carrier}/{trackingNumber}:** Fetches live tracking details for the shipment.

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_hackathon-webdevelopment-marketplaceproject-activity-7285915162400727040-H83c?utm_source=share&utm_medium=member_desktop).

---

### Day 4: Dynamic Frontend Development
- Developed dynamic frontend pages for:
  - **Product Pages**: Automatically generated for each product.
  - **Product Detail Page**: Displaying detailed information about each product.
  - **Add to Cart**: Users can add products to the cart.
  - **Cart Page**: Displaying the items in the cart.
  - **Checkout Page**: Handling user checkout and order placement.
  - Implemented **Signup** and **Shipping APIs** for user registration and shipment handling.
  - Developed the functionality for **product fetching API**, **signup API**, and **shipping API**.


---

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_webdevelopment-ecommerce-nextjs-activity-7287015809992773632-fGT9?utm_source=share&utm_medium=member_desktop).

---

### Day 5: Testing and Error Handling
- Performed **functional testing** on the website, including API testing.
- Conducted **User Acceptance Testing (UAT)** to ensure the system meets business requirements.
- Implemented **error handling** for API responses and user interactions.

### Day 5: Testing, Error Handling, and UAT
- **Date**: 20-01-2025
- **Activities**:
  - Conducted **functional testing** on all aspects of the website.
  - Ran **API testing** for product fetching, order placement, and live shipment tracking.
  - Performed **User Acceptance Testing (UAT)** to ensure the platform met user expectations and business requirements.

---

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_hackathon-testingphase-innovation-activity-7287392750231023616-TUVR?utm_source=share&utm_medium=member_desktop).

---

### Day 6: Deployment and Final Documentation
- Pushed the project to **Git** and deployed it to **Vercel** for production.
- Completed the **final documentation**, including the API specifications and functionality descriptions.

---

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_hackathon-testingphase-innovation-activity-7287392750231023616-TUVR?utm_source=share&utm_medium=member_desktop).

---

