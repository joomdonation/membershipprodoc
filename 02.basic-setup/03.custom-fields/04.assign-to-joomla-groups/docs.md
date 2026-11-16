---
title: 'Assign to Joomla Groups'
media_order: joomla-groups.png
---

**Membership Pro** allows assigning subscribers to Joomla user groups you want base on value of a custom field which they choose during subscription process. For example, you can have a **Membership Option** custom field and if subscribers choose choose **3 Months**, they will be assigned to **3 Months Membership** user group, if they choose **6 Months**, they will be assigned to **6 Months Membership** user group and so on... Below you can see setup instructions:

1. Go to Users => Groups, create 3 new Joomla User Groups : **3 Months Membership**, **6 Months Membership**, **9 Months Membership**. Let's says these 3 groups has ID: **10, 11, 15**
2. Go to **Membership Pro => Custom Fields**, create a custom field with following important settings:
* **Field Type**: **List** or **Radio**
* **Values**: **3 Months**, **6 Months**, **9 Months** (each value in one line)
* **Joomla Group Ids**: **10**, **11**, **15** (each value in one line)

Please note that there is a mapping 1;1 between the value of an option with ID of the Joomla User Group which subscribers will be assigned to when they select that option.

![joomla-groups](joomla-groups.png "joomla-groups")