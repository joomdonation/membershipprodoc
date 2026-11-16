---
title: 'Develop payment plugin'
taxonomy:
    category:
        - docs
---

Membership Pro supports multiple payment gateways. Each payment gateway is implemented as a payment plugin in extension. If you want to use a payment gateway which is not supported by the extension, you will need to develop a payment plugin to work with that payment gateway.

Payment plugins can be devided into two types

## Redirect base payment plugin
With this type of payment plugin, subscribers will be redirected to payment gateway for processing payment. If you are developing this type of payment plugin, look at [https://github.com/joomdonation/os_osm_redirect](https://github.com/joomdonation/os_osm_redirect) for sample plugin structure and detailed instruction

## Credit card base payment plugin
With this type of payment plugin, subscribers will enter credit card information directly on your site to process payment. They won't be redirected to payment gateway. If you are developing this type of payment plugin, look at [https://github.com/joomdonation/os_osm_creditcard](https://github.com/joomdonation/os_osm_creditcard) for sample plugin structure and detailed instruction