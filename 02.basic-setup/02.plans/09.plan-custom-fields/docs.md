---
title: 'Plan Custom Fields'
published: true
media_order: 'custom_fields.png,edit_custom_fields.png'
---

Use plan custom fields to store extra information about subscription plans and display it on the plan details page and in the default plans list layout. You can define as many fields as you need in an XML file.

If you want to use this feature:

1. Look at **components/com_osmembership** folder, you will see a file called **fields.xml.txt**. That contains some pre-defined custom fields as an example. Rename that file to **fields.xml**
2. Now, when you add/edit a plan, you will see a new tab called Custom Fields to allow you to enter information for these custom fields.
3. You can use any custom field types supported by Joomla as documented here [https://docs.joomla.org/Standard_form_field_types](https://docs.joomla.org/Standard_form_field_types)
4. If you want to change change fields (add more fields, change title, remove fields), you can edit the file **components/com_osmembership/fields.xml** directly. Or go to Membership Pro -> Configuration, look at Custom Fields tab and edit directly from there
5. The data entered for these custom fields, as mentioned earlier, will be displayed on plan details page and plans list default layout page.