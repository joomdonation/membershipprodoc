---
title: 'Update Subscriptions Status'
media_order: scheduled-task-update-subscription-status.png
published: true
---

This scheduled task is used to update status of subscriptions to expired when current date passes their expiration date (and grace period). This should be used to replace the [System - Membership Pro Update Subscribers Status plugin](/plugins/update-subscribers-status); disable that plugin if you use this scheduled task

1. Go to **System -> Plugins**, make sure **Task - Membership Pro** plugin is enabled.
2. Go to **System -> Scheduled Tasks**, press New button in the toolbar to create a new scheduled task for **Membership Pro - Update Subscriptions Status** task type.
3. Setup all required parameters, save it.


## Task Basic Fields
This scheduled task should be run several times per day. Each time it runs, it will send reminder to 10 - 20 subscribers, so you can setup **Basic Fields** to following values

- **Execution Rule**: Set to **Interval, Hours**
- **Interval in Hours**: The value of this parameter depends on your estimation about how many subscriptions will be expired per day. Each time the scheduled task run, it will update status of maximum 20 subscriptions. Set this parameter to 1 hour for example, in a day, it will be able to update about 24 x 20 = 480 subscriptions and it will be more than enough. If you have small number of subscriptions expires per day, reduce this to 2, 4 6 or more hours...if needed. In general, set it to 1 or 2 hours would be OK for almost all sites. 

![scheduled-task-update-subscription-status](scheduled-task-update-subscription-status.png "scheduled-task-update-subscription-status")
