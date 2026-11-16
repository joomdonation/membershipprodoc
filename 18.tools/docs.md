---
title: Tools
taxonomy:
    category:
        - docs
---

The Tools menu appears on the right of most pages in the **Membership Pro** backend. The sections below explain when to use each tool.

## Tools -> Fix Database Schema
Use this tool to bring the database schema up to date after a failed upgrade or after importing data from a site that runs an older version of Membership Pro.

In case you could not access to Membership Pro for some reason (because SQL error), the tool can be accessed directly via this URL https://domain.com/administrator/index.php?option=com_osmembership&task=update.update (of course https://domain.com/administrator needs to be replaced with administrator URL of your site)

## Tools -> Purge URLs
Membership Pro stores all of it's URLs in database table called **#__osmebership_urls**. These urls are **cached URLs**, mean urls might still point to old resources in some special case (for example, when you imported Membership Pro data from a differnt site to this new site or you created a plan with same title in the past, then delete it for some reason and re-create a new plan with exactly same title/alias)

Use **Tools -> Purge URLs** to clear the cache so Membership Pro can generate URLs that point to the correct resources.

In case you could not access to Membership Pro for some reason (because SQL error), the tool can be accessed directly via this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.reset_urls (of course https://domain.com/administrator needs to be replaced with administrator URL of your site)


## Make field sort and searchable
By default, you can sort and search subscriptions by core fields such as first_name, last_name, and email. Use this tool to make a custom field searchable.

1. Log in to administrator area of your site
2. Access to this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.make_field_search_sort_able&field_id=100. Of course:
- https://domain.com/administrator needs to be repalced with administrator URL of your site
- 100 will need to be replaced with the ID of the custom field which you want to be searchable

## Support More Decimal Number
By default, Membership Pro supports two decimal places for values such as Price and Tax Rate. To support more decimal places, log in to your site's administrator area and open the following URL.

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.alter_price_fields

(Replace https://domain.com/administrator/ with administrator URL of your site)

## Trigger onMembershipActive event for active subscriptions
Sometimes, you might want to trigger **onMembershipActive** for active subscriptions on your site (for example, you have active subscriptions and now want to assign them to certain user groups via Joomla Groups Plugins - you did not setup Joomla Groups plugin before)

For this, you can run this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_active_event

The above URLs will trigger **onMembershipActive** event for all active subscriptions and run it for every plugins. If you want to limit it to process certain plugin only (for example, joomlagroups, mailchimp,acym,acymailing....), you can pass that plugin in the URL like https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_active_event&plugin=joomlagroups

## Trigger onMembershipExpire event for expired subscriptions
Sometimes, you might want to trigger **onMembershipExpire** for expired subscriptions on your site (for example, you have active subscriptions and now want to assign them to certain user groups via Joomla Groups Plugins - you did not setup Joomla Groups plugin before)

For this, you can run this URL https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_expired_event

The above URLs will trigger **onMembershipExpire** event for all active subscriptions and run it for every plugins. If you want to limit it to process certain plugin only (for example, joomlagroups, mailchimp,acym,acymailing....), you can pass that plugin in the URL like https://domain.com/administrator/index.php?option=com_osmembership&task=tool.trigger_expired_event&plugin=joomlagroups

## Update Recurring Payment Amount
Sometimes, you might want to change price of your recurring subscription plan. Normally, when you change that price, that new price will only affect new subscriptions, existing subscriptions will still have old price. However, in some special cases, you would want existing subscriptions will use new price for next payment, too. For that, you will have to:
- Log in to the payment gateway, find all existing subscriptions, update it to use the new price
- Update the recurring payment amounts stored in Membership Pro to that new amount so that the email sent to user will contains that new amount. For this, you can use this tool
https://domain.com/administrator/index.php?option=com_osmembership&task=tool.update_recurring_payment_amounts&plan_id=[ID_OF_PLAN]&regular_amount=[AMOUNT]&regular_discount_amount=[DISCOUNT_AMOUNT]&regular_tax_amount=[TAX_AMOUNT]&payment_processing_fee=[PAYMENT_PROCESSING_FEE]&regular_gross_amount=[REGULAR_GROSS_AMOUNT]

In most cases, you would only care about the amount users have to pay for each recurring payment (no tax, no discount amount, no payment processing fee...) and in that case, the URL will just be simple like this

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.update_recurring_payment_amounts&plan_id=[ID_OF_PLAN]&regular_amount=[AMOUNT]

Note that:

https://domain.com/administrator/ needs to be replaced with administrator URL of your site
[ID_OF_PLAN] needs to be replaced with ID of the subscription plan which is needs to change price
[AMOUNT] needs to be replaced with the price/amount subscribers have to pay for each recurring payment

## Update state data to use state 2 code
Membership Pro stores state data for each subscription uses state 2 code (2 characters length). If for some reason (for example, the data is imported from CSV file), you have state data with full state name instead of state 2 code and want to correct it, you can use this tool:

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_state_2code_data

(Replace https://domain.com/administrator/ with administrato URL of your site)

## Fix Row size too large error

On a multilingual website, specially when you have many languages installed, the system will need to add more fields to it's database tables to store data for these additional languages and could cause this **Row size too large (> 8126)** error. When it happens, you can follow the instructions below to get the issue sorted:

1. Log in to administrator area of your site
2. Go to the two urls below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_row_size
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.fix_row_size2

## Delete PDF Invoices
When invoicing is enabled, Membership Pro generates a PDF for each paid subscription and stores it on your server. Use this tool to delete those PDFs and free up disk space.

1. Log in to administrator area of your site
2. Go to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.remove_pdf_invoices

## Delete PDF Member Cards
When member cards are enabled, Membership Pro generates the cards and stores them on your server. Use this tool to delete the PDF member cards and free up disk space.

1. Log in to administrator area of your site
2. Go to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.remove_pdf_member_cards

## Delete Orphan Files
A **File** custom field can leave uploads on your server that are no longer associated with a subscription record. For example, a user might upload a file and then abandon the subscription process. Use this tool to delete those files and free up disk space.

1. Log in to administrator area of your site
2. Go to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.delete_orphan_files


## Sort countries by name
1. Log in to administrator area of your site
2. Go to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.order_countries_by_name

## Import Joomla Users

Follow these steps to add users from selected Joomla user groups to a plan.

1. Log in to administrator area of your site
2. Go to the url below (replace https://domain.com/administrator with administrator url of your site)
- https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_joomla_users_to_plan&plan_id=[PLAN_ID]&user_group_ids=[ID_OF_USER_GROUP]

- Replace - https://domain.com/administrator/ by administrator URL of your site
- [PLAN_ID] by ID of the plan you want to add users to
- [ID_OF_USER_GROUP] by ID of user group you want

For example  https://domain.com/administrator/index.php?option=com_osmembership&task=tool.add_joomla_users_to_plan&plan_id=3&user_group_ids=8 will add users from User Group With ID = 8 into plan with ID = 3

## Sending Up To 6 Reminder Emails

By default, Membership Pro only allows sending maximum 3 reminders email. Starting with version 4.2.2, we added a hidden tool to allow you to send up to 6 reminder emails in Membership Pro. If you want to use these extra reminders:

1. Log in to administrator area of your site
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

If you enable membership IDs after subscribers have already signed up, use this tool to generate IDs for those subscribers.

https://domain.com/administrator/index.php?option=com_osmembership&task=tool.generate_membership_id

Of course, you need to replace - https://domain.com/administrator/ by administrator URL of your site 