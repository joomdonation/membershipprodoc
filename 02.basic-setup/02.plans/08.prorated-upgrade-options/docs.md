---
title: 'Prorated Upgrade Options'
published: true
---

When you allow subscribers to upgrade from one plan to another, you can choose how to prorate the upgrade. The options below explain how each choice affects the duration and price of the new subscription.

## By Time
 For this option, the remaining active duration of the original subscription will be added to the upgrade subscription. For example, if you upgrade to 6 months plans and have 2 months left from original subscription, the upgrade subscription will have duration 8 months (6 months + 2 months).

## By Price
For this option, the money which subscriber has to pay for the upgrade will be deducted from the money left from the original subscription. The money left from original subscription is calculated based on:

- Number Of Days Left from active duration of original subscription
- Number Of Days of subscription duration (subscription lengths in days)
- Price of the original plan

DEDUCTED_AMOUNT = PLAN_PRICE * NUMBER_DAYS_LEFT / SUBSCRITPION_LENGTH_IN_DAYS

## Keep Duration
For this option, the subscription start date and subscription end date of the upgrade subscription will be same with subscription start date and subscription end date of the original subscription.

## Keep Duration, Price Prorated From Original Plan
- The subscription start date and subscription end date of the upgrade subscription will be same with subscription start date and subscription end date of the original subscription
- The amount subscriber has to pay for the upgrade is calculated based on the remaining days of the subscription and price of the original plan (note that the duration is kept):

AMOUNT = FROM_PLAN_PRICE * NUMBER_DAYS_LEFT / FROM_PLAN_SUBSCRITPION_LENGTH_IN_DAYS

+ FROM_PLAN_PRICE is price of the plan which user upgrade from
+ NUMBER_DAYS_LEFT: is number of days left of the original subscription
+ FROM_PLAN_SUBSCRITPION_LENGTH_IN_DAYS is subscription length of the original plan (convert to days)

>>>
Note that this amount calculation only works for upgrading to one time subscription plan. For recurring plan, the payment amount for upgrade will still be determined by upgrade option price.


## Keep Duration, Price Prorated From Upgrade Plan
- The subscription start date and subscription end date of the upgrade subscription will be same with subscription start date and subscription end date of the original subscription
- The amount subscriber has to pay for the upgrade is calculated based on the remaining days of the subscription and price of the upgrade plan:

AMOUNT = UPGRADE_PLAN_PRICE * NUMBER_DAYS_LEFT / UPGRADE_PLAN_SUBSCRITPION_LENGTH_IN_DAYS

+ UPGRADE_PLAN_PRICE is price of the plan which user upgrade to.
+ NUMBER_DAYS_LEFT: is number of days left of the original subscription.
+ UPGRADE_PLAN_SUBSCRITPION_LENGTH_IN_DAYS is subscription length of the plan which user is upgrading to (convert to days)

>>>
Note that this amount calculation only works for upgrading to one time subscription plan. For recurring plan, the payment amount for upgrade will still be determined by upgrade option price.