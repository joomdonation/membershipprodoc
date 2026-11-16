---
title: 'Conditional Text'
media_order: 'sms_reminder_plugin_settings.png,plug_membershiprosms_nexmo.zip,plug_membershiprosms_twilio.zip,sms_reminder_settings.png'
---

From version 2.23.0, Membership Pro support conditional text in invoice and messages. That mean it allows you to show text depend on certain value. You can use any any tags in the condition. For example:

{mpShowText [FIRST_NAME]=Tuan}This text will be shown if data entered into first_name field is Tuan{/mpShowText}

{mpShowText [PUBLISHED]=0}This text will be shown if published = 0, mean subscription status is Pending{/mpShowText}

{mpShowText [PUBLISHED]=1}This text will be shown if published = 1, mean subscription status is Active{/mpShowText}

{mpShowText [PLAN_ID]=3}This text will be shown if the plan of the subscription has ID = 3{/mpShowText}

{mpShowText [ACT]=renew}This text will be shown if the subscription is a renewal subscription{/mpShowText}

{mpShowText [ACT]=upgrade}This text will be shown if the subscription is a upgrade subscription{/mpShowText}

{mpShowText [ACT]=subscribe}This text will be shown if the subscription is a new subscription{/mpShowText}

Of if you want to have text on multi-lines:

{mpShowText [FIRST_NAME]=Tuan}
This text will be shown if data entered into first_name field is Tuan
{/mpShowText}

{mpShowText [PUBLISHED]=0}
This text will be shown if published = 0, mean subscription status is Pending
{/mpShowText}

{mpShowText [PUBLISHED]=1}
This text will be shown if published = 1, mean subscription status is Active
{/mpShowText}

{mpShowText [PLAN_ID]=3}
This text will be shown if the plan of the subscription has ID = 3
{/mpShowText}

{mpShowText [ACT]=renew}
This text will be shown if the subscription is a renewal subscription
{/mpShowText}

{mpShowText [ACT]=upgrade}
This text will be shown if the subscription is a upgrade subscription
{/mpShowText}

{mpShowText [ACT]=subscribe}
This text will be shown if the subscription is a new subscription
{/mpShowText}

You can use any tags in the condition (same with how you use tags in emails message). The tag will be replaced with it's value before comparing with the value in the condition. If the condition matches, the text will be displayed. If the condition false, text won't be displayed.

Supported operators: **>**, **<**, **=**, **~**, **@** :

**>**    :  Greater

**gt**   :  Greater

**<**    :  Smaller

**lt**    :  Smaller

**=**    :  Equal

**~**    :  Different

**@**   : Include