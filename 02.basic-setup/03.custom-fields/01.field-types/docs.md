---
title: 'Supported Field Types'
taxonomy:
    category:
        - docs
---

**Membership Pro** support the following custom field types:
1. **Text**  
2. **URL**
3. **Email**
4. **Number**
5. **Tel**
6. **Range**
7. **Password**
8. **Textarea**
9. **List**: This field type will generate a dropdown (single or multiple select). To make it become multiple select, please set **Multiple** property to **Yes**
10. **Chekboxes**
11. **Radio**
12. **Date**: Display a calendar allows selecting a date
13. **Heading**: Display **title of the field** as a header on subscription form
14. **Message**: Display a text message on subscription form. The message you want to display need to be entered into **Description** of the custom field
15. **File** : Allow subscribers to upload file while subscribing for a subscription plan. The file types which subscribers can upload is controlled in **Allowed File Types** config option.
16. **Countries**: Display list of published countries in a single dropdown select
17. **State**: Display list of states of a the selected country. When subscribers select a new country in the country dropdown, the list of states in this field will also be updated automatically
18. **Hidden**: Add a hidden input to the form. Enter the value you want to use for this field in **Default Values** setting.
19. **Signature**: Allow subscribers to sign electronically by drawing their signature directly on the form using a mouse, touch screen, or stylus.
20. **SQL**: Display a select dropdown. The options in this select dropdown will be returned from a SQL command. Please note that:
* The SQL command needs to be entered into **Default Values** property of the field
* The SQL command needs to return two columns : **value** and **text**
* Sample SQL command which you can use: **SELECT name AS value, name AS text FROM #__osmembership_countries WHERE published = 1 ORDER BY name** 

>>>>> Right now, we only allow one country field and one state field on the form so that it can work together (when country is changed, the states list will be changed / update, too).



>>>>> In case you don't have country field in the form but still have state field, the state field will get list of states from Default Country which you select in Membership Pro
