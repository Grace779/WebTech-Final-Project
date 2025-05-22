E-Commerce Web Application
Project Overview
This is a simple e-commerce web application developed as a mini-project for the Web Technology & Internet (INSY-413) course at the Faculty of Information Technology. The application uses Spring Boot for the backend and Thymeleaf for the frontend, with a focus on implementing core e-commerce functionalities such as product browsing, shopping cart management, user authentication, and order processing. It also includes admin features for managing products and orders.
The application meets the following user stories:

Customer: Browse products, view product details, add products to the shopping cart, view cart, proceed to checkout, and register/login to manage orders.
Admin: Add and manage products, view and update order statuses.

Technology Stack

Backend: Spring Boot, Spring Data JPA, Spring Security
Frontend: Thymeleaf, Spring MVC, Bootstrap (for styling)
Database: PostgreSQL (configurable for MySQL or other databases)
Build Tool: Maven
Deployment: Heroku (or specify your chosen cloud platform)

Features
Backend (Spring Boot)

User Roles: Defined USER and ADMIN roles with restricted access using Spring Security.
Product Management: RESTful APIs for CRUD operations on products (create, read, update, delete).
Order Management: APIs for placing orders and viewing order history, with relationships between User, Product, and Order entities.
Database: Configured with Spring Data JPA for PostgreSQL, handling product and user data.
Error Handling: Comprehensive error handling with meaningful JSON responses for API calls.

Frontend (Thymeleaf)

UI Components: Product listing, product details, shopping cart, user authentication (login/signup), and order management pages.
Styling: Bootstrap for responsive and modern UI design.
API Integration: Fetches product data, handles user authentication, and manages orders via backend APIs.
Cart Functionality: Add/remove products from the cart, calculate totals, and proceed to checkout.
Input Validation: Server-side validation using Spring validations to ensure data integrity.
Static Resources: CSS and JavaScript files for enhanced interactivity and styling.

Additional Features

Error Handling: User-friendly error messages displayed on the frontend and proper exception handling in the backend.
Deployment: Deployed on Heroku (or specify your platform) for public access.
Source Code: Hosted on GitHub with public access.

Prerequisites
To run this project locally, ensure you have the following installed:

Java: JDK 17 or higher
Maven: For dependency management and building the project
PostgreSQL: Database server (or configure for MySQL)
Git: For cloning the repository
IDE: IntelliJ IDEA, Eclipse, or any Java-compatible IDE
Heroku CLI: For deployment (if using Heroku)

Setup Instructions

Clone the Repository:
git clone https://github.com/Grace779/WebTech-Final-Project.git
cd WebTech-Final-Project


Configure the Database:

Install PostgreSQL and create a database (e.g., ecommerce_db).
Update the application.properties file in src/main/resources with your database credentials:spring.datasource.url=jdbc:postgresql://localhost:5432/ecommerce_db
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect




Build the Project:
mvn clean install


Run the Application:
mvn spring-boot:run

The application will start on http://localhost:8080.

Access the Application:

Open a browser and navigate to http://localhost:8080.
Use the following default credentials for testing:
User: user@example.com / password
Admin: admin@example.com / admin123




Deploy to Heroku (optional):

Log in to Heroku:heroku login


Create a Heroku app:heroku create


Configure the Heroku PostgreSQL add-on:heroku addons:create heroku-postgresql:hobby-dev


Push to Heroku:git push heroku main


Open the deployed app:heroku open





Project Structure
WebTech-Final-Project/
├── src/
│   ├── main/
│   │   ├── java/com/sda/java3/ecommerce/
│   │   │   ├── config/               # Spring Security configuration
│   │   │   ├── controller/           # REST and MVC controllers
│   │   │   ├── entity/              # JPA entities (Product, User, Order)
│   │   │   ├── repository/          # Spring Data JPA repositories
│   │   │   ├── service/             # Business logic and services
│   │   │   └── ECommerceApplication.java  # Main application class
│   │   ├── resources/
│   │   │   ├── static/              # CSS, JavaScript, and other static resources
│   │   │   ├── templates/           # Thymeleaf templates
│   │   │   └── application.properties  # Configuration file
├── pom.xml                          # Maven dependencies
└── README.md                        # This file

How to Use

Browse Products: Navigate to the homepage (/) to view all products.
Add to Cart: Click "Add to Cart" on a product to include it in your shopping cart.
View Cart: Go to /cart to see your cart and proceed to checkout.
User Authentication: Register at /signup or log in at /login.
Admin Features: Log in as an admin to access /admin for product and order management.

Error Handling

Frontend: Displays user-friendly messages for invalid inputs or failed actions (e.g., incorrect login credentials).
Backend: Returns appropriate HTTP status codes (e.g., 400 for bad requests, 401 for unauthorized access) with JSON error messages.

GitHub Repository
The source code is publicly available at:https://github.com/Grace779/WebTech-Final-Project
Submission
This project has been submitted via Google Classroom under the assignment link:https://classroom.google.com/c/Nzc3NTAxMTgwNjMw/a/Nzc3NTAxNDA1NjEz/details
Troubleshooting

Database Connection Issues: Ensure PostgreSQL is running and the application.properties file has correct credentials.
Dependency Errors: Run mvn clean install to resolve missing dependencies.
Push Errors: If you encounter src refspec main does not match any, ensure you have committed changes and are on the main branch:git add .
git commit -m "Initial commit"
git push -u origin main



Future Improvements

Add payment gateway integration for real transactions.
Implement advanced search and filtering for products.
Enhance UI with more interactive features using JavaScript frameworks.

