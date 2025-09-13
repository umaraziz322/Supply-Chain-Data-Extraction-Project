# Supply Chain Data Extraction Project
## Introduction
This project is a SQL-based analysis of a hypothetical supply chain database. Its main purpose is to demonstrate the practical application of database design principles and SQL queries to derive key business insights. By structuring and querying data related to customers, suppliers, products, and orders, the project identifies sales trends, evaluates supplier performance, and uncovers opportunities for business growth. In essence, it shows how to use SQL as a powerful tool for data analysis to support strategic decision-making in a business environment.
## Project Summery
This project is a practical exercise in Supply Chain Management (SCM) data analysis using SQL (Structured Query Language). It simulates a real-world scenario by creating a foundational database and then querying that data to extract valuable business insights.
Project Structure and Database Design
The project begins with the essential steps of setting up a relational database. It's designed around five core tables that represent key entities in a supply chain:
Customer: Stores information about the people or companies buying products.
Supplier: Holds data on the vendors providing the products.
Product: Contains details about the items being sold, including price, package size, and if they've been discontinued.
Orders: Records each order placed, including the order date, a unique order number, and the total amount.
OrderItem: A crucial "linking" table that connects Orders and Products. It details the specific items within each order, their quantity, and the unit price at the time of sale.
The tables are interconnected using primary keys and foreign keys, which enforce data integrity and allow you to link information across different tables using JOIN operations. For instance, the Orders table is linked to the Customer table via CustomerId, ensuring every order is associated with a specific customer.
Data Analysis and Business Insights
The core of the project is a series of SQL queries designed to answer specific business questions. These queries are categorized into four levels of increasing complexity, demonstrating a progressive mastery of SQL concepts.
#### Level 1: Foundational Queries
These queries focus on basic data retrieval and aggregation to get a feel for the data. Examples include:
o	Finding the number of customers in each city.
o	Listing products that are not discontinued.
o	Identifying customers who have not placed any orders.
#### Level 2: Intermediate Analysis
This section uses more complex JOIN operations and aggregate functions to uncover deeper insights. Key questions answered here include:
o	Identifying the most in-demand products by summing the total quantity sold.
o	Calculating the total revenue and number of orders for each month.
o	Pinpointing the top suppliers based on the revenue generated from their products.
#### Level 3: Advanced Filtering and Logic
These queries involve more sophisticated filtering and multi-table joins to answer very specific questions. For example:
o	Finding customers who purchased more than 10 units of a single product in an order.
o	Identifying suppliers of products that cost more than a certain amount.
#### Level 4: Strategic Business Questions
The final level tackles complex, real-world business problems that require a combination of all the SQL skills demonstrated previously. This is where the project truly shines by applying technical skills to solve strategic issues. Notable examples include:
o	Calculating the total amount of money saved by customers on discounted products.
o	Providing business advice to a new supplier ("Mr. Kavin") by identifying high-demand products and potential competitors.
o	Creating a consolidated list of customers and suppliers to analyze regional business relationships.
This project is an excellent demonstration of how a structured database and the power of SQL can be used to analyze a business's health, understand customer behavior, and guide strategic decision-making. It shows the full lifecycle of a data project, from setting up the foundation to delivering actionable insights.

## Highlights
Here are some key findings from the data analysis:
### Customer & Order Insights
Customer Locations: The customer base is concentrated in five cities: Lahore, Karachi, Quetta, Islamabad, and Multan. Lahore and Karachi have the highest number of customers, indicating they are key markets.
Order Frequency: Customers are frequent buyers, with a significant number of orders placed throughout the months of July, August, and September. Some customers, like Bilal Mehar (ID 5), are repeat customers who have placed multiple orders.
High-Value Customers: The customer who placed the highest value of orders, with a total amount of over $4,000, is Bilal Mehar (ID 5) from Multan. The project identified him as the top customer in terms of overall spending, which is a crucial insight for marketing and sales teams.
### Product & Supplier Performance
Top-Selling Products: The products with the highest demand (more than 100 units sold) are 'Soaps,' 'Suppliments,' and 'Lipsticks.' This information is vital for inventory management and future product selection.
Supplier Performance: 'Afzal Electronics' is the top supplier in terms of revenue generated, far surpassing its competitors. This suggests a strong market for electronics and a profitable partnership with this supplier.
Discontinued Items: The project identified that some products, like 'FaceWash' and 'Catllery,' have been discontinued, which could be due to low demand or other business decisions. This is an important detail for managing product catalogs.
### Business Expansion Insights
New Supplier Opportunities: For a new supplier like Mr. Kavin, the project recommends focusing on high-demand products like 'Soaps' and 'Suppliments' to enter a profitable market.
Competitor Analysis: The key competitors for these products are 'Glowing Angels' (for soaps) and 'Iron Fitness' (for supplements), providing Mr. Kavin with a clear understanding of the market landscape.
Geographic Gaps: The analysis revealed that some cities with customers (e.g., Peshawar) have no local suppliers, while some cities with suppliers (e.g., Multan) have no customers, indicating potential areas for market expansion and strategic partnerships.

## Weak Points & Problems
As I created this project solely to practice my SQL skills and this project have some problems and according to Google Gemini - This project provides a solid foundation for a SQL portfolio, but it has several weak points and potential problems that could be addressed to make it more robust and professional.
#### 🐛 Data-Related Issues
Hardcoded Data: The project relies on hardcoded INSERT statements. In a real-world application, this is impractical. Data would be ingested from other sources, like CSV files or an application interface. The current approach is suitable for a demo but not for a dynamic system.
Inconsistent Data Types: The OrderDate column is stored as a VARCHAR(40), which is a major design flaw. Date and time data should be stored using a dedicated data type like DATE or DATETIME. Storing dates as text makes it difficult to perform date-based calculations (e.g., finding orders within a specific date range) and can lead to data inconsistencies and slow performance. The queries had to use the complex STR_TO_DATE() function to compensate for this design choice.
Lack of Realism: The OrderItem table's UnitPrice is different from the Product table's UnitPrice. While this can represent a discount, the project doesn't explicitly calculate this discount or the amount saved for all orders, only in the Level 4 question. The data also seems to be for a single month, which limits the scope of long-term trend analysis.
#### 📉 Query and Structure Problems
Lack of ON DELETE CASCADE: The project notes that ON DELETE CASCADE was intentionally avoided to keep historical data. This is a valid business decision, but it introduces a risk of "orphan records" if parent records (e.g., a customer) are deleted without a corresponding application-level constraint to handle the deletion of their related orders. A more robust solution would be to use a soft delete (marking a record as deleted with a flag) or a trigger to archive data instead of a hard delete.
Redundant Queries: Many of the queries in different sections are very similar. For example, several queries look at customer data or count records. Consolidating or refactoring these could make the project more efficient and demonstrate a better understanding of query optimization.
#### 🖼️ Presentation and Findings
Unstructured Findings: The original project code simply lists queries and their comments. A professional project would include a separate document or section that summarizes the key findings and business insights, similar to the previous response. This demonstrates the ability to not just write code, but to derive and communicate business value from it.
Limited Visualization: While the project is a SQL-only exercise, in a real-world scenario, these findings would be presented visually using a Business Intelligence (BI) tool like Tableau or Power BI. Presenting a few mock-up dashboards would significantly enhance the project's appeal.


