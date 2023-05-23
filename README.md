# Hotel-Management-System-NodeJS-MYSQL

## DBMS Mini Project

### Team Members<a name="team-members"></a>

- Gopal Saraf: [github.com/GopalSaraf](https://github.com/GopalSaraf)
- Parth Sali: [github.com/parthsali](https://github.com/parthsali)
- Riddhi Sabane: [github.com/sabaneriddhi](https://github.com/sabaneriddhi)
- Vaishnavi Shinde: [github.com/vaish2022](https://github.com/vaish2022)

### Introduction

The hotel management system database is designed to store information related to hotel administration, user bookings, room categories, and user details. It provides functionality for managing bookings, room availability, and user information within a hotel.

### Entity-Relationship Diagram (ERD)

The ERD below illustrates the relationships between the entities in the hotel management system database:

![Hotel Management System ERD]()

### Entities and Attributes

1. **Admin**

   - `name` (varchar, primary key): The name of the admin.
   - `pass` (varchar): The password of the admin account.

2. **BookingStatus**

   - `email` (varchar, foreign key): The email of the user making the booking.
   - `category` (varchar): The category of the booked room.
   - `type` (varchar): The type of the booked room.
   - `roomWant` (int): The number of rooms requested.
   - `status` (int): The status of the booking (0 for pending, 1 for confirmed, etc.).
   - `date` (date): The date of the booking.

3. **Category**

   - `name` (varchar, primary key): The name of the room category.
   - `type` (varchar, primary key): The type of the room.
   - `cost` (int): The cost of the room.
   - `available` (int): The number of available rooms in this category.
   - `img` (varchar): The image path of the room category.
   - `dec` (varchar): Description of the room category.

4. **User**
   - `name` (varchar): The name of the user.
   - `email` (varchar, primary key): The email of the user.
   - `phone` (varchar): The phone number of the user.
   - `password` (varchar): The password of the user.

### Tables and Relationships

- The `admin` table stores information about the hotel administrators. It has a one-to-one relationship with the `user` table based on the `email` field.

- The `bookingstatus` table keeps track of the bookings made by users. It has a many-to-one relationship with the `user` table based on the `email` field.

- The `category` table contains information about the room categories available in the hotel. It has a one-to-many relationship with the `bookingstatus` table based on the `category` field.

- The `user` table stores user information such as name, email, phone number, and password. It has a one-to-many relationship with both the `bookingstatus` table (based on the `email` field) and the `admin` table (based on the `email` field).

### SQL Statements

The provided SQL statements include the creation of tables, insertion of sample data, and necessary indexes and constraints.

- Table creation statements:

  - `admin`: Stores admin information.
  - `bookingstatus`: Keeps track of booking information.
  - `category`: Contains room category details.
  - `user`: Stores user information.

- Sample data insertion statements:

  - `admin`: Inserts an admin account with the name 'admin' and password 'admin'.
  - `bookingstatus`: Inserts a sample booking made by a user.
  - `category`: Inserts room category information.
  - `user`: Inserts user information, including admin and regular user accounts.

- Indexes and constraints:
  - Indexes are created on the primary key fields of each table.
  - A foreign key constraint is added to the `bookingstatus` table referencing the `user` table.

### Conclusion

This documentation provides an overview of the hotel management system database, including its entities, relationships, and SQL statements for table creation, data insertion, indexes, and constraints. You can use this as a reference to understand the structure and functionality of the database and build upon it for your college DBMS mini project.
