# OLA-Data-Analyst-Project 
Project Category: Advanced

## Overview of the OLA Data Analyst Project 🚖📊
This OLA Data Analyst Project is a data analytics case study that involves analyzing ride data for the city of Bengaluru over a period of one month. The project includes data generation, SQL queries, and Power BI visualizations to derive insights into ride performance, cancellations, revenue, and customer behavior.

```sql
DROP TABLE IF EXISTS OLA;

CREATE TABLE OLA (
    Booking_DateTime DATETIME,
    Booking_ID VARCHAR(50),
    Booking_Status VARCHAR(20),
    Customer_ID VARCHAR(50),
    Vehicle_Type VARCHAR(20),
    Pickup_Location VARCHAR(100),
    Drop_Location VARCHAR(100),
    V_TAT INT,
    C_TAT INT,
    Cancelled_Rides_by_Customer INT,
    Cancelled_Rides_by_Driver INT,
    Incomplete_Rides INT,
    Incomplete_Rides_Reason VARCHAR(255),
    Booking_Value DECIMAL(10,2),
    Payment_Method VARCHAR(50),
    Ride_Distance DECIMAL(10,2),
    Driver_Ratings DECIMAL(3,2),
    Customer_Rating DECIMAL(3,2)
);
```

🔹 Key Aspects of the Project

### 1️⃣ Data Structure & Features
The dataset is designed with 1,00,000 (1 lakh) ride records and contains the following columns:<br>

Booking details: Booking_ID, Booking_Status, Customer_ID, Vehicle_Type, Pickup_Location, Drop_Location<br>
Ride analytics: Avg VTAT (Vehicle Arrival Time), Avg CTAT (Customer Arrival Time), Ride Distance, Booking Value<br>
Cancellations & Incompleteness: Cancelled Rides by Customer, Cancelled Rides by Driver, Incomplete Rides, and reasons for them<br>
Ratings & Payments: Driver Ratings, Customer Rating, Payment Method<br>
Important conditions:<br>
✅ 62% of rides must be successful<br>
✅ Customer cancellations ≤ 7%<br>
✅ Driver cancellations ≤ 18%<br>
✅ Incomplete rides ≤ 6%<br>
✅ More bookings on weekends & match days<br>
✅ Higher ride values on weekends

### 2️⃣ SQL Queries for Data Analysis
A series of SQL queries are used to extract meaningful insights, such as:
-- 1. Retrieve all successful bookings
```sql
WITH cte
SELECT * FROM bookings WHERE Booking_Status = 'Success';
```

-- 2. Find the average ride distance for each vehicle type
```sql
WITH cte
SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance 
FROM bookings 
GROUP BY Vehicle_Type;
```

-- 3. Get the total number of cancelled rides by customers
```sql
WITH cte
SELECT COUNT(*) AS total_cancelled_by_customer 
FROM bookings 
WHERE Booking_Status = 'cancelled by Customer';
```

-- 4. List the top 5 customers who booked the highest number of rides
```sql
WITH cte
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides 
FROM bookings 
GROUP BY Customer_ID 
ORDER BY total_rides DESC 
LIMIT 5;
```

-- 5. Get the number of rides cancelled by drivers due to personal and car-related issues
```sql
WITH cte
SELECT COUNT(*) AS total_cancelled_by_driver 
FROM bookings 
WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';
```

-- 6. Find the maximum and minimum driver ratings for Prime Sedan bookings
```sql
WITH cte
SELECT MAX(Driver_Ratings) AS max_rating, MIN(Driver_Ratings) AS min_rating 
FROM bookings 
WHERE Vehicle_Type = 'Prime Sedan';

-- 7. Retrieve all rides where payment was made using UPI
```sql
WITH cte
SELECT * FROM bookings WHERE Payment_Method = 'UPI';
```

-- 8. Find the average customer rating per vehicle type
```sql
WITH cte
SELECT Vehicle_Type, AVG(Customer_Rating) AS avg_customer_rating 
FROM bookings 
GROUP BY Vehicle_Type;
```

-- 9. Calculate the total booking value of rides completed successfully
```sql
WITH cte
SELECT SUM(Booking_Value) AS total_successful_value 
FROM bookings 
WHERE Booking_Status = 'Success';
```

-- 10. List all incomplete rides along with the reason
```sql
WITH cte
SELECT Booking_ID, Incomplete_Rides_Reason 
FROM bookings 
WHERE Incomplete_Rides = 'Yes';
```

### 3️⃣ Power BI Dashboards & Visualizations
Power BI is used to create interactive dashboards for ride analytics. Some key visuals include:
📈 Ride Volume Over Time – Trends in booking numbers
📊 Booking Status Breakdown – Success vs. cancellations
🚗 Top Vehicle Types by Distance – Which vehicles travel the most
⭐ Customer & Driver Ratings – Average ratings per vehicle type
💰 Revenue by Payment Method – UPI, cash, card, etc.

#🔹 Insights & Business Value
This project is valuable for OLA’s business strategy, helping to:
✔ Identify peak booking hours & locations
✔ Reduce cancellations & incomplete rides
✔ Improve customer & driver experience
✔ Optimize pricing & revenue strategies
✔ Make data-driven decisions to boost ride efficiency

#🔹Segregation of the views:
1. Overall
- Ride Volume Over Time
- Booking Status Breakdown
2. Vehicle Type
- Top 5 Vehicle Types by Ride Distance
3. Revenue
- Revenue by Payment Method
- Top 5 Customers by Total Booking Value
- Ride Distance Distribution Per Day
4. Cancellation
- Cancelled Rides Reasons (Customer)
- cancelled Rides Reasons(Drivers)
5. Ratings
- Driver Ratings
- Customer Ratings

Answers:
1. Ride Volume Over Time: A time-series chart showing the number of rides per day/week.
2. Booking Status Breakdown: A pie or doughnut chart displaying the proportion of different
booking statuses (success, cancelled by the customer, cancelled by the driver, etc.).
3. Top 5 Vehicle Types by Ride Distance: A bar chart ranking vehicle types based on the total
distance covered.
4. Average Customer Ratings by Vehicle Type: A column chart showing the average
customer ratings for different vehicle types.
5. cancelled Rides Reasons: A bar chart that highlights the common reasons for ride
cancellations by customers and drivers.
6. Revenue by Payment Method: A stacked bar chart displaying total revenue based on
payment methods (Cash, UPI, Credit Card, etc.).
7. Top 5 Customers by Total Booking Value: A leaderboard visual listing customers who have
spent the most on bookings.
8. Ride Distance Distribution Per Day: A histogram or scatter plot showing the distribution of
ride distances for different Dates.
9. Driver Rating Distribution: A box plot visualizing the spread of driver ratings for different
vehicle types.
10. Customer vs. Driver Ratings: A scatter plot comparing customer and driver ratings for
each completed ride, analyzing correlations.

## 🎯 Final Thoughts
This is a real-world data analytics project perfect for practicing SQL, Power BI, and Excel skills. It helps in understanding ride-sharing trends, customer behavior, and operational efficiency in a structured way. 🚀
