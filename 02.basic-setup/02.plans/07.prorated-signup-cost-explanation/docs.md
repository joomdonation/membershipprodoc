---
title: 'Prorated Signup Cost'
media_order: pro-rated-signup-cost.png
---

On plans with a fixed expiration date, all subscriptions expire on the same date, such as 12-31-2026, regardless of when subscribers sign up. By default, subscribers pay the full price even if only one or two months remain.

If you want to change this default behavior, you can set **Prorated Signup Cost** of the plan to **By Days** or **By Months**:

* If you set it to **By Days**, when subscribers sign up, the system will calculate the remaining days of the subscription (For example, today is **11-16-2026** and if fixed expiration date set to **12-31-2016**, the the remaining days would be **45 days**) and multiple with the price for each day to calculate the subscription price subscribers have to pay (instead of asking subscribers to pay for full price). So for example, if price of the plan is 365$ (1$ each day), the subscribers will only have to pay 45$ instead of 365$. If someone subscribes on tomorrow, he will have to pay 44$ and so on....
* With **By Months**, Membership Pro multiplies the number of months remaining by the monthly price. For example, if today is **11-16-2026** and the fixed expiration date is **12-31-2026**, there are **2 months** remaining. On a $120 plan ($10 per month), a subscriber pays $20. If they sign up the following month, they pay $10.

![pro-rated-signup-cost](pro-rated-signup-cost.png "pro-rated-signup-cost")