---
title: Tools
taxonomy:
    category:
        - docs
---

When you access to most of the pages in **Membership Pro** backend, at the right, there is a menu called Tools which you might need to use in some special cases as explained below:

## Tools -> Fix Database Schema
This tool is usually used when you update from old version of Membership Pro to new version but the update process was failure for some reasons (or when you import Membership Pro data from a different site - using an older version of Membership Pro than the current site). Access to this menu item will help updating database schema to latest version and make sure Membership Pro works properly on your site.

In case you could not access to Membership Pro for some reasons (because SQL error), the tool can be accessed directly via this URL https://domain.com/administrator/index.php?option=com_osmembership&task=update.update (of course https://domain.com/administrator needs to be replaced with administrator URL of your site)

## Tools -> Purge URLs
Membership Pro stores all of it's URLs in database table called **#__osmebership_urls**. These urls are **cached URLs**, mean urls might still point to old resources in some special case (for example, when you imported Membership Pro data from a differnt site to this new site or you created a plan with same title in the past, then delete it for some reason and re-create a new plan with exactly same title/alias)

That's when you have to Purge URLs so that Membership Pro will re-create new URLs and point it to new resource. Access to **Tools -> Purge URLs** usually help solving these issue. 

In case you could not access to Membership Pro for some reasons (because SQL error), the tool can be accessed directly via this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.reset_urls (of course https://domain.com/administrator needs to be replaced with administrator URL of your site)


## Make field sort and searchable
By default, Membership Pro only allow sorting and searching subscriptions for core fields (such as first_name, last_name, email....). If for you want to search for subscription records base on data of a custom field, you can use this tool

1. Login to administrator area of your site
2. Access to this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.make_field_search_sort_able&field_id=100 . Of course:
- https://domain.com/administrator needs to be repalced with administrator URL of your site
- 100 will need to be replaced with the ID of the custom field which you want to be searchable

## Support More Decimal Number
By default, Membership Pro only allows you to setup Price, Tax Rate...with 2 decimal number. If for some reasons, you want to setup price with more decimal number, use this tool. Just login to administrator area of your site and access to this URL

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.alter_price_fields

(Replace https://domain.com/administrator/ with administrator URL of your site)

## Trigger onMembershipActive event for active subscriptions
Sometime, you might want to trigger **onMembershipActive** for active subscriptions on your site (for example, you have active subscriptions and now want to assign them to certain user groups via Joomla Groups Plugins - you did not setup Joomla Groups plugin before)

For this, you can run this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_active_event

The above URLs will trigger **onMembershipActive** event for all active subscriptions and run it for every plugins. If you want to limit it to process certain plugin only (for example, joomlagroups, mailchimp,acym,acymailing....), you can pass that plugin in the URL like https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_active_event&plugin=joomlagroups

## Trigger onMembershipExpire event for expired subscriptions
Sometime, you might want to trigger **onMembershipExpire** for expired subscriptions on your site (for example, you have active subscriptions and now want to assign them to certain user groups via Joomla Groups Plugins - you did not setup Joomla Groups plugin before)

For this, you can run this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_expired_event

The above URLs will trigger **onMembershipExpire** event for all active subscriptions and run it for every plugins. If you want to limit it to process certain plugin only (for example, joomlagroups, mailchimp,acym,acymailing....), you can pass that plugin in the URL like https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_expired_event&plugin=joomlagroups

## Update Recurring Payment Amount
Sometime, you might want to change price of your recurring subscription plan. Normally, when you change that price, that new price will only affect new subscriptions, existing subscriptions will still have old price. However, in some special cases, you would want existing subscriptions will use new price for next payment, too. For that, you will have to:
- Login to the payment gateway, find all existing subscriptions, update it to use the new price
- Update the recurring payment amounts stored in Membership Pro to that new amount so that the email sent to user will contains that new amount. For this, you can use this tool
https://domain.com/administrator/index.php?option=com_osmembership&task=tool.update_recurring_payment_amounts&plan_id=[ID_OF_PLAN]&regular_amount=[AMOUNT]&regular_discount_amount=[DISCOUNT_AMOUNT]&regular_tax_amount=[TAX_AMOUNT]&payment_processing_fee=[PAYMENT_PROCESSING_FEE]&regular_gross_amount=[REGULAR_GROSS_AMOUNT]

In most cases, you would only care about the amount users have to pay for each recurring payment (no tax, no discount amount, no payment processing fee...) and in that case, the URL will just be simple like this

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.update_recurring_payment_amounts&plan_id=[ID_OF_PLAN]&regular_amount=[AMOUNT]

Note that:

https://domain.com/administrator/ needs to be replaced with administrator URL of your site
[ID_OF_PLAN] needs to be replaced with ID of the subscription plan which is needs to change price
[AMOUNT] needs to be replaced with the price/amount subscribers have to pay for each recurring payment

## Update state data to use state 2 code
Membership Pro stores state data for each subscription uses state 2 code (2 characters length). If for some reasons (for example, the data is imported from CSV file), you have state data with full state name instead of state 2 code and want to correct it, you can use this tool:

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_state_2code_data

(Replace https://domain.com/administrator/ with administrato URL of your site)

## Fix Row size too large error

On a multilingual website, specially when you have many languages installed, the system will need to add more fields to it's database tables to store data for these additional languages and could cause this **Row size too large (> 8126)** error. When it happens, you can follow the instructions below to get the issue sorted:

1. Login to administrator area of your site
2. Access to the two urls below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_row_size
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_row_size2

## Delete PDF Invoices
If invoice is enabled on your site, it will be generated for each paid subscription and stored on a folder on your server. If you want to have these PDF invoices deleted to save server space, you can use this tool.

1. Login to administrator area of your site
2. Access to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.remove_pdf_invoices

## Delete PDF Member Cards
If member card is enabled on your site, it will be generated and stored on a folder on your server. If you want to have these PDF member cards deleted to save server space, you can use this tool.

1. Login to administrator area of your site
2. Access to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.remove_pdf_member_cards

## Delete Orphan Files
If you use **File** custom field on your site, there might be orphan files left on your server (files upload by users but not associated to any subscription records - for example - uploaded but users did not process subscription). For that, you might want to delete these orphan files to clean up, save hosting space:

1. Login to administrator area of your site
2. Access to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.delete_orphan_files


## Sort countries by name
1. Login to administrator area of your site
2. Access to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.order_countries_by_name

## Import Joomla Users

Sometime, you might want to import users from certain Joomla user groups into certain the plan you want. To do that:

1. Login to administrator area of your site
2. Access to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_joomla_users_to_plan&plan_id=[PLAN_ID]&user_group_ids=[ID_OF_USER_GROUP]

- Replace - https://domain.com/administrator/ by administrator URL of your site
- [PLAN_ID] by ID of the plan you want to add users to
- [ID_OF_USER_GROUP] by ID of user group you want

For example  https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_joomla_users_to_plan&plan_id=3&user_group_ids=8 will add users from User Group With ID = 8 into plan with ID = 3

## Sending Up To 6 Reminder Emails

By default, Membership Pro only allows sending maximum 3 reminders email. From version 4.2.2, we added a hidden tool to allow you to send up to 6 reminder emails in Membership Pro. If you want to use these extra reminders:

1. Login to administrator area of your site
2. If you want to send up to 4 reminder emails (one extra compare to default), access to this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_fourth_reminder_fields
3. If you want to send up to 5 reminder emails (one extra compare to default), access to this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_fifth_reminder_fields
4. If you want to send up to 6 reminder emails (one extra compare to default), access to this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_sixth_reminder_fields

After that, you can now edit the plan, configure it to send extra reminder emails. You also need to go to Membership Pro -> Emails & Messages, find the message items below and enter subject and message of these extra reminder emails:

- fourth_reminder_email_subject
- fourth_reminder_email_body
- fifth_reminder_email_subject
- fifth_reminder_email_body
- sixth_reminder_email_subject
- sixth_reminder_email_body

## Generate Membership ID

You might forgot to enable Membership ID feature in the extension at the time you setup the extension. After the extension running for certain time, you want to use the feature and need to generate Membership ID for existing subscribers. To do that, you can use this tool:

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.generate_membership_id

Of course, you need to replace - https://domain.com/administrator/ by administrator URL of your site 