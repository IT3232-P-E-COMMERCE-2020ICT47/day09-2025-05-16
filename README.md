
# Employee Management System

## Overview
This is a Spring Boot application for managing departments and employees in an organization. The application provides RESTful APIs to perform CRUD (Create, Read, Update, Delete) operations on department and employee data.

## Project Structure

### Models
- **Department**: Entity class representing a department with attributes such as id, name, established date, and a list of employees.
- **Employee**: Entity class representing employees (referenced in Department but not shown in the provided code).

### Repository
- **DepartmentRepo**: JPA repository interface for Department entity that extends JpaRepository to provide CRUD operations.

### Service
- **DepartmentService**: Service class that handles business logic for department operations.
  - Gets all departments
  - Gets a department by ID

### Controller
- **DepartmentController**: REST controller that handles HTTP requests for department operations.
  - GET /dept - Retrieves all departments
  - GET /dept/{id} - Retrieves a specific department by ID
  - (Commented out) POST, PUT, DELETE operations for departments

## Database Configuration
The application uses MySQL database with the following configuration:
- Database URL: jdbc:mysql://localhost:3306/employee
- Username: root
- Password: (empty)
- Hibernate DDL Auto: update (creates/updates tables automatically)

## How to Run
1. Ensure you have Java 11 or higher installed
2. Install MySQL and create a database named 'employee'
3. Configure the database connection in application.properties
4. Build the project using Maven: `mvn clean install`
5. Run the application: `mvn spring-boot:run`

## API Endpoints

### Department Endpoints
- **GET /dept**: Retrieves all departments
  - Response: List of Department objects
  - Status codes: 200 OK
 
  ![Screenshot (1123)](https://github.com/user-attachments/assets/7ad05297-50d3-4961-a57e-67adb65e93ed)


- **GET /dept/{id}**: Retrieves a specific department by ID
  - Path variable: id (Department ID)
  - Response: Department object
  - Status codes: 200 OK (if found), 404 NOT_FOUND (if not found)

  ![Screenshot (1124)](https://github.com/user-attachments/assets/478290a5-dd54-4c61-ac2d-1b40c6ccc3f6)

  ![Screenshot (1125)](https://github.com/user-attachments/assets/19b51ecc-4087-441e-9e8f-91cdcde0c79e)


### Commented Department Endpoints (Ready for Implementation)
The following endpoints are commented out in the code but ready for implementation:
- **GET /dept**: Retrieves all departments
  - Response: List of Department objects
  - Implementation: Saves the department to the database using repository
 
  ![Screenshot (1115)](https://github.com/user-attachments/assets/46bf5165-bd9b-45e3-9323-78b55d1adbf8)

  ![Screenshot (1119)](https://github.com/user-attachments/assets/cbd439a7-5532-4762-b981-294b016a290c)


- **GET /dept/{id}**: Retrieves a specific department by ID
  - Path variable: id (Department ID)
  - Response: Department object
  - Implementation: Saves the department to the database using repository
 
  ![Screenshot (1116)](https://github.com/user-attachments/assets/5ecfcf5f-8b1c-40dd-8811-85d402e2a1bd)

  ![image](https://github.com/user-attachments/assets/ae90f3a5-8e11-44fd-8f92-1a7ee3bb16fd)

- **POST /dept**: Creates a new department
  - Request body: Department object
  - Response: String message "New Department added"
  - Implementation: Saves the department to the database using repository
 
  ![Screenshot (1118)](https://github.com/user-attachments/assets/8a232627-980b-4b5f-b536-c49e4e5e7113)

  ![Screenshot (1121)](https://github.com/user-attachments/assets/bec4cc8a-6b94-4a06-92f4-7797df97450f)

- **PUT /dept/{id}**: Updates an existing department
  - Path variable: id (Department ID)
  - Request body: Updated Department object
  - Response: String message "The Department Updated" if successful, "Couldn't find the department" if not found
  - Implementation: Checks if department exists, then saves the updated department
 
    ![Screenshot (1120)](https://github.com/user-attachments/assets/21d13960-1fb9-46ae-b719-463608bd616c)

    ![image](https://github.com/user-attachments/assets/738e2e84-7933-4f1b-9f7c-f013cc8c7415)

- **DELETE /dept/{id}**: Deletes a department
  - Path variable: id (Department ID)
  - Response: String message "The Department Deleted" if successful, "Couldn't find the department" if not found
  - Implementation: Checks if department exists, then deletes the department by ID
 
   ![Screenshot (1122)](https://github.com/user-attachments/assets/9667befc-becd-4753-9b69-4121dee73aa7)

   ![image](https://github.com/user-attachments/assets/02e92387-6a7c-42b4-b32f-181221b100f4)

## Entity Relationships
- A Department has many Employees (One-to-Many relationship)
- The relationship is mapped by the 'department' field in the Employee entity

## Notes
- The Department Controller includes two implementation approaches:
  1. Current active implementation using a service layer (DepartmentService)
  2. Commented out direct repository implementation that can be uncommented for simpler usage
- The commented implementation provides full CRUD operations (GET, POST, PUT, DELETE)
- To use the commented implementation, uncomment the code in DepartmentController and comment out the current service-based implementation
- Consider implementing proper exception handling and validation for production use
- Future development could include implementing the Employee entity and related endpoints

## Dependencies
- Spring Boot
- Spring Data JPA
- MySQL Connector
- Jakarta Persistence API

## Contributors
[Your Name/Team]

## License
[Your License]
