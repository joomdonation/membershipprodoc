---
title: 'QRCODE Scanner'
media_order: 'frontend-subscriptions-management.png,manage-subscriptions-permission.png,my_downloads.png,my_pages.png,my_schedule_content.png,access_resources_from_profile.png'
published: true
---

This menu item type opens the built-in QR code scanner so you can check a user's **Membership Status** for a subscription plan.

1. Enable the [Member Card](/basic-setup/membership-card) feature.
2. In Member Card Layout, insert the [QRCODE] tag where you want the QR code to appear on the card.
3. Create a menu item using the QRCODE Scanner menu item type.
4. On your mobile device, log in to the site with an account that has the **Manage Subscriptions** permission.
5. Open the menu item you created in step 3.

Scan the QR code on the member's card to see their subscription status, such as pending, active, or expired.

## Customize the membership status message

Membership Pro displays a subscription status message when you scan the QR code. To customize the message, go to Membership Pro -> Translation and edit the relevant language item.

- OSM_CHECK_MEMBERSHIP_STATUS_PENDING
- OSM_CHECK_MEMBERSHIP_STATUS_ACTIVE
- OSM_CHECK_MEMBERSHIP_STATUS_EXPIRED
- OSM_CHECK_MEMBERSHIP_STATUS_CANCELLED_PENDING
- OSM_CHECK_MEMBERSHIP_STATUS_CANCELLED_REFUNDED

You can include email message tags, such as **[FIRST_NAME]**, **[LAST_NAME]**, **[EMAIL]**, **[PLAN_TITLE]**, **[FROM_DATE]**, and **[TO_DATE]**, to display more subscription information.