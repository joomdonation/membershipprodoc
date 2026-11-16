---
title: 'What''s the difference between PayPal and PayPal Pro payment plugin'
visible: true
---

You might think that PayPal Pro payment plugin is the pro version (mean has more features) of the standard PayPal payment plugin comes with Membership Pro by default. However, it is not correct, PayPal and PayPal Pro is different types of payment plugins:

1. os_paypal (which comes with Membership Pro by default) implements PayPal Website Payment Standard method provides by PayPal. With this payment method, users will be redirected to PayPal website for processing payment, the whole payment process is handled by PayPal, so it  can be considered as a safe payment method
2. os_paypal_pro (MP PayPal Pro) payment plugin allow customers to enter credit card information directly on your site for processing payment. They won't be redirected to PayPal, so it is simpler for customers to make a payment. However, please note that:
- PayPal Pro is only available in some countries like US, UK, Canada, Australia, so you can only use PayPal Pro if you are from one of the above countries
- PayPal charges you monthly fee (30$ / month if I remember correctly) if you want to use PayPal Pro
- With PayPal Pro, customers will enter credit card directly on your site for processing payment, so you your site should have SSL certificate so that credit card information will be encrypted before passing over interner, safe for your customers
