---
title: 'Incomplete Payment Notification'
taxonomy:
    category:
        - docs
published: true
media_order: incomplete-payment-notificatin.png
---

>>> This plugin was removed from version 4.2.1. Please use **[Membership Pro - Incomplete Payment Subscriptions Notification](/scheduled-tasks/offline-recurring-invoice)** scheduled task instead.

Each time the plugin runs, it will check and send notification to administrators list of subscription records which failed to process payment for the registration (payment processing error or users ignore the payment process....). By default, it will be run every 12 hours, you can change **Cache Time (Hours)** parameter to have it run more often if needed (for example, every 4 hours)

## Configure The Plugin
To use this plugin, you need to go to **System -> Plugins**, find and enable **System - Incomplete Payment Subscription Notification** plugin. It has following parameters, you can be changed it to meet your own need:

- **Notification Emails**: Enter emails you want to receive notification, comma separated. For example email1@domain.com,email2@domain.com. If you leave it empty, the **Notification Emails**  in event or in Membership Pro -> Configuration will receive notifications.
- **Subject**: Subject of the notification email.
- **Message**: Message of the notification email.

## Supported Tags
- Use [IDS] tag to show IDs of the subscription records which did not complete payment (comma separated)
- Use [LINKS] tag to show IDs of these registration records and link to each subscription record (from backend subscriptions management)

![incomplete-payment-notificatin](incomplete-payment-notificatin.png "incomplete-payment-notificatin")
