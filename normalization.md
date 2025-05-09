# Database Normalization Explanation (AirBnB Clone)

## ✅ Step 1: First Normal Form (1NF)
All tables have:
- Atomic (indivisible) values
- No repeating groups
→ Schema satisfies 1NF

## ✅ Step 2: Second Normal Form (2NF)
- All tables have a single-column primary key (UUID)
- No partial dependencies
→ Schema satisfies 2NF

## ❗ Step 3: Third Normal Form (3NF)
### Potential Issue:
- The `Booking` table includes a `total_price` field
- This can be derived from:  
  `Property.pricepernight × (end_date - start_date)`
- Storing it violates 3NF by introducing a transitive dependency

### ✅ Solution:
- Remove `total_price` from the `Booking` table
- Instead, calculate it in the application layer or using SQL when needed

## ✅ Summary of Adjustments
- Booking.total_price → Removed
- All other tables meet 3NF requirements

## ✔️ Result
The database schema has been normalized up to **Third Normal Form (3NF)**.

