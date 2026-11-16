---
title: 'Migrate from Akeeba Subscription To Membership Pro'
media_order: 'os_osm_paypal.zip,com_aks2membershippro.zip,plug_system_osmembershipakeeba.zip'
published: true
---

**Akeeba Subscription** was a popular Membership extension for Joomla. For some reasons, the author of that extension discountinued support for the product, made it a developer product only,so I decided to develop a migration script to allow migrating data from **Akeeba Subscription to Membership Pro**. The following data could be migrated:
1. Level Groups -> Membership Pro categories
2. Subscription Levels -> Membership Pro subscription plans
3. Subscriptions

Further more, if you use recurring subscription in Akeeba subscription, these recurring subscriptions will still work well in Membership Pro (when PayPal notify Akeeba subscription about the recurring payment, there will be a plugin routing this notification into Membership Pro and Membership Pro will extend the related recurring subscription)

If you want to migrate from Akeeba Subscription into Membership Pro, please follow the instructions below:

1. Go to Extensions -> Manager, install this component **com_aks2membershippro.zip**. You can get it here [com_aks2membershippro.zip](com_aks2membershippro.zip)
2. Now, access to **Components -> Akeeba Subscription to Membership Pro migrator** to perform the migration:
* If you want to **delete existing membership pro data** (categories, plans, subscriptions) to perform the migration from scratch, click on **CLEAR EXISTING DATA** button.   
* Then click on **Start the migration** button. The migrator component will perform the migration, wait until the process completed.
3. Check the subscription plans in Membership Pro again, make sure it is all correct
4. If your Akeeba Subscriptions setup has recurring subscriptions, you need to do the additional steps below:
* Go to Extensions -> Manager, install and publish this plugin **plug_system_osmembershipakeeba.zip**, you can get the plugin here [plug_system_osmembershipakeeba.zip](plug_system_osmembershipakeeba.zip)

Congratulations! You are done. All the important data in **Akeeba Subscriptions** was successfully migrated to Membership Pro and you can now turn disable **Akeeba Subscriptions** extension on your Joomla site.
    
