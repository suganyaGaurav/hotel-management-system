`PROJECT_NOTES.md`

# Project Notes – Hotel Management System

## Purpose of This File
This document explains **how the system works internally** and **why specific design choices were made**.  
It is intended to provide clarity for reviewers, learners, and interview discussions.

---

## System Flow (High-Level)
1. User interacts with the system through a menu-driven interface.
2. Based on the selected option, the corresponding function is executed.
3. Data is updated in in-memory data structures.
4. Control returns to the main menu until the user exits.

The entire system is controlled through a single Python file to keep the learning focus simple and transparent.

---

## Data Design & State Management
The system uses **Python dictionaries and lists** to store and manage state:

- `room_no`  
  Stores allocated room numbers per room category.

- `records`  
  Stores customer booking details indexed by customer ID.

- `billamounts`  
  Tracks the total bill amount for each customer.

### Why In-Memory Storage?
- Simpler for learning purposes
- No dependency on databases
- Helps understand how state is managed programmatically

---

## Booking Logic
- Users enter check-in and check-out dates.
- Dates are validated using the `datetime` module.
- The system ensures checkout is after check-in.
- Room numbers and customer IDs are generated randomly and checked for uniqueness.
- Booking details are stored immediately after successful validation.

---

## Validation Logic
Validation is an important focus of this project:

- **Date Validation**
  - Uses `datetime` to compare check-in and check-out dates.

- **Name Validation**
  - Ensures only alphabetic characters and spaces using Regular Expressions.

- **Phone Number Validation**
  - Ensures a valid 10-digit Indian mobile number format.

This simulates basic real-world data validation requirements.

---

## Room Service & Restaurant Logic
- Room services such as laundry and cleaning add fixed or calculated costs.
- Restaurant menu items are stored with prices.
- Food orders are processed interactively.
- Food bills are added to the customer’s total bill.

---

## Billing Logic
- Room charges are calculated based on:
  - Room type
  - Number of days stayed
- Additional services and food charges are accumulated.
- Final bill is generated per customer ID.

---

## Design Decisions
- **Single Python File**:  
  Chosen to keep the learning process straightforward and traceable.

- **Menu-Driven Interface**:  
  Helps simulate real system interaction without UI complexity.

- **Functions for Each Feature**:  
  Encourages modular thinking even within a single file.

---

## Known Limitations
- No data persistence (data resets on program exit)
- No authentication or authorization
- No concurrency handling
- Not optimized for large-scale use

---

## Future Improvements (Conceptual)
If extended to a real-world system:
- Introduce database storage
- Add user authentication
- Implement GUI or web interface
- Improve error handling and logging
- Modularize into multiple files

---

## Summary
This project focuses on **clarity, logic, and foundational system design** rather than scale or production complexity.  
It reflects a disciplined learning approach to building software systems using core Python concepts.
