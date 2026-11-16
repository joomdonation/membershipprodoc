---
title: 'Advanced Subscription Start Date'
published: true
media_order: curl.png
---

By default, when users subscribe for your subscription plan, the start date of the subscription will be the datetime which they subscribe for the plan. However, sometime, you would want to change this default behavior and it could be controlled by **Subscription Start Date Option** parameter of the plan. It has the following options:

- **Register Date**: That's default behavior. With this option, start date of the subscription will be the datetime which users subscribe for your plan.
- **Fixed Date**: This option can be used if you want all subscriptions of the plan will be started at the fixed datetime you want. When you choose this option, you need to enter that fixed date time you want into **Fixed Subscription Start Date** parameter
- **Determine By Customer**: This option can be used if you want to allow your subscribers to choose the start date of the subscription himself. That mean each subscriber can have his own subscription start date. When you choose this option, you need to:
+ Create a **Date** custom field to allow subscribers to choose his own Subscription Start Date. You might want to set **Hide On Membership Renewal** to **Yes** so that he can only choose the date for new subscription only, not renewal
+ Then select that custom field in **Subscription Start Date Field** setting of the plan.

## Trigger onMembershipActive On Subscription Start Date
By default, even if you configure your plan to allow custom subscription start date, Membership Pro will still trigger **onMembershipActive** event as soon as their subscription is active (they complete payment for their subscription or admin publish the subscription in case the subscriber uses offline payment for the subscription). That mean they will be assigned to the configured Joomla User Groups, Subscribed to mailing lists... at the date they sign up, not on the actual subscription start date (in short, they will have active subscription permissions earlier than they should)

In most case, that's OK. But if you have problem with that behavior (for example, you use their Joomla groups to give discount on Events Booking, on shopping cart...), you might want to change this behavior so that the **onMembershipActive** event will only be triggered on the actual subscription start date. To have it works like that, please create a scheduled task of **[Membership Pro - Trigger Active Event](/scheduled-tasks/trigger-active-event)** task type
