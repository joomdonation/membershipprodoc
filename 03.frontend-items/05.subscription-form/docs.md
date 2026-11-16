---
title: 'Subscription Form'
media_order: onetime_subscription_form.png
---

The **Subscription Form** page lets users enter their details and complete payment to sign up for a specific plan. They can open the form by clicking Sign Up in the plans list or on the plan details page, or by opening a menu item.

If you want users to access this page from menu item, create a menu item to link to **Subscription Form** menu option of **Membership Pro**. Beside common Joomla menu items parameters, these menu options support the following parameters specific to Membership Pro:

- **Select Plan**: Choose the plan you want users to sign up for when they click on this menu item. You need to choose a valid/published plan for this parameter.
![Subscription Form](onetime_subscription_form.png)

## Customize Subscription Form
The subscription form in Membership Pro is fully customizable.

1. **Registration Integration**: If you want to allow your subscribers to enter username and password to register for an account on your website when they sign up for your subscription plan, you can go to **Membership Pro -> Configuration**, find the config option **Registration Integration**, set it to **Yes**.
2. **Show forgot username/password options**: If set to **Yes**, there will be links displayed on subscription form to allow existing users to reset username/password for their accounts in case they forgot.
3. **Show Login Box**: If you want to users who have existing account on your site to be able to login before continue their subscription process (so that the subscription record will be assigned to his account), you can go to **Membership Pro -> Configuration**, find the config option **Show login box on subscription page**, set it to **Yes** (this should be set to Yes if you allow users registration)
4. **Show/Hide, Require/Not require form fields**: If you want to make a field on subscription form to be showed/hided or required/not required, please go to Membership Pro -> Custom Fields, publish/unpublish or mark it as required/not required.
5. **Change title of the custom fields**: Sometime, you might want to change title of the custom field (for example, change it from Organization to Company). In this case, just go to **Membership Pro -> Custom Fields**, click on the custom field you want to change and edit it, change the title to meet your need.
6. **Add more custom fields to subscription form**: When you first install Membership Pro, the extension auto generate a list of pre-defined custom fields which we call Core Fields. They are **First Name, Last name**......If you want to collect more information of subscribers, you can go to **Membership Pro -> Custom Fields** and create any extra custom fields you want. With custom fee field feature, you can even config it so that the subscription price will be changed based on what options users choose on registration form.