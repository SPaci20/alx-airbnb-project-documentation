Airbnb Clone Backend: Key Features and Functionalities
This document summarizes the core functionalities derived from the database specification, categorized into modules for clarity. This structure can be directly used to create a detailed Draw.io diagram (e.g., using a tree or mind map layout).

1. User and Authentication Management (USER Entity)
A. Core Authentication
A1. Registration: Allow users to sign up as a guest, host, or admin.

A2. Login/Logout: Secure user session management using password_hash.

A3. Profile Retrieval: Fetch user details (first name, last name, phone).

A4. Uniqueness Enforcement: Ensure email is unique across all users.

B. Access Control
B1. Role-Based Permissions: Enforce access rules based on role (e.g., only host can create properties; only admin can modify any record).

2. Property Management (PROPERTY Entity)
A. Host Operations
A1. Listing Creation: Allow a host to create a new listing, linking it via host_id (FK).

A2. Update Listing: Allow hosts to modify property name, description, location, and pricepernight.

A3. Deactivation/Deletion: Ability for host or admin to remove a listing.

B. Guest Operations (Search & Viewing)
B1. Property Search: Search and filter listings based on criteria (e.g., location, price range).

B2. Detail View: Retrieve full details of a property, including description and host information.

3. Booking System (BOOKING Entity)
A. Booking Flow
A1. Create Reservation: Guest submits a booking request specifying start_date and end_date.

A2. Availability Check: System must validate that the requested dates do not overlap with existing confirmed bookings for the property.

A3. Price Calculation: Calculate total_price based on pricepernight and duration.

B. Status & Management
B1. Status Tracking: Track booking lifecycle using status (pending, confirmed, canceled).

B2. Host Approval: Host/Admin can change status from pending to confirmed or canceled.

B3. History: Guest can view their past and upcoming bookings.

4. Payment Processing (PAYMENT Entity)
A. Transaction Management
A1. Record Payment: Record transaction details (amount, payment_date).

A2. Method Tracking: Record the payment_method used (credit_card, paypal, stripe).

A3. Integrity Enforcement: Enforce a 1:1 relationship with the BOOKING entity (booking_id is unique in PAYMENT).

5. Reviews and Ratings (REVIEW Entity)
A. Submission
A1. Review Creation: Allow a user to submit a review and rating (1-5) for a property they have booked.

A2. Rating Validation: Enforce the rating range constraint (CHECK: rating ≥1 AND rating ≤5).

B. Retrieval
B1. Property Reviews: Fetch all reviews for a specific property.

B2. User Reviews: Fetch all reviews written by a specific user.

6. Messaging and Communication (MESSAGE Entity)
A. Communication Flow
A1. Send Message: Allow any user (guest or host) to send a message to another user.

A2. Thread Tracking: Messages are linked via sender_id and recipient_id.

A3. Inbox/Outbox: Retrieve messages based on whether the current user is the sender or the recipient.