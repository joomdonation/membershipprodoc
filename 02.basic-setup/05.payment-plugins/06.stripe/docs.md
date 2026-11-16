---
title: Stripe
visible: true
---

## Installation
When you purchase the payment plugin, you will receive a zip file called **os_osm_stripe_unzip_first.zip**. Unzip that file, you will get the file **os_osm_stripe.zip**. Go to Membership Pro -> Payment Plugins to install it as any other payment plugin. See [https://docs.joomdonation.com/membershippro/basic-setup/payment-plugins#install-new-payment-plugin](/basic-setup/payment-plugins#install-new-payment-plugin) for installation instructions if needed.

## Configuration
1. Click on the payment plugin to edit, enter payment plugin parameters, then publish it. You can follow instructions at https://stripe.com/docs/keys#api-keys to get API Keys from your Stripe account to enter into payment plugin parameters.

2. If you use recurring subscription plans, you will need to log in to your Stripe account, add a "Webhook URL" below (see https://stripe.com/docs/webhooks/setup#add-endpoint-dashboard for instructions to add webhook)

https://domain.com/index.php?option=com_osmembership&task=recurring_payment_confirm&payment_method=os_stripe

(Of course, need to replace https://domain.com/ with your website url)

Stripe will also asks you for the event for webhook, just select **invoice.payment_succeeded** in this case