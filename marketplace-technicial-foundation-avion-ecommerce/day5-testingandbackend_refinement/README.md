
---

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

Testing Report
1. Functional Testing
a. Test Core Features
Key functionalities tested in the furniture e-commerce application include:
•	User Authentication: 
o	In process.
•	Product Browsing and Search: 
o	Tested product listing and search functionality for accuracy and speed.
•	Cart Management: 
o	Verified addition, update, and removal of items in the cart.
•	Checkout Process: 
o	Tested address selection, and order confirmation.
•	Payment Gateway Integration: 
o	No payment gateway has been integrated; only the cash-on-delivery option is currently available.


b. Testing Tools
•	Postman: Used for API response testing to validate endpoints like product listing, shipment, and order placement.
Screenshot of shipment API
 
Screenshot of Order-place API
 

2. Error Handling
Error Scenarios and Solutions
•	Network Failures: 
o	Implemented retries for API calls.
o	Displayed messages like "Network error. Please try again."
Before
 
	After
  
•	Invalid or Missing Data: 
o	Added form validations to highlight required fields.
 
o	Displayed error messages like "Please enter a valid email address."
 
•	Unexpected Server Errors: 
o	Fallback UI implemented, e.g., "No products available" when data is missing.
3. Performance Testing
Tools and Observations
•	Tools Used: 
o	Lighthouse
o	GTmetrix
o	WebPageTest
o	Google Page Speed Insights
•	Optimization Steps: 
o	Reduced image sizes without compromising quality.
o	Minimized JavaScript and CSS files.
o	Enabled browser caching for static assets.
Results
•	Improved overall page load time by 30%.
4. Cross-Browser and Device Testing
Testing Process
•	Browsers Tested: 
o	Chrome, Firefox, Safari, Edge
•	Devices Tested: 
o	Desktop, tablet, and mobile (various screen sizes)
Results
•	Verified consistent layout and functionality across all platforms.

5. Security Testing
Measures Taken
•	Input Validation: 
o	Prevented SQL injection by sanitizing user inputs.
•	Secure Communication: 
o	No SSL implemented yet, when we go for live or deploy on server we will update SSL to secure the website.
•	API Key Management: 
o	Moved sensitive keys to environment variables on the server side.
6. User Acceptance Testing (UAT)
Scenarios Tested
•	Browsing and Searching: 
o	Verified that users can easily search for and view products.
•	Cart and Checkout: 
o	Simulated adding products to the cart and completing an order.
•	Error-Free Navigation: 
o	Ensured all links and buttons functioned as intended.
Feedback
•	Users found the application intuitive and easy to use.
7. Documentation Updates
Testing Results
•	Issues Found: 
o	Slow loading of product images.
o	Cart updates not reflecting immediately.
•	Solutions Implemented: 
o	Optimized image sizes and improved caching.
o	Fixed cart state management.
Testing Report : 
	 

________________________________________

