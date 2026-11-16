---
title: 'Export/Import doesn''t work'
visible: true
---

Sometime, you cannot export/import subscriptions on your site and see some PHP error. It usually happens because the Zip library is not enabled on your hosting account. There are two ways to fix:

1. If you just want to export subscriptions, go to Membership Pro -> Configuration, set Export Data Format config option to **CSV** or **Excel 2003 (XLS)**. Then try again, export should work.
2. If you want to import subscription or want to export data to Excel format, please contact your hosting provider, ask them to enable Zip library for your hosting account, just send this link to your hosting provider support http://php.net/manual/en/zip.installation.php . After that, everything should work as expected