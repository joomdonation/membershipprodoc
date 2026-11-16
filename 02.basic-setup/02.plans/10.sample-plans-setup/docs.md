---
title: 'Sample Plans Setup'
published: true
---

## Manual Renewal Plan
You would want to setup this type of subscription plan if you want users to subscribe for the plan, become active subscriber (for example for 1 month) and renew the subscription manually before it's expiring. Example Setup:

Subscription Length: 1 Month
Price: 100$ (price subscribers have to pay every month (or week/year, depends on subscription length)
Recurring Subscription: No

## Fixed Expiration Date
You would want to setup this type of subscription plan if you want all subscriptions of this plan expires on same date (not depends on the date users subscribe for the plan). Example Setup:

- Expired Date: 2020-12-31 (set to the date you want)
- Subscription Length: 1 Year
- Price: 100 (change to the price you want)

With that setup, all subscriptions of this plan will be expired on that same date 2020-12-31. By defaut, users will have to pay full price to subscribe for the plan (even if there is only 1 month left until that expired date Expired Date). To allow users to pay base on the time left (from the sign up date to the Expired Date), you can set **Prorated Signup Cost** to **By Days** or **By Months**.

## Plan with Setup Fee
You can setup this kind of plan if you want subscribers of the plan to be charged a setup fee for the first payment- together with subscription fee of the plan (when he first subscribes for the plan). Subscribers won't be charged this setup fee again when they renew subscription (both manual or automatic renewal). Example Setup:

Subscription Length: 1 Month
Price: 100
Setup Fee : 250

With that setup, when users first sign up, he will have to pay 350$ (100$ subscription fee + 250$ setup fee). When he renews subscription (after one month), he will only have to pay 100$ and so on. 

## Automatic Renewal
You can setup this kind of plan if you want renewal happens automatically every week(s), every month(s), every year(s) (subscribers does not need to come back to your site to renew subscription manually after subscribing for the plan). Example Setup:

- Subscription Length: 1 Month ( Change it to subscription length you want)
- Price: 100 (change it to price you want users to pay - for each month in this sample plan)
- Enable Renewal: Yes
- Recurring Subscription: Yes

## Automatic Renewal With Trial Duration
You would want to setup this kind of plan if you want to allow users to:
- Pay a different price (could be smaller, or greater than price of the plan or even be free) and has active subscription for the plan in a trial duration
- After that duration, subscribers will have to pay the recurring price (setup price) for every duration (setup in subscription length of the plan). Example Setup:

Subscription Length: 1 Month
Price: 100
Recurring Subscription: Yes
Trial Duration: 1 Week
Trial Amount: 0

With above setup, users will get free subscription for one week and then pay 100$ every month (automatically).

## Disable Renewal Plan
You would want to setup this kind of plan if you want to give users a chance to try the subscription for certain duration (for example 1 week)  before they subscribe to other plans on your site. Example Setup:

Subscription Length: 1 Week
Price: 0 (Mean free or any price you want)
Enable Renewal: No

With that setup, each user can only subscribe for that plan to become active subscriber for one week only. After one week, subscription will be expired and users won't be allowed to renew the subscription anymore. They can only _try_ the subscription for one week only

## Lifetime Subscription
You would want to setup this type of subscription plan if you want users to subscribe for the plan (could be free or paid plan) and become lifetime subscribers (they will be active forever and never has to renew their subscription). Example Setup:

- Subscription Length: 1 Year (does not matter)
- Price: 0 (or set it to price you want if this is a paid plan)
- Lifetime Subscription: Yes
