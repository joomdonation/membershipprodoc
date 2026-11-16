---
title: 'Subscription status is Pending after paid'
visible: true
---

Sometime, during testing peior, you see that after making payment at PayPal, the status of subscription record is Pending instead of Active as expected. Don't worry, there could be many reasons causing this issue and we will figure it out:

1. First, please make sure your site is public accessible, so:

- If your site is on local computer (localhost), you need to upload it to a liver server (which people can access to from internet)
- Joomla allows you to turn of your site offline mode. If you use offline mode, PayPal won't work, so you need to make your site Online (Go to System - Global Configuration, set Offline parameter to No)
- If frontend of your site is protected by username and password (htaccess/server protection) - usually happens during development while you don't want users to see the site on development mode, please turn off this protection

2. Make sure PayPal IPN is enabled in your PayPal account (the one which receives payment)

By default, PayPal IPN is turned on in your PayPal account. Each time a payment processed, PayPal will send an IPN message to Membership Pro to notify this payment. If for some reasons, PayPal IPN is turned off on your PayPal account, Membership Pro won't work and you will need to turn it on.

- Follow the instructions at https://www.jotform.com/help/276-How-to-Enable-IPN-for-Paypal to enable PayPal IPN in the PayPal account which receive payment on your site. PayPal will ask for IPN URL, simply enter URL of your site into that parameter
- Go to Membership Pro -> Payment Plugins, click on os_paypal payment plugin to edit, set Log IPN Messages parameter to Yes. 

After that, try to subscribe again, make payment. If it still doesn't work, submit a support ticket sending us super admin account of your site so that we can check and correct it for you