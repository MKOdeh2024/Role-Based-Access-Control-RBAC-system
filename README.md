## Role-Based Access Control (RBAC) with TypeORM and Express.js

In this project, you will build an RBAC system using TypeORM and Express.js, allowing for the creation and management of Users, Roles, and Permissions.

### Entities

#### User
- **Attributes**:
  - `id`: primary key
  - `username`
  - `password`
  - `email`
  - ...and more
- **Relationship**:
  - Many-to-Many with `Role` entity
  - One-to-One with `Profile` entity

#### Role
- **Attributes**:
  - `id`: primary key
  - `name`: e.g., "admin", "user", "editor"
- **Relationship**:
  - Many-to-Many with `User` entity
  - Many-to-Many with `Permission` entity

#### Permission
- **Attributes**:
  - `id`: primary key
  - `name`: e.g., "create_post", "edit_user", "delete_comment"
- **Relationship**:
  - Many-to-Many with `Role` entity

#### Profile
- **Attributes**:
  - `id`: primary key
  - `firstName`
  - `lastName`
  - `dateOfBirth`
  - ...and more
- **Relationship**:
  - One-to-One with `User` entity

### API Endpoints:
- Create User
- Create Permission
- Create Role (Set permissions of the role while creating the role)
- Assign Role to User
- Get User (with his roles and permissions)

### Project Setup:

#### Prerequisites:
- Node.js
- TypeORM
- Express.js
- AWS RDS (For database)

#### Instructions:

1. **Initialize your project**:
   ```bash
   npm init
   - Install necessary packages:
bash
 - Copy code
npm install express typeorm pg reflect-metadata
- Setup TypeORM:
- Create an ormconfig.json at the root of your project.
- Configure it to connect to your AWS RDS PostgreSQL instance.
- Create Entity files:
- Create entities for User, Role, Permission, and Profile in a /entities folder.
- Set up Express.js:
  - Create your server file, e.g., server.js.
  - Define your routes and controllers for the above-mentioned API endpoints.
  - Run migrations:
bash
Copy code
typeorm migration:run
  - Start your server:
bash
- Copy code
node server.js
 - Submissions:
   - Create a GitHub repository for your project.
   - Commit and push your code.
  -  Include a README.md file with detailed instructions on setting up and running your application.
   -  Submit the GitHub repository link along with any additional documentation.
```
