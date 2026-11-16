---
title: 'Delete Old Subscriptions'
media_order: task-delete-old-subscriptions.png
published: true
---

This scheduled task is used to deletes subscriptions older than certain Number Of Years (by default 10 years). Normally, you would not need to use this feature. However, it was asked by one customer, so we added support for it. To use this feature:

## Create and configure the scheduled task

1. Go to **System -> Plugins**, make sure **Task - Membership Pro** plugin is enabled.
2. Go to **System -> Scheduled Tasks**, press New button in the toolbar to create a new scheduled task for **Membership Pro - Delete Old Subscriptions** task type.
3. Setup all required parameters, save it.

![task-delete-old-subscriptions](task-delete-old-subscriptions.png "task-delete-old-subscriptions")

## Task Basic Fields
This scheduled task should not be run so often. Run it every few days should be enough. So you can setup **Basic Fields** to following values

- **Execution Rule**: Set to **Interval, Months**
- **Interval in Months**: Set to the number you want, for example, if you set it to 3, the task will be run every 3 months.
- **Execution Day**: Choose the day in month you want the task to be executed (for example, set it to 1 and it will be run on the first day of month)
- **Execution Time (UTC)**: Choose the time in the day the task will be executed, for example 10:00 AM.

## Task Parameters
- **Years to delete old subscriptions after**:  Enter a number here (for example 10) and subscription records older than that number of years will be deleted each time the task is executed.