# BuySphere API  

BuySphere API is a backend service for a user-driven marketplace platform. It supports product management, user authentication, community-based listings, and more.  

## 🚀 Getting Started  

### Prerequisites  
Before getting started, make sure you have the following installed:  
- **Java** >= version 17 
- **Database**: PostgreSQL or compatible SQL database
- **JDK**: Coretto 21
- **Build tool**: Maven

### Installation  

1. **Clone the Repository**

   Clone the project repository to your local machine:
   ```bash
   git clone https://github.com/DavidPerez-2357/BuySphere-API.git

2. **Set Up Environment Variables**

   To configure the necessary environment variables, follow these steps (example for IntelliJ IDEA):

   - In the top right corner, click on the application name > `Edit Configurations`.
   - Click on `Modify options` and enable the "Environment variables" checkbox.
   - In the Environment variables input, click the last icon to open the input field.
   - Add the following environment variables with their **name** and **value**:

   
     | Name                 | Description                                                                                           |
     |----------------------|-------------------------------------------------------------------------------------------------------|
     | `DATABASE_URL`        | The connection string for the database, including the database type, host, port, and database name.   |
     | `DATABASE_USERNAME`   | The username used to authenticate to the database.                                                    |
     | `DATABASE_PASSWORD`   | The password associated with the database username for authentication.                                |
     | `PORT`                | The port number the application will listen on for incoming network requests.                         |


## 🚪 API Endpoints

### Authentication Routes

- **POST** `/auth/login`  
  Logs in a user and returns a JWT token.  
  **Permissions**: Public (no authentication required).

- **POST** `/auth/register`  
  Registers a new user.  
  **Permissions**: Public (no authentication required).

### User Routes  

- **GET** `/users`  
  Fetches a list of all users.  
  **Permissions**: **ADMIN** only.

- **POST** `/users`  
  Creates a new user.  
  **Permissions**: Public (no authentication required, but only for registration).

- **PUT** `/users/{id}`  
  Modify a specific user by ID.  
  **Permissions**: Authenticated user (can only modify their own user) or **ADMIN**.

- **GET** `/users/{id}`  
  Retrieves details of a specific user by ID.  
  **Permissions**: Authenticated user (can only view their own user) or **ADMIN**.

### Product Routes

- **GET** `/products`  
  Fetches a list of all products.  
  **Permissions**: Public (no authentication required).

- **POST** `/products`  
  Creates a new product.  
  **Permissions**: Authenticated user (**ADMIN** or user who created the product).

- **PUT** `/products/{id}`  
  Modify a specific product by ID.  
  **Permissions**: Authenticated user (can modify their own products) or **ADMIN**.

- **GET** `/products/{id}`  
  Retrieves details of a specific product by ID.  
  **Permissions**: Public (no authentication required).
