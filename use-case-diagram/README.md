Use Case Diagram Guide for Airbnb Clone Backend
This guide details the Actors and Use Cases derived from the system features, which should be used to construct the final visual Use Case Diagram in Draw.io.

1. Actors
Actor

Description

Key Responsibilities (High-Level)

Guest

Any registered user whose primary goal is to search, book, and review properties.

Search, Book, Pay, Review, Message.

Host

A registered user who owns and manages property listings.

Manage Properties, Approve Bookings, Message.

Admin

A user with elevated privileges for system oversight and management.

Delete/Deactivate Listings, Modify Booking Status, View Audit Logs.

System

Handles automatic processing, validation, and integrity checks (e.g., payment gateway interactions).

Price calculation, Availability checks, Payment integrity.

2. Primary Use Cases
Module

Use Case

Actors

Includes/Extends

Authentication

Register Account

Guest, Host, Admin





Login/Logout

Guest, Host, Admin



Property

Search and View Listings

Guest





Create/Update Listing

Host





Manage Listing (Deactivate/Delete)

Host, Admin



Booking

Create Reservation Request

Guest

Includes: Check Availability, Calculate Total Price



Manage Booking Status

Host, Admin





View Booking History

Guest



Payment

Submit Payment

Guest

Includes: Record Payment

Review

Submit Property Review

Guest

Includes: Rating Validation

Messaging

Send Message

Guest, Host





View Message Inbox/Outbox

Guest, Host



3. System-Driven Use Cases (Implicit)
These use cases run automatically to support the primary user actions:

Check Availability: (Included by Create Reservation Request) Validates dates against existing confirmed bookings.

Calculate Total Price: (Included by Create Reservation Request) Determines final cost based on dates and per-night price.

Enforce Payment Integrity: (Included by Submit Payment) Ensures 1:1 linkage between a booking and a payment record.

Draw.io Instruction: Create a system boundary and place the actors outside the boundary. Draw connections between the Actors and their respective Use Cases inside the boundary.