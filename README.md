Clickstream: E-commerce Conversion Funnel Analysis — README

📝 Project Overview

This Power BI project analyzes user behavior using clickstream data collected from an e-commerce platform. The goal is to understand customer journey patterns, identify funnel drop-offs, and improve overall conversion.

🎯 Business Objective

The project answers the key question:

Where do users drop off in the funnel, and how can we improve conversion rate?

It helps stakeholders optimize:

User engagement

Product discovery

Add‑to‑cart behavior

Checkout success

📂 Data Source

Single Excel dataset containing:

SessionID

UserID

Timestamp

PageType

DeviceType

Country

ReferralSource

TimeOnPage_seconds

itemInCart

Purchased

🧩 Data Modeling

A Star Schema model was created:

Fact Table: User clickstream/Session logs

Dimension Tables: Device, Country, PageType, Referral Source

This improves performance, relationships, and DAX accuracy.

📌 Key KPIs

Total Sessions

Conversion Rate (%)

Add-to-Cart Rate

Average Time on Page

Sessions by Device Type

Sessions by Country

🧠 DAX Measures
Cart Users =
CALCULATE(
    DISTINCTCOUNT(Fact_Events[UserID]),
    Fact_Events[itemInCart] = 1
)

Purchase Users =
CALCULATE(
    DISTINCTCOUNT(Fact_Events[UserID]),
    Fact_Events[Purchased] = 1
)

Conversion Rate % =
DIVIDE(
    [Purchase Users],
    DISTINCTCOUNT(Fact_Events[UserID]),
    0
)

Cart Abandonment % =
DIVIDE(
    ([Cart Users] - [Purchase Users]),
    [Cart Users],
    0
)

Dashboard Pages
1️⃣ Main Funnel Dashboard

Shows complete journey:

Page Visit → Product View → Add to Cart → Purchase

Engagement metrics

Device & Country insights

2️⃣ Drill-Through Page

Session‑level deep dive:

Timestamp navigation

Geo map visualization

Event sequence analysis

🔍 Key Insights

High Time on Page positively impacts add‑to‑cart rate

Mobile users drop more during checkout compared to desktop

UK, India, Australia show higher engagement

Referral sources heavily influence purchase behavior

📢 Recommendations

Improve mobile checkout flow

Add personalized product suggestions

Run A/B tests on CTA buttons

Focus marketing on high-engagement countries

📎 Appendix

Dashboard screenshots will be included here.

✅ Conclusion

This project provides a clear understanding of user behavior and highlights actionable insights that can significantly improve e-commerce funnel performance.
