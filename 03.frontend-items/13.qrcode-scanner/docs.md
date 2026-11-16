---
title: 'QRCODE Scanner'
media_order: 'frontend-subscriptions-management.png,manage-subscriptions-permission.png,my_downloads.png,my_pages.png,my_schedule_content.png,access_resources_from_profile.png'
published: true
---

This menu item type allows you to use build-in QRCODE scanner to check **Membership Status** of a subscription plan of certain user. To use it:

1. Enable and use [Member Card](/basic-setup/membership-card) feature
2. In Member Card Layout, enter [QRCODE] tag in the position you want. That will render a QRCODE in Member Card
3. Setup a menu item to link to QRCODE Scanner menu item type
4. Login to the site (from your mobile) using an account which have **Manage Subscriptions** permission. 
5. Access to the menu item which you created in step 3. 

When your user bring their member card to you, you can can scan QRCODE in the member card. It will show subscription status of that member (pending, active, expired).

## Customize the membership status message

When you scan the QR CODE, Membership Pro will show a message show you the subscription status of the member. The message is controlled by the following language items, and you can go to Membership Pro -> Translation to find and change it:

- OSM_CHECK_MEMBERSHIP_STATUS_PENDING
- OSM_CHECK_MEMBERSHIP_STATUS_ACTIVE
- OSM_CHECK_MEMBERSHIP_STATUS_EXPIRED
- OSM_CHECK_MEMBERSHIP_STATUS_CANCELLED_PENDING
- OSM_CHECK_MEMBERSHIP_STATUS_CANCELLED_REFUNDED

You can use same tags with the tags supported in email message (**[FIRST_NAME]** , **[LAST_NAME]**, **[EMAIL]**, **[PLAN_TITLE]**, **[FROM_DATE]**, **[TO_DATE]**.... in the message to show more information you want for the subscription.