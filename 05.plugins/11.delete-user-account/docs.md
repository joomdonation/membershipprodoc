---
title: 'Delete User Account'
taxonomy:
    category:
        - docs
media_order: delete-user-account.png
published: true
---

You might want to delete the Joomla user account of the subscriber when all of his subscription records are deleted from Membership Pro. To do that, please go to System -> Plugins, find **Membership Pro - Delete User Account** plugin and enable it. The plugin has a parameter called **Exclude User Groups** which prevent the account to be deleted by the plugin if the user belong to the configured user groups. 

By default, all important user groups in Joomla like Super Users, Administrator, Editor, Publisher... are configured to be excluded. You might want to adjust the parameter to meet your own need.

![delete-user-account](delete-user-account.png "delete-user-account")