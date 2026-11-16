---
title: 'Use Joomla ACL'
visible: true
---

Every Joomla item (especially items from Joomla core) such as **Menu Items**, **Modules**, **Categories**, **Articles**, **EDocman Documents**.... has a field called **Access** to control who (users from what groups) can access/ view that item.  Base on that basic principle, we can set up Membership Pro so that only subscribers from the subscription plan(s) can access to these items (but public members and normal registered users cannot). The steps are:

1. Log in to administrator area of your site using a super admin account.
2. Access to **Users -> Groups -> Add New Group** to create a new Joomla Group called **Subscribers**. This should be child group of Registered user group.
3. Access to **Users -> Access Levels -> Add New Access Level** to create a new access level called **Subscribers**. Only choose **Subscribers** user group for this access level.
4. Follow the instructions at [Joomla Groups integration](/joomla-groups-integration) to assign subscribers of the plan to **Subscribers** group
5. Edit the item (modules, menu items, articles...) you want to allow subscribers from this memebership plan to access, set **Access** property of that item to **Subscribers** (the access level which you created in step #3)

By doing that, when users sign up for this subscription plan, they will be assigned to **Subscribers** user group, thus has **Subscribers access level** and can access/see the items which you restricted. After their subscription expires, they **will be removed from Subscribers group** and **lost the Subscribers access level**, so they could not access/see these items anymore. As you can see, we can assign subscribers of different subscription plans to different Joomla groups, so you can give them access to different restricted resources based on the plans they sign up. Hope you get the idea and can set it up to suit your needs :).