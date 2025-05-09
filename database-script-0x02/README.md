Explanation:
Data Types:

Used INT for numeric fields like IDs and quantities.

VARCHAR for strings with varying lengths (names, emails).

DECIMAL for prices to avoid floating-point precision issues.

TEXT for larger textual data (e.g., product descriptions).

TIMESTAMP for date-related fields.

Primary Keys:

Each table has a primary key (PRIMARY KEY), ensuring each record is unique and indexed.

Foreign Keys:

Orders references Users (user_id).

Order_Items references both Orders (order_id) and Products (product_id).

Foreign keys ensure referential integrity and cascade delete behavior where applicable.

Indexes:

Created indexes on commonly queried columns (like email, user_id, product_name, etc.) to speed up searches.

Constraints:

CHECK constraints ensure valid values (like positive prices or quantities).

A UNIQUE constraint on the email in the Users table ensures that no two users have the same email.
