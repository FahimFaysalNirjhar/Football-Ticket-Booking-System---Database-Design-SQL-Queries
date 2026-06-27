# ⚽ Football Ticket Booking System

A PostgreSQL-based Football Ticket Booking System designed to manage football fans, match information, and ticket bookings. This project demonstrates database design, ERD modeling, relational integrity, and SQL query implementation.

## 👨‍💻 Author

**Fahim Faysal Nirjhar**  
Software Engineer

GitHub: https://github.com/FahimFaysalNirjhar

---

# 📌 Project Overview

The Football Ticket Booking System allows:

- Football fans to book tickets for matches.
- Ticket managers to manage match ticket availability.
- Tracking of bookings and payment statuses.
- Maintaining relational integrity between users, matches, and bookings.

---

# 🏗️ Database Schema

The database consists of three tables:

## 1. Users

Stores all registered users and administrators.

| Column       | Description                   |
| ------------ | ----------------------------- |
| user_id      | Unique user identifier        |
| full_name    | User's full name              |
| email        | User email address            |
| role         | Football Fan / Ticket Manager |
| phone_number | Contact number                |

---

## 2. Matches

Stores football match information.

| Column              | Description                                  |
| ------------------- | -------------------------------------------- |
| match_id            | Unique match identifier                      |
| fixture             | Match fixture                                |
| tournament_category | Tournament name                              |
| base_ticket_price   | Base ticket price                            |
| match_status        | Available, Selling Fast, Sold Out, Postponed |

---

## 3. Bookings

Stores ticket booking transactions.

| Column         | Description                             |
| -------------- | --------------------------------------- |
| booking_id     | Unique booking identifier               |
| user_id        | References Users                        |
| match_id       | References Matches                      |
| seat_number    | Reserved seat                           |
| payment_status | Pending, Confirmed, Cancelled, Refunded |
| total_cost     | Final ticket cost                       |

---

# 🔗 Entity Relationship Diagram (ERD)

Relationships:

### One-to-Many

```text
Users (1) --------< Bookings (Many)
```

One user can make multiple bookings.

### Many-to-One

```text
Bookings (Many) >-------- (1) Matches
```

Many bookings can belong to a single match.

---

# 🛠️ Technologies Used

- PostgreSQL
- SQL
- Draw.io / Lucidchart (ERD Design)
- Git & GitHub

---

# 📂 Project Structure

```text
Football-Ticket-Booking-System/
│
├── README.md
├── schema.sql
├── sample_data.sql
├── queries.sql
└── ERD/
    └── football_ticket_booking_erd.png
```

---

# 📊 SQL Queries Implemented

### Query 1

Retrieve available Champions League matches.

### Query 2

Search users using LIKE and ILIKE.

### Query 3

Handle NULL payment statuses using COALESCE.

### Query 4

Retrieve booking details using INNER JOIN.

### Query 5

Display all users including those without bookings using LEFT JOIN.

### Query 6

Find bookings whose cost exceeds the average booking cost using a subquery.

### Query 7

Retrieve the top 2 expensive matches while skipping the most expensive match using LIMIT and OFFSET.

---

# 🔐 Database Constraints

Implemented:

- Primary Keys
- Foreign Keys
- Unique Constraints
- Check Constraints
- NOT NULL Constraints

Examples:

```sql
CHECK (role IN ('Football Fan', 'Ticket Manager'))

CHECK (match_status IN
('Available','Selling Fast','Sold Out','Postponed'))

CHECK (total_cost >= 0)
```

---

# 🚀 How to Run

### Create Database

```sql
CREATE DATABASE football_ticket_booking;
```

### Connect Database

```sql
\c football_ticket_booking
```

### Execute Schema

```sql
\i schema.sql
```

### Insert Sample Data

```sql
\i sample_data.sql
```

### Run Queries

```sql
\i queries.sql
```

---

# 📸 Deliverables

- ERD Design
- PostgreSQL Database Schema
- Sample Data
- SQL Queries
- GitHub Repository
- Interview Video

---

# 🎯 Learning Outcomes

This project demonstrates:

- Relational Database Design
- Entity Relationship Modeling
- SQL Query Writing
- JOIN Operations
- Aggregate Functions
- Subqueries
- Data Integrity Constraints
- Database Normalization

---

## ⭐ Acknowledgement

Developed as part of a Database Management System (DBMS) assignment to demonstrate practical database design and SQL querying skills.

---

### Thank You ❤️

If you found this project useful, consider giving it a ⭐ on GitHub.
