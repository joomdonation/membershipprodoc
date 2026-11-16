---
title: 'Joomla Groups integration'
taxonomy:
    category:
        - docs
media_order: joomla-groups-integration.png
---

This is a common usage in **Membership Pro**. Usually, you will want that when users sign up for a subscription plan, they will be assigned to the **Joomla user group(s)** you want so that you can use Joomla core ACL to give them permissions to perform some actions or access to restricted resources on your site (of course, these resources are not available for public and normal registered users). Please follow the steps below to setup it if you want to have this feature:
1. Login to back-end of your site as a super admin account.
2. Access to Users -> Groups, Create a new Joomla group on your site, maybe calling that group as **Subscriber**. This group should be child group of **Registered** group
3. Go to **System -> Plugins**, find and enable the **Membership Pro - Joomla Groups plugin** plugin

Now, when you add/edit a subscription plan, you will see a new tab called **Joomla Groups Settings**. On this tab, there are two sections:

### When subscription active
* **Assign to Joomla Groups**: Choose the Joomla user group(s) you want subscribers will be assigned to when they sign up for this subscription plan. For example, in this case, you can choose **Subscriber** group which you just created.
* **Remove from Joomla Groups**: Choose the Joomla user group(s) you want subscribers will be removed from when they sign up for this subscription plan. Usually, you don't need to choose any user groups(s) here unless in **When subscription expired** section, you choose to assign expired subscribers to certain user group (like **Expired Members**) and if you do so, you should choose to remove them from that **Expired Members** when they subscribe for this plan.

### When subscription expired

* **Remove from Joomla Groups**: Choose the Joomla user group(s) which you want subscribers of this plan will be removed from when their subscription for this plan is expired. Usually, it should be the same with the groups you selected in **Assign to Joomla Groups** setting under **When subscription active** section. For example, in this case, you can choose **Subscriber** user group.
* **Assign to Joomla Groups**: Choose the Joomla user group(s) you want subscribers will be assigned to their subscription for this plan is expired. Usually, you don't need to choose any user groups(s) here unless you want to assign expired subscribers to **Expired Members** user group for example for managing purpose.

With the above setup, when subscribers sign up to this subscription plan, they will be assigned to **Subscriber** user group and they can access to the resources which you give to **Subscriber** user group. When their subscription for this plan is expired, they will be removed from **Subscriber** group, thus they cannot access to these resources anymore (unless they renew their membership).

If you want to restrict access to resources based on Joomla core ACL (you need to understand how Joomla ACL works), this will be a very powerful and flexible plugin.

![joomla-groups-integration](joomla-groups-integration.png "joomla-groups-integration")