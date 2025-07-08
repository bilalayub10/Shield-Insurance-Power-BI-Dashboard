# Shield Insurance Company Insights Dashboard

## Project Objective
This project aimed to **design an interactive Power BI dashboard** for Shield Insurance, a customer-focused insurance company. The primary objectives were to:
*   Monitor customer and revenue growth.
*   Track policy trends over time.
*   Analyze performance by age group and sales mode.

The core idea was to shift from static reporting to a more dynamic, insight-driven view of the business.

## Data Overview
The dashboard utilizes data provided by Shield Insurance, covering the timeframe from **November 2022 to April 2023**. It includes the following tables;

### `dim_customer.csv`
Contains customer-level details  

**Key fields:**
- `customer_code` – Unique identifier for each customer  
- `dob` – Customer's date of birth  
- `city` – Customer's location  

### `dim_date.csv`
Standard date dimension table for time-based analysis  

**Key fields:**
- `date`, `mmm_yy` – Daily and monthly formats  
- `day_type` – Weekday labels (e.g., Monday, Tuesday)  
- `week_no` – Week number of the year as per the date column

### `dim_policies.csv`
Details of all policy types offered  

**Key fields:**
- `policy_id` – Unique policy identifier  
- `base_cover` – Base cover amount for that particular policy 
- `base_premium_amt(INR)` – The premium amount that the customer has to pay to get the policy

### `fact_premiums.csv`
Tracks premium payments and sales data  

**Key fields:**
- `date`, `customer_code`, `policy_id`  
- `sales_mode` – Mode of the sales (Offline-Agent, Offline-Direct, Online-App, Online-Website)  
- `final_premium_amt(INR)` – The premium amount that is paid for that policy by the customer

### `fact_settlements.csv`
Contains policy settlement statistics by age  

**Key fields:**
- `age` – Age of the policyholder  
- `settlement%` – Percent of policy settlements happend for this age

### `dim_age` *(Custom table created in Power Query)*
A reference dimension created to map individual ages to age groups for consistent and reusable segmentation across the model.

**Key fields:**
- `age` – Numeric age  
- `age_group` – Categorical age range (e.g., 18–24, 25–30, etc.)

## Project Approach

To deliver a clean, insightful, and interactive dashboard for Shield Insurance, I followed a structured end-to-end BI development process that involved:

### 1. Data Understanding & Cleaning
- Reviewed five primary datasets provided by the client: `dim_customer`, `dim_date`, `dim_policies`, `fact_premiums`, and `fact_settlements`
- Cleaned and transformed the data using **Power Query**
- Created a custom reference table `dim_age` to categorize customers into **age groups** for consistent and reusable segmentation across visuals

### 2. Data Modeling
- Established relationships between fact and dimension tables using keys like `customer_code`, `policy_id`, and `date`
- Built a **star schema** model in Power BI to ensure optimized performance and clean filtering
![Data Model](images/data-model.png)

### 3. 🧠 Calculations with DAX
- Created DAX measures to track **KPIs** such as:
  - Total Revenue  
  - Total Customers  
  - Daily Revenue Growth 
  - Daily Customers Growth  

### 4. Dashboard Design & Visualization
- Designed three core views:
  - **General View** – Tracks customer/revenue performance and breakdowns by city and age group. 
  - **Sales Mode Analysis** – Compares revenue and customers across sales channels.  
  - **Age Group Analysis** – Examines customer behavior, settlement rates, and policy preference by age.

- Ensured a **consistent layout**, navigation pane, and filters across all views for a seamless user experience

### 5. Testing & Insight Extraction
- Verified filters, slicers, and cross-interactions across visuals
- Extracted **actionable business insights** to support data-driven decision-making

This structured approach ensured the dashboard was not only visually compelling but also strategically useful for real-world business analysis.

## Dashboard Views
The dashboard is organized into four key views — including a Home Page for navigation — each designed to support specific business questions and guide users through interactive analysis.

### Home View
This serves as the main navigation hub, allowing users to easily jump between General, Sales Mode, and Age Group views.
![Home View](images/data-model.png)

### General View
Offers a high-level overview of customer and revenue performance:
- Displays total revenue, customer count, and daily growth metrics.
- Tracks monthly performance trends.
- Breaks down revenue and customers by **city** and **age group**.
- Helps quickly assess overall performance and key customer segments.

![General View](images/data-model.png)

**Key Insights from the View:**
- **Delhi NCR** is the **top-performing city**, contributing over ₹400 million in revenue from more than 11,000 customers.
- The **31–40 and 41–50 age groups** are the **most profitable segments**, generating over ₹300M and ₹200M in revenue, respectively. Notably, the **65+ group also shows strong revenue contribution**, indicating engaged senior customers.
- Revenue reached a high point of **₹264 million in March 2023**, before dropping to ₹154 million in April. Customer count followed a similar pattern.
- **Customer segmentation by city and age group** helps identify high-performing segments, such as the **31–40 age group in Delhi NCR**, which alone generates ₹127M revenue with over 4,000 customers.

### Sales Mode Analysis
Breaks down performance across different sales channels:
- Shows customer and revenue split across **sales modes** (Offline Agent, Online App, etc.).
- Visualizes monthly trends in sales channel performance.
- Helps identify which channels are growing or underperforming.

![Sales Mode Analysis](images/data-model.png)

**Key Insights from the View:**
- The **Offline-Agent channel significantly leads** in both customer share (55.41%) and revenue contribution (55.67%).
- **Online-App and Offline-Direct** follow, with online channels steadily gaining traction.
- The near-identical pattern between customer count and revenue share across channels suggests a **relatively consistent average revenue per customer**.
- While Offline-Agent consistently leads in monthly customer acquisition, **digital channels (Online-App and Online-Website) surpassed Offline-Direct by February 2023**, highlighting their growing adoption.

### Age Group Analysis
Explores customer behavior across various age segments:
- Displays total customers per **age group**.
- Analyzes settlement rates and policy preferences by age.
- Helps uncover which age groups are most engaged and profitable.

![Age Group Analysis](images/data-model.png)

**Key Insights from the View:**
- **Expected settlement percentage increases with age**, starting at 37.51% for 18–24 and reaching 74.33% for customers aged 65 and above.
- The **31–40 age group shows the highest engagement across all sales modes**, particularly with Offline-Agent.
- **Younger age groups (18–24, 25–30) show a more balanced use of online and offline channels**, while **older segments rely more heavily on traditional offline agent interactions**.
- The **31–40 and 41–50 age segments demonstrate the highest diversity and volume in policy selection**, indicating opportunities for age-targeted marketing and policy design.
- The **31–40 group is the company’s core customer base**, leading by a wide margin with 10,440 customers, followed by 41–50 (6,050 customers).

## Tools & Technologies

- **Power BI** – For building the interactive dashboard and visualizing business insights.  
- **Power Query** – For data transformation and cleaning within Power BI.  
- **DAX (Data Analysis Expressions)** – A formula language used to create calculated measures and apply time intelligence.  
- **Excel** – Used as the original data source for importing CSV files.

## Let's Connect
Feel free to reach out for any feedback or to connect:

*   **Email**: bilalayub.connect@gmail.com
*   **LinkedIn**: [https://www.linkedin.com/in/muhammad-bilal-ayub/](https://www.linkedin.com/in/muhammad-bilal-ayub/)









