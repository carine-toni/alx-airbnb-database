User
user_id (PK)

first_name

last_name

email (UNIQUE, Indexed)

password_hash

phone_number (nullable)

role (ENUM: guest, host, admin)

created_at

2. Property
property_id (PK)

host_id (FK → User.user_id)

name

description

location

pricepernight

created_at

updated_at

3. Booking
booking_id (PK)

property_id (FK → Property.property_id)

user_id (FK → User.user_id)

start_date

end_date

total_price

status (ENUM: pending, confirmed, canceled)

created_at

4. Payment
payment_id (PK)

booking_id (FK → Booking.booking_id)

amount

payment_date

payment_method (ENUM: credit_card, paypal, stripe)

5. Review
review_id (PK)

property_id (FK → Property.property_id)

user_id (FK → User.user_id)

rating (1–5)

comment

created_at

6. Message
message_id (PK)

sender_id (FK → User.user_id)

recipient_id (FK → User.user_id)

message_body

sent_at

✅ Step 2: Define Relationships
Here’s how the tables relate:

Entity	Relationship
User	Owns many properties (host) → Property.host_id
Makes many bookings → Booking.user_id
Writes many reviews → Review.user_id
Sends & receives messages → Message.sender_id, recipient_id
Property	Belongs to a user (host), has many bookings and reviews
Booking	Connects User and Property, is paid via Payment
Payment	Belongs to one booking
Review	Linked to one user and one property
Message	Sender and recipient are both users
