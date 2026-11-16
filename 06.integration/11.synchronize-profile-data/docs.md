---
title: 'Synchronize Profile Data'
media_order: plug_cbmembershippro.zip
taxonomy:
    category:
        - docs
---

Membership Pro has plugins to allow you to synchronize subscriber's data which is stored in Membership Pro with **Joomla User Profile** and third party extensions. Right now, the folllowing third party extensions are supported: **Community Builder**, **Jomsocial**, **Jomsocial**, **EasyProfile**.

1. When an existing user signs up, Membership Pro fills in the subscription form from their profile (**Joomla User Profile or third party extensions profile**). This saves the user from re-entering their information. If they change a field on the form, Membership Pro syncs the change back to their profile (**Joomla User Profile or third party extensions profile**).
2. When someone signs up without an existing account (**Joomla account or third party extensions account**), Membership Pro creates a Joomla account and updates their profile (**Joomla User Profile or third party extensions profile**) with the information from the subscription form.
3. When subscribers update their details on their Membership Pro profile page, those changes sync to **Joomla User Profile or third party extensions profile**.
4. **The integration is one way only**. Membership Pro syncs changes to **Joomla User Profile or third party extensions profile**. Changes made in those external profiles do not sync back to Membership Pro.

## Joomla User Profile 
To synchronize data with **Joomla User Profile**, please follow the steps below:
1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - Userprofile plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Joomla Profile Field Mappping** property, select the corresponding field in **Joomla User Profile** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want

## Joomla User Custom Fields 
To synchronize data with **Joomla User Custom Fields**, please follow the steps below:
1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - Userprofile plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Joomla Profile Field Mappping** property, select the corresponding field in **Joomla user custom fields** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want

### Change Fields Permissions Setting
You might have to go to **Users** -> **Manage**, click the **Options** button in the toolbar, select **Public** user group, set **Edit Custom Field Value** permission to **Allowed**. That will allow **Membership Pro** to save data to Joomla User Custom Fields when users first sign up for your plan (they do not have user account yet)

## Community Builder
This feature only works if you are using [**Community Builder**](http://extensions.joomla.org/extension/community-builder) extension on your site. If you don't use Community Builder extension, please ignore this section.

To synchronize data with **Community Builder**, please follow the steps below:

1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - CB plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Field Mapping** property, select the corresponding field in **Community Builder** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want

By default, only data changed in Membership Pro is added/updated to Community Builder. If you want data changed from CB is updated to all subscription records of the user in Membership Pro, please download and install the CB Membership Pro plugin [plug_cbmembershippro.zip](plug_cbmembershippro.zip) (to support two ways data synchronization)

## Jomsocial
This feature only works if you are using [**Jomsocial**](http://www.jomsocial.com/) extension on your site. If you don't use Jomsocial extension, please ignore this section.

To synchronize data with **Jomsocial**, please follow the steps below:

1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - Joomsocial plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Field Mapping** property, select the corresponding field in **Jomsocial** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want

## EasySocial
This feature only works if you are using [**EasySocial**](http://stackideas.com/easysocial/) extension on your site. If you don't use EasySocial extension, please ignore this section.

To synchronize data with **EasySocial**, please follow the steps below:

1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - Easysocial plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Field Mapping** property, select the corresponding field in **EasySocial** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want

## EasyProfile
This feature only works if you are using [**EasyProfile**](https://www.easy-profile.com/) extension on your site. If you don't use EasyProfile extension, please ignore this section.

To synchronize data with **EasyProfile**, please follow the steps below:

1. Go to Extensions -> Plugins Manager, find and publish the plugin **Membership Pro - Easy Profile plugin**
2. Go to **Membership Pro -> Custom Fields**, click on the custom field you want to synchronize data to edit, look at **Field Mapping** property, select the corresponding field in **EasyProfile** which will be synchronized with this field. Save it.
3. Repeat step #2 for all other fields you want