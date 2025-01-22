# E-Commerce Furniture Project

This project is an e-commerce platform that sells trendy, Pinterest-inspired, and affordable furniture. The website is built using **Next.js 14** and **TypeScript** and integrates **Sanity** for data management. The system supports both **user** and **admin** functionalities, including managing products, tracking shipments, placing orders, and more.

---

### Day 2: Technical Documentation and System Architecture
- **Date**: 17-01-2025
- **Activities**:
  - **Technical Requirements**: Listed the technical dependencies, frameworks, and libraries for the project.
  - **System Architecture Design**: Designed the system architecture including backend services, database structure, and APIs.
  - **API Specification**: Defined the APIs that would be used for product management, order placement, and shipment tracking.

---

### Day 3: API Integration and Data Fetching
- **Date**: 18-01-2025
- **Activities**:
  - Integrated APIs for product management and data fetching from **Sanity**.
  - Developed the system to fetch product data and dynamically display it on the website.
  - Uploaded product data to **Sanity** and set up a migration utility for seamless updates.
  
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

```` json
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



````
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

````json
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

````

### Summary of APIs
**/api/products:** Fetches product details.
**/api/shipments/:** Creates a shipment and retrieves a tracking number.
**/api/tracks/{carrier}/{trackingNumber}:** Fetches live tracking details for the shipment.

- **Social Media**:
  - The day’s progress was shared on [LinkedIn](https://www.linkedin.com/posts/shoaibmunir88_hackathon-webdevelopment-marketplaceproject-activity-7285915162400727040-H83c?utm_source=share&utm_medium=member_desktop).

