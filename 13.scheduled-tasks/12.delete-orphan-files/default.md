---
title: 'Delete Orphan Files'
media_order: delete_orphan_files.png
published: true
---

If you create **File** custom field types to allow subscribers to upload files during the subscription process, when users access to subscription form, they might upload files but did not finish registration. These orphan files will be left on server, cost hosting space for no benifit. You can create a scheduled task have these orphan files deleted automatically to clean up the folder, save hosting space

## Create and configure the scheduled task

1. Go to **System -> Plugins** and make sure the **Task - Membership Pro** plugin is enabled.
2. Go to **System -> Scheduled Tasks**, click the **New** button in the toolbar to create a new scheduled task for **Membership Pro - Delete Orphan Files** task type.
3. Configure the required parameters and save the task.

## Task Basic Fields
This scheduled task should not be run so often. Run it every few days should be enough. So you can setup **Basic Fields** to following values

- **Execution Rule**: Set to **Interval, Days**
- **Interval in Days**: Set to the number you want, for example, if you set it to 1, the task will be run every 1 days. 
- **Execution Time (UTC)**: Choose the time in the day the task will be executed, for example 10:00 AM. 
- **Hours to delete orphan files after**: Enter number of hours here. By default, the system keeps these orphan files for 72 hours, mean 3 days. You can lower the number if required, but should keep it for at least 24 hours, just in case something happens with payment process, the file still be kept