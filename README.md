# Railway_Reservation_System

THIS IS A VERY SIMPLE RAILWAY RSESERVATION SYSTEM PROJECT USING  ONLY JAVA

# Railway Reservation System

## Description
This project is a console-based **Railway Reservation System** implemented in Java. It provides functionalities for booking tickets, canceling reservations, and checking the availability of tickets. The system is designed to manage ticket allocations across different preferences (Lower, Middle, Upper berths, RAC, and Waiting List) effectively.

---

## Features
1. **Ticket Booking**:
   - Books tickets based on the passenger's berth preference (Lower, Middle, or Upper berth).
   - Automatically allocates alternative berths if the preferred berth is unavailable.
   - Supports RAC (Reservation Against Cancellation) and Waiting List management.

2. **Ticket Cancellation**:
   - Cancels a ticket based on a unique Passenger ID.
   - Updates the system to allocate the canceled berth to RAC or waiting list passengers.

3. **View Available Tickets**:
   - Displays the current availability of berths (Lower, Middle, Upper), RAC tickets, and waiting list slots.

4. **View Booked Tickets**:
   - Lists all booked tickets with details such as passenger name, age, and allocated berth.

5. **User-Friendly Console Interface**:
   - Simple menu-driven interface with options to book, cancel, and view tickets.

---

## How It Works
1. **Passenger Class**:
   - Represents passenger details, including name, age, and berth preference.

2. **TicketBooker Class**:
   - Handles ticket allocation, RAC management, and waiting list logic.
   - Maintains the available count and passenger details in a centralized map.

3. **Main Class**:
   - Acts as the entry point for the application.
   - Provides a menu for user interaction:
     - **Option 1**: Book a ticket.
     - **Option 2**: Cancel a ticket.
     - **Option 3**: Check available tickets.
     - **Option 4**: View booked tickets.
     - **Option 5**: Exit the program.

---

## Requirements
- **Programming Language**: Java
- **Tools**: 
  - Java Development Kit (JDK)
  - IDE (e.g., IntelliJ IDEA, Eclipse)

---

## Usage
1. **Run the Program**:
   - Compile and execute the `Main.java` file.
   - Use the provided menu options to perform actions such as booking and canceling tickets.

2. **Booking Logic**:
   - Enter passenger details (name, age, and berth preference).
   - The system assigns a berth based on availability.

3. **Cancellation Logic**:
   - Provide the passenger ID for cancellation.
   - The system reassigns the canceled berth to RAC or waiting list passengers.

---
# Railway Reservation System

## Description
This **Railway Reservation System** is implemented in Java and comprises two main classes: `Main` and `TicketBooker`. Below is the description of each component:

---

### Main Class
1. **Purpose**:  
   Acts as the entry point of the application. It provides a console-based user interface for the system. Users can:
   - Book tickets.
   - Cancel reservations.
   - View available tickets.
   - Check booked ticket details.

2. **Key Methods**:
   - `bookTicket(Passenger p)`: Handles ticket booking based on preferences and availability.
   - `cancelTicket(int id)`: Allows ticket cancellation using the Passenger ID.
   - `main(String[] args)`: Provides a menu-driven interface for user interactions.

---

### TicketBooker Class
1. **Purpose**:  
   Manages ticket allocation, RAC, and waiting list functionalities. It maintains the state of ticket availability and passenger details.

2. **Key Features**:
   - **Available Berths**:
     - Tracks the number of available berths (Lower, Middle, Upper).
     - Supports RAC (Reservation Against Cancellation) and Waiting List management.
   - **Passenger Management**:
     - Stores passenger details in a `Map` with Passenger ID as the key.
     - Provides methods to book, cancel, and retrieve passenger information.

3. **Important Methods**:
   - `bookTicket(Passenger p, int berthInfo, String allottedBerth)`: Allocates a berth to a passenger and updates the system.
   - `bookRAC(Passenger p, int berthPref, String allottedBerth)`: Adds a passenger to the RAC queue.
   - `addToWait(Passenger p, int berthPref, String allottedBerth)`: Adds a passenger to the waiting list.
   - `cancelTicket(int id)`: Handles ticket cancellation, reallocates berths, and moves passengers from RAC or waiting list to confirmed.
   - `printAvailable()`: Displays the current status of available berths, RAC, and waiting list.
   - `printBooked()`: Displays details of all booked passengers.

4. **Data Structures Used**:
   - **Queues**:
     - `waitList`: Manages passengers in the waiting list.
     - `racList`: Manages passengers in the RAC queue.
   - **Lists**:
     - `bookedList`: Tracks confirmed passenger IDs.
     - `lbPos`, `mbPos`, `ubPos`, `racPos`, `waitPos`: Store available positions for berths and RAC/waiting slots.
   - **Map**:
     - `passengers`: Maps Passenger IDs to their details.

---

### Flow of Operations
1. **Booking**:
   - The system attempts to allocate the preferred berth type.
   - If unavailable, it assigns alternative berths, RAC, or a waiting list slot.
2. **Cancellation**:
   - Frees up the allocated berth and reassigns it to RAC or waiting list passengers, ensuring optimal utilization.
3. **Display**:
   - Provides real-time status of ticket availability and booked passenger details.

---

This system is designed to simulate a real-world railway reservation process, focusing on managing berth preferences, handling cancellations efficiently, and ensuring dynamic allocation of available resources.


# PASSENEGER JAVA
The Passenger class represents a passenger in a reservation system with the following details:

Attributes:
1. Static Field:
   - id: A static integer that starts at 1 and provides a unique ID for each passenger.

2. Instance Fields:
   - name: The passenger's name (String).
   - age: The passenger's age (int).
   - berthPref: The passenger's preferred berth (String).
   - passId: A unique passenger ID assigned using the static id field.
   - alloted: The assigned berth or seat for the passenger, initialized as an empty string (String).
   - seatNum: The seat number assigned to the passenger, initialized to -1 (int).

Constructor:
- The constructor accepts name (String), age (int), and berthPref (String) as parameters. It initializes the instance fields, assigns a unique ID using the static id, and sets default values for alloted and seatNum.

Purpose:
This class is useful for applications like reservation systems to store and manage passenger details, including their preferences and seat assignments.
