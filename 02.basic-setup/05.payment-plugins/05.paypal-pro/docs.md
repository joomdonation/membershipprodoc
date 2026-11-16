---
title: 'PayPal Pro'
visible: true
---

## Installation
When you purchase the payment plugin, you will receive a zip file called **os_osm_paypal_pro_unzip_first.zip**. Unzip that file, you will get the file **os_osm_paypal_pro.zip**. Go to Membership Pro -> Payment Plugins to install it as any other payment plugin. See [https://docs.joomdonation.com/membershippro/basic-setup/payment-plugins#install-new-payment-plugin](/basic-setup/payment-plugins#install-new-payment-plugin) for installation instructions if needed.

## Configuration
1. Click on the payment plugin to edit, enter payment plugin parameters, then publish it. Follow instructions at https://developer.paypal.com/docs/archive/nvp-soap-api/apiCredentials/#api-signatures to get API Username, API Password, API Signature of your PayPal account to enter into payment plugin parameters.
2. If you use recurring subscription plans, you will need to set IPN URL of your Paypal account to https://yoursite.com/index.php?option=com_osmembership&task=payment_confirm&payment_method=os_paypal_pro

(Please replace https://yoursite.com/ with the actual domain of your website)

Follow the instructions at https://developer.paypal.com/docs/ipn/integration-guide/IPNSetup/#setting-up-ipn-notifications-on-paypal to setup IPN URL.
