---
title: 'Incomplete Payment Subscriptions Notification'
media_order: task-incomplete-payment-subscriptions-notification.png
published: true
---

This scheduled task is used to send notification to administrators about the subscription records which choose to use online payment methods such as PayPal, Stripe.... but did not complete payment (ignore payment process or payment failed for whatever reasons). Administrator can then contact these users to see why they did not make payment if needed. To use this feature:

## Create and configure the scheduled task

1. Go to **System -> Plugins**, make sure **Task - Membership Pro** plugin is enabled.
2. Go to **System -> Scheduled Tasks**, press New button in the toolbar to create a new scheduled task for **Membership Pro - Incomplete Payment Subscriptions Notification** task type.
3. Setup all required parameters, save it.

![task-incomplete-payment-subscriptions-notification](task-incomplete-payment-subscriptions-notification.png "task-incomplete-payment-subscriptions-notification")

## Task Basic Fields
This scheduled task should be run every few hours. So you can setup **Basic Fields** to following values

- **Execution Rule**: Set to **Interval, Hours**
- **Interval in Hours**: Set to the number you want, for example, if you set it to 3, the task will be run every 3 hours.

## Task Parameters
- **Notification Emails**:  Enter the emails you want to receive notification about this incomplete payment subscriptions. Multiple emails are supported, just separate these emails by comma.
- **Subject**: Subject of the email. You can use [IDS] tag and it will be replaced with IDs of the incomplete payment subscriptions. For example: **Payment For Subscription [IDS] were not completed**
- **Message**: Body of the email. You can use [IDS] and [LINKS] tags in the message. For example:

Dear administrator

We would like to inform you that payment for subscription records with the following IDs: [IDS] were ignored or not completed. You might want to contact these subscribers ask them to see the reasons if needed. Here is links to these subscriptions:

[LINKS]

Regards,

Company Name