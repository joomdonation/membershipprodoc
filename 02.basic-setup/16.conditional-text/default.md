---
title: 'Conditional Text'
media_order: 'sms_reminder_plugin_settings.png,plug_membershiprosms_nexmo.zip,plug_membershiprosms_twilio.zip,sms_reminder_settings.png'
---

Starting with version 2.23.0, Membership Pro can show text in invoices and messages when a tag meets a condition. You can use any supported tag in the condition.

{mpShowText [FIRST_NAME]=Tuan}This text will be shown if data entered into first_name field is Tuan{/mpShowText}

{mpShowText [PUBLISHED]=0}This text will be shown if published = 0, mean subscription status is Pending{/mpShowText}

{mpShowText [PUBLISHED]=1}This text will be shown if published = 1, mean subscription status is Active{/mpShowText}

{mpShowText [PLAN_ID]=3}This text will be shown if the plan of the subscription has ID = 3{/mpShowText}

{mpShowText [ACT]=renew}This text will be shown if the subscription is a renewal subscription{/mpShowText}

{mpShowText [ACT]=upgrade}This text will be shown if the subscription is a upgrade subscription{/mpShowText}

{mpShowText [ACT]=subscribe}This text will be shown if the subscription is a new subscription{/mpShowText}

You can also put the text on multiple lines.

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

Use the same tags you use in email messages. Membership Pro substitutes the tag value before evaluating the condition. It displays the text only when the condition is met.

Supported operators: **>**, **<**, **=**, **~**, **@** :

**>**    :  Greater

**gt**   :  Greater

**<**    :  Smaller

**lt**    :  Smaller

**=**    :  Equal

**~**    :  Different

**@**   : Include