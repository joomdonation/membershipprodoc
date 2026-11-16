---
title: 'Installation & Upgrade'
taxonomy:
    category:
        - docs
---

## Installation
When you purchase **Membership Pro** extension from our site, you will receive an email contain the extension in a zip file called **membershippro_unzip_first.zip**. Unzip this file you will see a folder **Language Packages** and a zip file **com_osmembership.zip**. The component, all the modules and plugins are included in this single zip file. The installation process is simple, it can be installed in the same way with you install any other Joomla extensions:

1. Login to back-end of your site using a super administrator account.
2. Access to **Extensions -> Manage -> Install** menu item.
3. Browse for the file **com_osmembership.zip**.
4. Click on **Upload & Install** button

After the installation process completed, you will be redirected to dashboard screen to start configuring and settting up the extension.

![Dashboard](dashboard.png)

## Check for new version

To see whether your site is running on latest version of Membership Pro or not, you can go to **Membership Pro => Dashboard**,  look at the update notification icon at the bottom right (see the screenshot below):

![Update Notification Icon](update_notification.png)

1. If you are using latest version, you will see this text : **Membership Pro is up-to-date**. In this case, no update is require.
2. If your site is not running latest version, you will see the text like this: **Membership Pro 2.1.0 Update now!**. In this case, your site is running an out-dated version and you should download latest version to update to your site. To download latest version, go to [https://joomdonation.com](https://joomdonation.com), login to your account, then access to [My Downloads](https://joomdonation.com/my-downloads.html) menu item, download latest version and follow the instruction in Upgrade section below to upgrade it to your site.

## Upgrade
The process for upgrading Membership Pro to latest version is the same with new installation. Please note that:

1. Please don't uninstall old version before installing new version. It is not needed. Further more, if you uninstall the old version before upgrading, you will have to re-create the menu items which you created to link to the extension before.
2. Before updating the extension to latest version, you should make a backup copy of your site so that in case something goes wrong (for any reasons), you can roll back to earlier status. We suggest you to install [Akeeba Backup](https://www.akeebabackup.com/products/akeeba-backup.html) extension and make a backup of your site before upgrading

### Use Joomla Update
**Membership Pro** allows you to use **Joomla Update** to update the extension whenever there is new version release. To use **Joomla Update**, please follow the instructions below:

1. Go to [https://joomdonation.com/download-ids.html](https://joomdonation.com/download-ids.html) , get **Download ID** of your account
2. Then go to **Membership Pro -> Configuration**, enter the received **Download ID** into **Download ID** config option.

From now on, each time there is new version of Membership Pro release, Joomla will notify you about it when you access to backend of your site (or access to Membership Pro dashboard). You just have to click on the link to update the extension from within your site, don't have to access to our site to download new version and update manually anymore, sweet :).

Please note that each site need to have an unique **Download ID** (the same **Download ID** however, **can be used for all our products**), so if you use the product on different websites, please make sure to generate new **Download ID** for each site.

### Update Manually
Sometime, you might need to update to latest version manually (for example, when Joomla Update doesn't work). In this case, login to your account on our website, then access to **My Downloads** menu item [https://joomdonation.com/my-downloads.html](https://joomdonation.com/my-downloads.html), download latest version of the extension from there. Then install that latest version in the same way as new installation.

## Uninstall
If you have to uninstall Membership Pro for some reasons (for example, you want starts from scratch - or maybe after installing and using it, you realize that it doesn't meet your requirement), you can follow the instructions below to get the extension completely uninstalled:

1. Login to backend of your site using a super admin account
2. Access to Extensions => Manage => Manage menu item.
3. Enter membership keyword into the search box to search for membership pro component and all it's modules, plugins (see the screenshot)
4. Check on the items you want to un-install (look at Author column, it must be **Tuan Pham Ngoc** to make sure the extension belong to **Membership Pro** package)
5. Click on **Uninstall** button in the toolbar

![Uninstall](uinstall.png)

>>>>> When you uninstall Membership Pro, the database tables related to the extension won't be uninstalled. By doing that, when you re-install the extension in the future, all the old data will be kept and still be available. If you want to completely removing it, please access to your site database via phpmyadmin, look at all the tables with prefix **osmembership** and drop these tables

## Move data from one site to a new site
Sometime, you have to move membership pro data from one site to a new site. To do that, you will need to:
1. Export all membership pro related database tables from old site (tables with **osmembership** prefix) from the old site, import it to your new site database
2. You will have to migrate users (Joomla core users) data from old site to new site as well. To do that, you will need to export the following database tables from old site and import it to new site (of course you **jos** with the table prefix of your site)
* **jos_usergroups**
* **jos_users**
* **jos_user_keys**
* **jos_user_notes**
* **jos_user_profiles**
* **jos_user_usergroup_map**
* **jos_viewlevels**
3. If the two sites have different database table prefix, before import data in step 1 and 2 above, you will need to open the exported sql file in a text editor you like (for example, notepad++), find and replace the old site database table prefix with the new site database table prefix before running the import.
4. All the steps above should be done via PHPMYADMIN of your sites