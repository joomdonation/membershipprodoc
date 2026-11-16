---
title: 'Database error after updating to latest version'
---

Sometime, after updating from old version to latest version of the extension, you see an SQL error while working with the extension. The reason is because in new version, the extension add some fields to database and for some reason, upgrade was not success and these fields are not added. To solve this issue, you can:

1. Login to administrator area of your site
2. Access to Membership Pro, then Tools -> Fix Database Schema.

After that, the database schema will be updated to latest version and you should not get error anymore. You can also run that tool by access to this URL directly after login to administrator area of your site:

https://domain.com/administrator/index.php?option=com_osmembership&task=update.update

(Of course https://domain.com/administrator must be replaced with URL to access to administrator area of your site)


