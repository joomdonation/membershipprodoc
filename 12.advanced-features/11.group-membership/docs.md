---
title: 'Group Membership'
taxonomy:
    category:
        - docs
---

Group Membership is a nice / unique feature of Membership Pro. It allows you to set up a subscription plan so that when someone sign up for the plan, he will become group admin and can add/ remove group members to/ from his group:

1. Group members will have same access level with group admin, so they can view any restricted resources you give access to subscribers of that plan. The only difference is that group members could not add new members to the group like group admin
2. When group admin renew his subscription, subscription for all groups members will also be renewed
3. The number of group members which a group admin can add to his group can be controlled via a setting of the subscription plan or by the value which group admin choose/enter when he signs up for the plan, depend on how the plan is set up.

To setup this feature, please follow the steps below:

## Enable Group Membership For Plan
The maximum number group members which group admin can add into his group can be a **Fixed Number** (determine by admin when setup the plan) or a **Dynamic Number** (determined by group admin when he subscribe/renew his subscription for the plan).

1. If you want to allow **fixed number members** for the group, set **Number Members Type** setting of the plan to **Fixed Number**, then enter number of group members you want group admin can add to his group into **Max Number Of Group Members** input box. Save the plan.
2. If you want group admin to decide number of group members himself:
+ Create a custom field to allow admin to choose/enter number of members for his group. Usually, it should be a custom fee fleld because he should be charged different fees, depend on number of group members. You can use a **List** or **Text/Number** custom fee fields for that. See [https://docs.joomdonation.com/membershippro/basic-setup/custom-fields/custom-fee-fields#radio-list-single-dropdown-custom-field-type](/basic-setup/custom-fields/custom-fee-fields#radio-list-single-dropdown-custom-field-type) or [https://docs.joomdonation.com/membershippro/basic-setup/custom-fields/custom-fee-fields#textbox-custom-field-type](/basic-setup/custom-fields/custom-fee-fields#textbox-custom-field-type)
+ Set **Number Members Type** setting of the plan to **From Custom Field**, then choose the custom field which you created above in **Number Members Field** setting.

## Setup Manage Group Members Menu Item
To allow group admin to manage group members, create a menu item to link to **Manage Groups Members** menu item type of Membership Pro. After that, when someone signed up for the plan you just setup, he can login, access to the menu item to add/manage his group members.

Usually, you will just want that only group admin can see the menu item which you created in step #3 above. We can handle it using Joomla core ACL with a clever setup. Below are the steps:

1. Create a new Joomla group called **Group Admin** for example. This should be child group of **Registered** group. Remember ID of this group, we need it in later step.
2. Create an access level called **Group Admin**, only select **Group Admin group** for that access level
3. Config the subscription plan so that when user sign up for the plan, beside the groups you want, he will be assigned to **Group Admin** Joomla group as well
4. Go to **Extensions -> Plugins**, find the plugin **OS Membership - Group Membership Plugin**, click on it to edit. You will see a parameter called **Exclude Group Ids**. By default, it has the value 7, 8 (IDs of Administrator and Super Admin Group), please enter ID of the **Group Admin** into that parameter (separated by comma), for example, if Group Admin has ID = 10, please enter 7,8,10 into that parameter. The purpose of doing this step is that it prevent Group Members being assigned to this **Group Admin** joomla group so that they won't see the menu item.
5. Edit the menu item which you created before, set access to **Group Admin**. With this set up, only group admin can see and access to this menu item

## Invite Users To Join Group
From Manage Group Members, group admin can click on Invite Members button to invite the users he want to join the group. The email message on invite form is pre-populated by the default message setup by administrator of the site. You should go to Membership Pro -> Emails & Messages, find and change **invite_group_members_message** to meet your own need if needed. It's important that [JOIN_GROUP_LINK] tag is included in the message, that's the link members can click on to join the group when they received email.

## Allow Members To Join Group Membership
Starting with version 2.22.1, **Membership Pro** allows group admin to send join link to his members so that these members can click on the link, enter necessary information to join the group instead of group admin has to add all group members himself. To use this option:

- Create a hidden menu item to link to **Join Group** menu option of Membership Pro (note that this should not be displayed to end user - it is used to create link to Join Group page only)
- Edit the email message sent to subscribers when they sign up for your plan, insert the tag [JOIN_GROUP_LINK]. That link will be replaced with link to join the group
- Go to Membership Pro -> Emails & Messages, look at Group Membership Messages tab, adjust the email messages to suit your needs if needed

With that setup, when admin signs up for a group membership plan, he will receive an email contains join group membership link. He can then send that link to his members and these members can join the group themselves. Save Group Admin much time.