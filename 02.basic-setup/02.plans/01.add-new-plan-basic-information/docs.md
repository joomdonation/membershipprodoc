---
title: 'Basic Information'
media_order: plan-basic-information.png
---

Press New button in the toolbar to create new subscription plan. A form will be displayed to allow you to enter information of the plan.

### Basic Information

<table class="table table-bordered table-stripped table-considered">
<thead>
<tr><th width="15%">Property</th><th>Description</th></tr>
</thead>
<thead>
<tr>
<td><strong>Title</strong></td>
<td>Title of the subscription plan.</td>
</tr>
<tr>
<td><strong>Alias</strong></td>
<td>Alias will be used to generate the URL link to the plan detail page. If you unsure what to enter, simply leaves it empty and the system will generate the alias based on the title of the plan.</td>
</tr>
<tr>
<td><strong>Category</strong></td>
<td>Choose the category which the plan will be assigned to. As mentioned before, categories is optional in Membership Pro, so you don't have to choose a category if you don't have categories setup in the system.</td>
</tr>
<tr>
<td><strong>Price</strong></td>
<td>The price users have to pay to subscribe to this subscription plan. If you want the plan to be free, simply enter 0 into this field (or leave it empty).</td>
</tr>
<tr>
<td><strong>Subscription Length</strong></td>
<td>
How long the subscription will be active if subscribers sign up for this plan. It can be X days, X weeks, X months, X years.
</td>
</tr>
<tr>
<td><strong>Expired Date</strong></td>
<td>
<p>If you want all subscriptions of this plan to be expired on the same date (no matter when the subscribers sign up), you can choose that fixed expiration date into this field. For example, if you set this property to 31/12/2015:</p>
<ul>
<li>
If users sign up before 31/12/2015, their subscription will be expired on <strong>31/12/2015</strong>
</li>
<li>
If users sign up after 31/12/2015, for example on 06/05/2015, their subscription will be expired in <strong>31/12/2016</strong>
</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Lifetime Membership</strong></td>
<td>If you want all subscriptions of this plan to remain active for lifetime (never expired), you can set this field to Yes. By default, it should be No and subscribers will be expired after certain date (depends on Subscription length field)</td>
</tr>
<tr>
<td><strong>Thumbnail</strong></td>
<td>Thumbnail of the plan, it is optional. If you upload thumbnail for the plan, it will be displayed on plan list and plan detail page.</td>
</tr>
<tr>
<td><strong>Send First Reminder</strong></td>
<td>If you want the system to send the first remember email to subscribers of this plan <strong>X</strong> days before their subscription expired, enter <strong>X</strong> into this field. The reminder email message can be configured in Membership Pro => Emails && Messages section. If you enter 0 or leave empty, the first reminder email won't be sent.</td>
</tr>
<tr>
<td><strong>Send second Reminder</strong></td>
<td>
If you want the system to send the second remember email to subscribers of this plan <strong>Y</strong> days before their subscription expired, enter <strong>Y</strong> into this field.If you enter 0 or leave empty, the second reminder email won't be sent.
</td>
</tr>
<tr>
<td><strong>Send Third Reminder</strong></td>
<td>
If you want the system to send the third remember email to subscribers of this plan <strong>Z</strong> days before their subscription expired, enter <strong>Z</strong> into this field.If you enter 0 or leave empty, the third reminder email won't be sent.
</td>
</tr>
<tr>
<td><strong>Enable Renewal</strong></td>
<td>
<p>You should set this field to <strong>Yes</strong> so that users can renew their subscription before/when/after it is expired. There is only one case you should set it to No : The subscription plan is a free trial subscription plan, so you don't want subscribers to renew after it is expired</p>
</td>
</tr>
<tr>
<td><strong>Short description</strong></td>
<td>Short description of the subscription plan. It will be used to show on plans list page.</td>
</tr>
<tr>
<td><strong>Description</strong></td>
<td>Full description of the subscription plan. It will be displayed on plan details page. If you don't enter description, the short description will be used instead.</td>
</tr>
</thead>
</table>

![plan-basic-information](plan-basic-information.png "plan-basic-information")