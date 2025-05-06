# Hotel Booking Data Analysis

## Introduction

This project aims to analyze hotel booking data to extract valuable insights for hotel management. By leveraging Power BI's capabilities, we seek to identify key trends, patterns, and correlations within the booking data to inform strategic decision-making. This analysis will cover areas such as booking patterns, pricing trends, customer behavior, and cancellation drivers. The ultimate goal is to provide actionable recommendations that can optimize revenue, improve operational efficiency, and enhance customer satisfaction.

## Problem Statement

Our client, a prominent hotel chain, is facing challenges in managing bookings and maximizing revenue. They have reached out to Datafied Technologies to utilize data analytics for insights into booking patterns, guest demographics, and operational efficiencies. The goal is to develop a comprehensive strategy to enhance customer satisfaction and optimize revenue. The hospitality industry is highly competitive, and understanding booking dynamics is crucial for success. This project addresses the need to answer key business questions related to hotel bookings, such as:

* What factors contribute most significantly to booking cancellations, and how can these be mitigated?
* How do booking trends influence pricing strategies and revenue generation across different periods and room types?
* Which market segments and distribution channels are the most profitable and what are their associated booking patterns?
* What are the characteristics and preferences of repeat guests compared to first-time guests, and how can loyalty be fostered?
* How do booking lead times vary across different seasons and market segments, and what are the implications for operations and revenue?

By addressing these questions, the project aims to provide data-driven insights that can lead to tangible improvements in the hotel's performance.

## Data Sourcing

The data for this project was sourced from https://docs.google.com/spreadsheets/d/1FgtlobqnBH9-QihiOL3pW4qBqblPKTAHRdPIiAOE7gU/edit?gid=297258965#gid=297258965 

The data obtained includes details such as booking dates, arrival and departure dates, guest demographics, room types, lead times, market segments, distribution channels, deposit information, cancellation status, and special requests.

## Data Transformation and Cleaning
![image](https://github.com/user-attachments/assets/38023492-95b5-4b51-8ba7-a3abba2aed86)

Before analysis, the raw booking data underwent a series of transformation and cleaning steps using Power BI's Power Query Editor. These steps were crucial to ensure data quality, consistency, and suitability for modeling and visualization. Key transformations included:

* **Handling Missing Values:** Identifying and addressing missing data in key columns (e.g., by imputation or removal, with clear justification).
* **Data Type Conversion:** Ensuring columns had the correct data types (e.g., converting date fields to Date type, numeric fields to appropriate number types).
* **Removing Duplicates:** Identifying and removing any duplicate booking records to avoid skewing the analysis.
* **Filtering Outliers (if applicable):** Investigating and potentially filtering extreme or erroneous data points (e.g., unusually long stays or very high/low prices), with clear documentation of the criteria used.
* **Creating Calculated Columns** 
* **Standardizing Data:** Ensuring consistency in categorical columns (e.g., trimming whitespace, converting text to a consistent case).

## Data Modeling
![image](https://github.com/user-attachments/assets/d207b77f-ca19-49ab-a0b3-4c459eae9e64)

The transformed and cleaned data was then structured into a relational model within Power BI to establish relationships between different entities and facilitate analysis. The key tables and their relationships include:

* **Fact Table (Hotel Bookings):** This table contains the core booking transaction data, with foreign keys linking to the dimension tables. Key columns include booking ID, hotel ID, date keys (booking date, arrival date, departure date), guest information (if available), room details, price, lead time, length of stay, market segment key, distribution channel key, deposit type, cancellation status, and special requests.
* **Dimension Table (Date Dimension):** Contains a comprehensive set of dates with attributes like year, month, day. This allows for effective time-based analysis.
* **Dimension Table (Hotel Dimension):** Contains information about the different hotels, such as Hotel ID and Hotel Name.
* **Dimension Table (Location Dimension):** Contains geographical information, such as Country Name, Country Code, Region, Continent.
* **Dimension Table (Market Segment Dimension):** Lists the different market segments (e.g., Aviation, Corporate, Groups) and their unique IDs, as well as their discounts.
* **Relationship Establishment:** One-to-many relationships were established between the dimension tables and the fact table using the corresponding key columns. For example, one date in the Date Dimension can be associated with Arrival Date in the fact table.

## Data Analysis and Visualization
![image](https://github.com/user-attachments/assets/a962e832-0fb4-424d-994e-d2617f066121)

Following the data modeling phase, I proceeded to analyze the hotel booking data and create visualizations in Power BI to address the key business questions outlined in the Problem Statement. The dashboard developed (as referenced in the image) provides a comprehensive overview of booking patterns and trends. Key visualizations and insights include:

* **Key Performance Indicators (KPIs):**
    * **Total Bookings:** Displaying the overall number of bookings. (As seen with "Total Bookings 101K").
    * **Total Cancellations:** Showing the total count of canceled bookings. (As seen with "Total Cancellation 27K").
    * **Cancellation Rate:** Calculated as the percentage of bookings that were canceled. (As seen with "Cancellation Rate 27%").
    * **Booking Cancellation Ratio:** The ratio of total bookings to total cancellations, indicating the proportion of successful bookings relative to cancellations. (As seen with "Booking Cancellation 4:1").
    * **Average Booking Changes:** The average number of modifications made to bookings. (As seen with "Avg Booking Changes 0.27").
    * **Average Waiting Days:** The average difference in days between the booking date and the arrival date (lead time). (As seen with "Avg Waiting Days 1").
    * **Maximum Waiting Days:** The longest lead time observed in the bookings. (As seen with "Max Waiting Days 391").

* **ADR Trends (Line Chart):** A line chart illustrating the Average Daily Rate (ADR) over time (months), segmented by hotel type to identify seasonal patterns and pricing fluctuations. (As seen in the "ADR Trends" visual).

* **Booking by Hotel (Donut Chart):** A donut chart showing the distribution of bookings across different hotel types (if the dataset includes multiple properties), highlighting the contribution of each hotel to the total bookings. (As seen in the "Booking By Hotel" visual).

* **Cancellation Patterns (Area Chart):** An area chart displaying cancellation trends over time, segmented by market segment, lead time to identify periods or booking characteristics with higher cancellation rates. (As seen in the "Cancellation Patterns" visual).

* **Booking by Region (Bar Chart):** A bar chart showing the number of bookings originating from different geographical regions , indicating key source markets. (As seen in the "Booking By Region" visual).

These visualizations collectively provide a multi-faceted view of the hotel booking data, enabling the identification of key trends, correlations, and potential areas for improvement.

## Conclusions and Recommendations

Based on the analysis and visualizations, several key conclusions and recommendations can be drawn:

* **High Cancellation Rate:** The cancellation rate of 27% indicates a significant loss of potential revenue. Further investigation into the drivers of these cancellations (as highlighted in the "Cancellation Patterns" visual and correlations with lead time, market segment) is crucial. **Recommendation:** Implement targeted strategies to reduce cancellations, such as revised deposit policies for high-risk segments, proactive communication with guests for long-lead bookings, and offering incentives for non-refundable bookings where appropriate.

* **ADR Fluctuations:** The ADR trends show variations over time, likely influenced by seasonality and demand. Understanding these patterns allows for dynamic pricing optimization. **Recommendation:** Refine dynamic pricing strategies to capitalize on peak seasons and adjust rates competitively during off-peak periods. Analyze ADR performance by hotel and room type to optimize pricing tiers.

* **Market Segment and Channel Performance:** The revenue contribution by market segment and distribution channel (while not directly visualized in this dashboard snapshot, this analysis would be crucial) needs to be thoroughly evaluated. **Recommendation:** Focus marketing and sales efforts on the most profitable market segments and distribution channels. Optimize commission structures and partnerships with high-performing channels.

* **Lead Time Impact:** The average and maximum waiting days (lead time) provide insights into booking horizons. Understanding how lead time correlates with cancellations and ADR is vital for forecasting and pricing. **Recommendation:** Develop forecasting models that incorporate lead time trends. Adjust pricing based on booking pace and lead time, potentially offering early booking discounts or last-minute deals strategically.

* **Regional Performance:** The "Booking by Region" visual highlights key source markets. **Recommendation:** Tailor marketing campaigns to focus on high-performing regions and explore opportunities to attract more guests from underperforming regions.

Further in-depth analysis, including exploring the characteristics of repeat guests and the impact of booking changes, will provide additional actionable insights for the hotel management to optimize revenue, enhance guest satisfaction, and improve operational efficiency.

---
