# Flight Reservation System Database Application ✈️

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

The **Flight Reservation System** is a database-driven application designed to efficiently manage and streamline the operations of an airline booking process. It provides a robust backend structure to handle critical data, including flight schedules, passenger information, seat availability, ticket bookings, and payment tracking. 

This project demonstrates core relational database concepts, efficient querying, and data integrity tailored for a real-world reservation scenario.

## Key Features

*   **Flight Management:** Store and retrieve comprehensive flight details (origin, destination, departure/arrival times, aircraft type).
*   **Passenger Profiles:** Securely manage customer data, preferences, and booking history.
*   **Booking System:** Process reservations, manage booking statuses (confirmed, pending, canceled), and issue unique booking references.
*   **Seat Allocation:** Track available, reserved, and booked seats across different classes (Economy, Business, First).
*   **Payment Tracking:** Record transactions, payment methods, and billing information linked to specific bookings.
*   **Reporting:** Execute complex queries to generate insights (e.g., flights on a specific date, passenger lists, revenue summaries).

## Database Schema (ER Diagram)

*(Include an image or a link to your Entity-Relationship diagram here. E.g., `![ER Diagram](docs/er-diagram.png)`)*

### Core Entities:
*   **`Flight`**: flight_id, origin, destination, departure_time, arrival_time...
*   **`Passenger`**: passenger_id, first_name, last_name, email, passport_number...
*   **`Booking`**: booking_id, passenger_id, flight_id, booking_date, status...
*   **`Ticket`**: ticket_id, booking_id, seat_number, class, price...
*   **`Payment`**: payment_id, booking_id, amount, payment_date, method...

## Tech Stack

*(Update these based on what you actually used)*
*   **Database Engine:** PostgreSQL / MySQL / SQL Server
*   **Backend Language:** Node.js / Java / Python / C#
*   **Framework (if applicable):** Express.js / Spring Boot / Django 
*   **Database Design Tool:** dbdiagram.io / MySQL Workbench / pgAdmin

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

*   [Install PostgreSQL/MySQL](Link to installation)
*   [Install Node.js/Python/Java](Link to installation)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Nerosegnofic/Flight-Reservation-System-Database-App.git](https://github.com/Nerosegnofic/Flight-Reservation-System-Database-App.git)
    cd Flight-Reservation-System-Database-App
    ```

2.  **Database Setup:**
    *   Log in to your local database server.
    *   Execute the initialization script to create the schema and tables:
        ```bash
        # Example for MySQL
        mysql -u your_username -p < sql/schema.sql
        ```
    *   (Optional) Load the dummy data for testing:
        ```bash
        mysql -u your_username -p < sql/seed_data.sql
        ```

3.  **Application Setup (If applicable):**
    *   Install dependencies:
        ```bash
        npm install  # or pip install -r requirements.txt / mvn clean install
        ```
    *   Configure your database connection strings in the `.env` or configuration file.
    *   Run the application:
        ```bash
        npm start # or python app.py 
        ```

## Usage

*(Provide examples of how to use the app or run key SQL queries. For example:)*

**Find all available flights from JFK to LHR on 2026-10-15:**
```sql
SELECT flight_number, departure_time, available_seats
FROM Flights
WHERE origin = 'JFK' AND destination = 'LHR' 
AND DATE(departure_time) = '2026-10-15';
