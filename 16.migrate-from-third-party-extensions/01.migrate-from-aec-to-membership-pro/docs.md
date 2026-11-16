---
title: 'Migrate from AEC to Membership Pro'
published: true
media_order: 'com_aec2membershippro.zip,os_osm_paypal.zip,plug_system_aec2osmembership.zip'
---

AEC was a popular Membership extension for Joomla. For some reasons, the author of that extension discontinued the development, shut-down his website, so I decided to develop a migration script to allow migrating data from AEC to Membership Pro. The following data will be migrated:
1. Categories
2. Plans
3. Subscriptions

Furthermore, if you use recurring subscription in **AEC**, these recurring subscriptions will still work well in **Membership Pro** (when PayPal notify **AEC** about the recurring payment, there will be a plugin routing this notification into Membership Pro and Membership Pro will extend the related recurring subscription)

If you want to migrate from AEC into Membership Pro, please follow the instructions below:

1. Go to Extensions -> Manager, install this component **com_aec2membershippro.zip**. You can get it here [com_aec2membershippro.zip](com_aec2membershippro.zip)
2. Now, access to **Components -> AEC to Membership Pro migrator** to perform the migration:
* If you want to **delete existing membership pro data** (categories, plans, subscriptions) to perform the migration from scratch, click on **CLEAR EXISTING DATA** button.   
* Then click on **Start the migration** button. The migrator component will perform the migration, wait until the process completed.
3. Check the subscription plans in Membership Pro again, make sure it is all correct
4. If your AEC setup has recurring subscriptions, you need to do the additional steps below:
* Go to Extensions -> Manager, install and publish this plugin **plug_system_aec2osmembership.zip**, you can get the plugin here [plug_system_aec2osmembership.zip](plug_system_aec2osmembership.zip)

Congratulations! You are done. All the important data in AEC was successfuly migrated to Membership Pro and you can now turn disable AEC extension on your Joomla site.
