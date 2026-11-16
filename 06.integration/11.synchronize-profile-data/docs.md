---
title: 'Synchronize Profile Data'
media_order: plug_cbmembershippro.zip
taxonomy:
    category:
        - docs
---

Membership Pro has plugins to allow you to synscronize subscriber's data which is stored in Membership Pro with **Joomla User Profile** and third party extensions. Right now, the folllowing third party extensions are supported: **Community Builder**, **Jomsocial**, **Jomsocial**, **EasyProfile**.

1. When users sign up in Membership Pro, if he has an existing account, the data stored in his profile (**Joomla User Profile or third party extensions profile**), the data from his profile will be used to fill-in subscription form automatically so that he won't have to type the information again. If he changes data of any fields on subscription form, the changed will be synchronized back to his profile (**Joomla User Profile or third party extensions profile**)
2. When users sign up in Membership Pro, if he doesn't have an existing account (**Joomla account or third party extensions account**), Membership Pro will create a Joomla account for him and update the profile (**Joomla User Profile or third party extensions profile**) with the data which subscriber entered on subscription form.
3. When subscriber access to his profile page in Membership Pro and update his profile data, the changes will be updated to **Joomla User Profile or third party extensions profile**.
4. **The integration is one way only**. That means the change in Membership Pro will be synchronized to **Joomla User Profile or third party extensions profile** but the changes from Joomla User Profile or third party extensions profile won't be updated back to Membership Pro. Maybe in the future, we will have two ways integration, but at the time of this writing, it is not supported.

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
You might have to go to **Users** -> **Manage**, click on **Options** button in the toolbar, select **Public** user group, set **Edit Custom Field Value** permission to **Allowed**. That will allow **Membership Pro** to save data to Joomla User Custom Fields when users first subscribe for your plan (they do not have user account yet)

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