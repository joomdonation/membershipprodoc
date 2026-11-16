---
title: 'PayPal Pro'
visible: true
---

## Installation
After purchasing the payment plugin, extract **os_osm_paypal_pro_unzip_first.zip** to find **os_osm_paypal_pro.zip**. Go to Membership Pro -> Payment Plugins to install it. For detailed steps, see [https://docs.joomdonation.com/membershippro/basic-setup/payment-plugins#install-new-payment-plugin](/basic-setup/payment-plugins#install-new-payment-plugin).

## Configuration
1. Open the payment plugin, fill in its parameters, and publish it. Follow the instructions at https://developer.paypal.com/docs/archive/nvp-soap-api/apiCredentials/#api-signatures to find the API Username, API Password, and API Signature for your PayPal account. Enter these values in the plugin settings.
2. If you use recurring subscription plans, you will need to set IPN URL of your Paypal account to https://yoursite.com/index.php?option=com_osmembership&task=payment_confirm&payment_method=os_paypal_pro

(Please replace https://yoursite.com/ with the actual domain of your website)

Follow the instructions at https://developer.paypal.com/docs/ipn/integration-guide/IPNSetup/#setting-up-ipn-notifications-on-paypal to setup IPN URL.
