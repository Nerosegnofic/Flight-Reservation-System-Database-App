# Flight Reservation System Database Application ✈️

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

The **Flight Reservation System** is a robust backend architecture built to manage the complex data workflows of modern airline booking systems. This database-driven application is designed to efficiently handle flight scheduling, passenger profiles, seat allocations, and secure payment tracking.

This project serves as a practical implementation of relational database design, focusing on data integrity, efficient indexing, and complex querying for a real-world ticketing scenario.

## Key Features

*   **Fleet & Route Management:** Maintain detailed records of flight origins, destinations, schedules, and aircraft specifications.
*   **Customer Identity Management:** Securely store passenger demographics, contact information, and historical travel data.
*   **Reservation Engine:** Track the entire lifecycle of a booking (pending, confirmed, canceled) and generate unique reservation references.
*   **Dynamic Seat Allocation:** Monitor real-time availability across various cabin classes (Economy, Business, First Class) to prevent double-booking.
*   **Transaction Logging:** Record payment statuses, billing amounts, and transaction methods linked to individual reservations.
*   **Operational Analytics:** Utilize advanced SQL queries to generate insights on daily flight manifests, revenue streams, and route popularity.

## Database Schema (ER Diagram)

*(Include an image or a link to your Entity-Relationship diagram here. E.g., `![ER Diagram](docs/er-diagram.png)`)*

### Core Entities:
*   **`Flight`**: flight_id, origin, destination, departure_time, arrival_time...
*   **`Passenger`**: passenger_id, first_name, last_name, email, passport_number...
*   **`Booking`**: booking_id, passenger_id, flight_id, booking_date, status...
*   **`Ticket`**: ticket_id, booking_id, seat_number, cabin_class, price...
*   **`Payment`**: payment_id, booking_id, amount, payment_date, method...

## Tech Stack

*   **Database Engine:** PostgreSQL / MySQL / SQL Server
*   **Backend Environment:** Node.js / Java / Python 
*   **Framework Options:** Express.js / Spring Boot / Django 
*   **Database Design Tools:** dbdiagram.io / MySQL Workbench / pgAdmin

## Getting Started

Follow these instructions to configure the database schema and application environment on your local machine.

### Prerequisites

*   A local relational database server ([PostgreSQL](https://www.postgresql.org/download/) or [MySQL](https://dev.mysql.com/downloads/))
*   A backend runtime environment ([Node.js](https://nodejs.org/), [Java](https://www.oracle.com/java/technologies/downloads/), or [Python](https://www.python.org/downloads/))

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Nerosegnofic/Flight-Reservation-System-Database-App.git
    cd Flight-Reservation-System-Database-App
    ```

2.  **Database Setup:**
    *   Log into your local SQL server.
    *   Run the provided initialization script to build the schema:
        ```bash
        # Example for MySQL
        mysql -u your_username -p < sql/schema.sql
        ```
    *   (Optional) Populate the database with test data:
        ```bash
        mysql -u your_username -p < sql/seed_data.sql
        ```

3.  **Application Setup:**
    *   Install backend dependencies:
        ```bash
        npm install  # For Node.js environments
        # or pip install -r requirements.txt for Python
        # or mvn clean install for Java
        ```
    *   Update your `.env` or configuration file with the correct database credentials.
    *   Launch the application server:
        ```bash
        npm start 
        # or python app.py 
        ```

## Usage

**Example Query: Find all available flights from JFK to LHR on October 15, 2026:**
```sql
SELECT flight_number, departure_time, available_seats
FROM Flights
WHERE origin = 'JFK' 
  AND destination = 'LHR' 
  AND DATE(departure_time) = '2026-10-15';
