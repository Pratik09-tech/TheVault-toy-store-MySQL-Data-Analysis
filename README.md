# Optimizing eCommerce Website Performance: SQL Analysis for The Vault Toy Store

## Project Preview
In this project, we are analyzing the e-commerce website of The Vault toy store. As a Database Analyst, we need to work closely with
The CEO, Head of Marketing, and Website Manager to optimize the marketing channel, monitor the website performance, and assess the impact of the product launch.

## Entity Relationship Diagram (ERD)
![image](https://github.com/user-attachments/assets/ed99d05c-8a33-49fb-8c6d-7efbe1159331)

## Objectives
▪️Traffic Source Analysis: To assess and optimize marketing channels by analyzing the traffic source using UTM parameters to identify where your customers are
coming from, and which channels are driving the highest quality traffic.

▪️Content Analysis: To understand which pages are seen the most by users, and to identify where to focus on improving the business by finding the most-viewed
pages and the most common entry pages.

▪️Conversion Funnel Analysis: This will help to understand and optimize each step of the users’ experience on their journey toward purchasing the products.

▪️Seasonality and Business Pattern Analysis: Analyzing Seasonality and Business Patterns to gather insights about upcoming spikes and slowdowns in demand
and to understand how much support staff we should have at different times of day or days of the week.

▪️Device Performance Assessment: Compare conversion rates and user engagement across different devices (desktop vs. mobile) to tailor marketing efforts 
and optimize bids based on performance.

▪️Repeat Behavior Analysis: Repeat visits help us understand user behavior and identify some of our most valuable customers.

# Business Problems and Solutions


## Analyzing Website Traffic Sources and Optimizing the Bids

### 1. Ask:- CEO Cindy Sharp wants to see the site traffic breakdown by UTM Source, Campaign, and Referring Domain.

Query:

    SELECT
	      utm_source,
        utm_campaign,
        http_referer,
        COUNT(DISTINCT website_session_id) AS sessions
    FROM website_sessions
    WHERE created_at < '2012-04-12'
    GROUP BY 1,2,3
    ORDER BY 4 DESC;

Query Result:

![image](https://github.com/user-attachments/assets/2250906e-158d-4b65-a48f-f85bdf55b6ef)

▪️Findings:- The primary traffic source is "gsearch nonbrand" with 282,706 sessions, indicating a strong reliance on this channel for website traffic.
