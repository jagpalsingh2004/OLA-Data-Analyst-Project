# OLA-Data-Analyst-Project 
Project Category: Advanced

## Overview of the OLA Data Analyst Project 🚖📊
This OLA Data Analyst Project is a data analytics case study that involves analyzing ride data for the city of Bengaluru over a period of one month. The project includes data generation, SQL queries, and Power BI visualizations to derive insights into ride performance, cancellations, revenue, and customer behavior.

🔹 Key Aspects of the Project
1️⃣ Data Structure & Features
The dataset is designed with 1,00,000 (1 lakh) ride records and contains the following columns:

Booking details: Booking_ID, Booking_Status, Customer_ID, Vehicle_Type, Pickup_Location, Drop_Location
Ride analytics: Avg VTAT (Vehicle Arrival Time), Avg CTAT (Customer Arrival Time), Ride Distance, Booking Value
Cancellations & Incompleteness: Cancelled Rides by Customer, Cancelled Rides by Driver, Incomplete Rides, and reasons for them
Ratings & Payments: Driver Ratings, Customer Rating, Payment Method
Important conditions:
✅ 62% of rides must be successful
✅ Customer cancellations ≤ 7%
✅ Driver cancellations ≤ 18%
✅ Incomplete rides ≤ 6%
✅ More bookings on weekends & match days
✅ Higher ride values on weekends

2️⃣ SQL Queries for Data Analysis
A series of SQL queries are used to extract meaningful insights, such as:
🔹 Retrieving all successful bookings
🔹 Calculating average ride distance per vehicle type
🔹 Identifying top 5 customers with the highest number of rides
🔹 Analyzing cancellation reasons (customer vs. driver)
🔹 Finding max & min driver ratings for Prime Sedan rides
🔹 Calculating total revenue from successful rides

Example Query:

sql
Copy
Edit
SELECT Vehicle_Type, AVG(Ride_Distance) as avg_distance 
FROM bookings 
GROUP BY Vehicle_Type;
3️⃣ Power BI Dashboards & Visualizations
Power BI is used to create interactive dashboards for ride analytics. Some key visuals include:
📈 Ride Volume Over Time – Trends in booking numbers
📊 Booking Status Breakdown – Success vs. cancellations
🚗 Top Vehicle Types by Distance – Which vehicles travel the most
⭐ Customer & Driver Ratings – Average ratings per vehicle type
💰 Revenue by Payment Method – UPI, cash, card, etc.

🔹 Insights & Business Value
This project is valuable for OLA’s business strategy, helping to:
✔ Identify peak booking hours & locations
✔ Reduce cancellations & incomplete rides
✔ Improve customer & driver experience
✔ Optimize pricing & revenue strategies
✔ Make data-driven decisions to boost ride efficiency

🎯 Final Thoughts
This is a real-world data analytics project perfect for practicing SQL, Power BI, and Excel skills. It helps in understanding ride-sharing trends, customer behavior, and operational efficiency in a structured way. 🚀
