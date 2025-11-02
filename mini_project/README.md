Ride-Sharing Data Pipeline (Uber-like)

Goal: Analyze ride data for surge pricing and driver earnings.
Data: NYC Taxi dataset (free on data.gov).
Flow:

Extract CSVs (for one month).

Transform with Python (filter nulls, compute trip duration/distance).

Load into database.

Write SQL reports: busiest hours, top pickup zones, average fare per mile.

Bonus: build daily aggregates and schedule with cron.

🧩 Skills: Batch processing, data cleaning, SQL window functions.
