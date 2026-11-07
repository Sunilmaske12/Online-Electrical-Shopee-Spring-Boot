# Online Electrical Shopee (OES)

Online Electrical Shopee (OES) is an academic e-commerce web application for browsing and purchasing electrical products. This repository contains the Spring Boot application, including its Java backend, JSP-based web pages, and static frontend assets.

## Features

- User registration, login, and account-related flows
- Product browsing and product details
- Product and category management
- Shopping cart and order placement
- Order details and invoice pages
- Razorpay test-mode payment integration
- Admin features for managing products, categories, banners, and orders
- Blog and contact pages
- Email-based OTP and password-reset flows
- Customer support and chat-related functionality

> The repository includes both server-side application code and JSP frontend views. It is not a standalone REST API backend.

## Technology Stack

- Java 17
- Spring Boot 3.1.1
- Spring MVC
- Spring Security
- Spring Data JPA / Hibernate
- MySQL
- JSP views
- HTML, CSS, and JavaScript
- Maven
- Razorpay Java SDK
- Jakarta Mail

## Project Structure

```text
OES/
├── src/
│   └── main/
│       ├── java/com/springBoot/jsp/OES/
│       │   ├── controller/       # Web request controllers
│       │   ├── dao/              # Spring Data repositories
│       │   ├── entity/           # JPA entity classes
│       │   ├── securityConfig/   # Spring Security configuration
│       │   └── service/          # Business logic and service classes
│       └── resources/
│           ├── templates/        # JSP view pages
│           ├── static/           # CSS, JavaScript, images and assets
│           └── application.properties
├── pom.xml
└── mvnw
```

## Prerequisites

- JDK 17
- Maven (or use the included Maven Wrapper)
- MySQL
- An IDE such as IntelliJ IDEA, Eclipse, or VS Code

## Database Configuration

Create a MySQL database named `springboot_oes`, or update the database name in the application configuration.

Configure the database connection in `src/main/resources/application.properties`. Use your own local credentials and do not commit passwords or other secrets.

Example configuration:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/springboot_oes
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
```

The example above is a template. Set `DB_USERNAME` and `DB_PASSWORD` in your local environment before running the application.

## External Service Configuration

The application contains email delivery and Razorpay test-payment integration. Configure email credentials and Razorpay test credentials outside the source code before using these features.

Do not publish email app passwords, API secrets, or payment credentials in the repository. Use test credentials only for development.

## Run the Application

1. Clone the repository:

   ```bash
   git clone <YOUR_REPOSITORY_URL>
   ```

2. Open the project directory:

   ```bash
   cd <repository-folder>/OES
   ```

3. Configure MySQL and the required external-service settings.

4. Run the application using the Maven Wrapper:

   **macOS / Linux**
   ```bash
   ./mvnw spring-boot:run
   ```

   **Windows**
   ```bat
   mvnw.cmd spring-boot:run
   ```

5. Open the local application using the port configured by Spring Boot (8080 by default):

   ```text
   http://localhost:8080/
   ```

If the project is imported into an IDE, run the `OesApplication` main class after configuring the database and external services.

## Build

```bash
./mvnw clean package
```

The executable JAR is generated in the `target/` directory.

## Notes

- This is an academic project and should not be considered production-ready without further security, validation, testing, and deployment work.
- The application uses JSP pages packaged with the Spring Boot project.
- Razorpay integration is intended for test-mode use unless separately configured with valid production credentials.
- Keep local configuration and secret values out of Git.

## Author

**Sunil Maske**

- GitHub: [Sunilmaske12](https://github.com/Sunilmaske12)
- LinkedIn: [sunil-maske](https://www.linkedin.com/in/sunil-maske/)
