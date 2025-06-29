## Overview  
This project represents a fully operational e-commerce application, built to demonstrate key modern development practices such as the MVC pattern, structured database design, modular service architecture, and third-party payment integration. It includes critical features such as secure user authentication, a product catalog, shopping cart management, order processing, and integration with Stripe for payment handling.

## Features  
1. **User Management:**  
   - Account registration and login  
   - Role-based authorization  

2. **Product Management:**  
   - Categorized product listings with inventory tracking  
   - Support for image attachments to enhance product listings  

3. **Shopping Cart:**  
   - Add, modify, or remove items from the cart  
   - Display detailed pricing per item and total cart value  

4. **Order Management:**  
   - Submit orders and view summaries  
   - Seamless Stripe integration for processing payments securely  

5. **Payment Processing:**  
   - Stripe-based checkout sessions  
   - Graceful handling of payment success and failure events  

6. **Database Design:**  
   - Relational schema optimized using indexing and foreign keys  
   - Normalized structure ensures efficient and scalable data access  

7. **Error Handling:**  
   - Use of custom exceptions for informative error messaging  
   - Runtime errors handled in a user-friendly manner  

## Technologies Used  
1. **Backend:**  
   - Java  
   - Spring Boot (includes Controllers, Services, Repositories)

2. **Database:**  
   - MySQL with relational modeling  
   - Support for indexing and foreign key constraints  

3. **Payment Gateway:**  
   - Stripe for secure payment handling  

4. **Frontend:**  
   - Not included, but backend supports integration with modern frameworks such as React or Angular  

5. **Tools and Libraries:**  
   - Lombok to reduce boilerplate  
   - Hibernate as the ORM solution  

## Folder Structure (MVC-Oriented)  
```markdown
onlineshop
├── docs
│   ├── api-docs
│   ├── class-diagram
│   ├── shema-diagram
│   └── postman-collection
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── onlineshop
│   │   │           ├── shop
│   │   │           │   ├── common
│   │   │           │   │   ├── dtos
│   │   │           │   │   ├── exceptions
│   │   │           │   │   ├── models
│   │   │           │   ├── config
│   │   │           │   │   ├── GlobalConfig
│   │   │           │   │   ├── WebConfig
│   │   │           │   ├── data
│   │   │           │   │   ├── DataInitializer
│   │   │           │   │   ├── RoleRepository
│   │   │           │   ├── cartAndCheckout
│   │   │           │   │   ├── controllers
│   │   │           │   │   ├── dtos
│   │   │           │   │   ├── exceptions
│   │   │           │   │   ├── models
│   │   │           │   │   ├── repositories
│   │   │           │   │   └── services
│   │   │           │   ├── Auth
│   │   │           │   │   ├── – -
│   │   │           │   ├── product
│   │   │           │   │   ├── - -
│   │   │           │   ├── order
│   │   │           │   │   ├── - -
│   │   │           │   ├── user
│   │   │           │   │   ├── - -
│   │   │           └── Application.java
│   │   └── resources
│   │       ├── application.properties
│   │       └── templates
│   │           └── index.html
└── README.md
└── pom.xml
```

## Key Highlights  
1. **Stripe Integration:** Seamlessly integrated Stripe for secure and efficient payment transactions.  
2. **Scalability:** The normalized database structure is designed to accommodate growth with consistent performance.  
3. **Error Management:** Thoughtfully crafted custom exceptions enhance user understanding and experience.  
4. **Optimization Techniques:** Caching and database indexing were employed to boost performance.

## Limitations  
1. **Stripe Fees:** Stripe’s per-transaction cost may be restrictive for small-scale or low-budget applications.  
2. **Database Scalability:** In high-traffic environments, improvements like table denormalization or sharding might be necessary.  
3. **Caching Risks:** Potential issues with outdated cache content need to be managed through proper invalidation strategies.  
4. **Monitoring Tools:** While basic error handling is in place, advanced logging and monitoring tools like Sentry or ELK could enhance visibility.

## Suggestions for Improvement  
1. **Asynchronous Processing:** Introduce message queues (e.g., Kafka) to improve performance during high-load order handling.  
2. **Multi-Gateway Support:** Integrate additional payment gateways such as Razorpay or PayPal to offer more payment flexibility.  
3. **Frontend Development:** Implement a user-facing interface using frameworks like React or Angular for a complete user experience.  
4. **Enhanced Monitoring:** Use APM tools such as New Relic or Datadog to monitor performance and identify bottlenecks.

## Conclusion  
This project offered practical experience in building a scalable and maintainable e-commerce solution using contemporary development techniques. With an emphasis on modular architecture, third-party integrations, and clean code practices, it serves as a strong foundation for future enhancements. Despite a few limitations, it is well-prepared for scaling and further development.

## Getting Started

### Prerequisites  
- Java 11 or higher  
- Maven  
- Stripe account with API credentials  

### Installation  
1. Clone the repository:  
    ```sh
    git clone https://github.com/yourusername/onlineshop.git
    ```
2. Enter the project directory:  
    ```sh
    cd onlineshop
    ```
3. Install dependencies:  
    ```sh
    mvn clean install
    ```

### Configuration  
1. Update `application.properties` with database and Stripe configuration:  
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/onlineshop
    spring.datasource.username=root
    spring.datasource.password=yourpassword
    STRIPE_SECRET_KEY=your_stripe_secret_key
    baseURL=http://localhost:8080/
    ```

### Running the Application  
1. Start the application:  
    ```sh
    mvn spring-boot:run
    ```
2. Open in browser: `http://localhost:8080`

## API Endpoints

### User Management  
- `GET /api/users/{userId}/user` – Retrieve user by ID  
- `POST /api/users/add` – Register a new user  
- `PUT /api/users/{userId}/update` – Update user details  
- `DELETE /api/users/{userId}/delete` – Remove user  
- `POST /api/users/reset-password` – Trigger password reset  

### Cart and Checkout  
- `POST /api/v1/cartItems/item/add` – Add an item to the cart  
- `POST /api/v1/checkout/create-session` – Initialize checkout session  

## Contributing  
We welcome contributions! Fork the repository and create a pull request to suggest improvements.

## License  
This project is licensed under the MIT License.