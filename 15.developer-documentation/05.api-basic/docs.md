---
title: 'API Basic'
---

Membership Pro has a very basic API methods to allow external applications (could be mobile app) to call to add, update, get details information of a subscription record.

## Enable API
If you want to use APIs, you will first need to enable it. Go to Membership Pro -> Configuration, look at API Settings tab, set Enable API parameter to Yes. You should also set a secret key into **Api Key** config option for secure purpose (only applications know that key can called the API methods)

## Supported Methods

### Add New Subscription

**Request URL**: https://domain.com/index.php?option=com_osmembership&task=api.add&api_key=[API_KEY]

- https://domain.com needs to be replaced with your site domain
- [API_KEY] needs to be replaced with the API key you set in the Api Key config option

**Request Data**: Passed in key value-pair. Important parameter including:

- plan_id : ID of the plan which you want to add the subscription record to
- user_id : ID of existing user in case the subscription is created for an existing user
- username, password (in case you want the system to create a new Joomla account for the subscription and assign the subscription record to that account)
- email: Email of subscription
- first_name, last_name, organization.... and any of the custom fields
- published: 0: Pending, 1: Active, 2: Expired
- from_date, to_date (start date and end date of the subscription, if it's not passed, it will be calculated automatically by the system)
- amount, discount_amount, tax_amount, payment_processing_fee, gross_amount, tax_rate : The amounts of the subscription

### Update An Existing Subscription

**Request URL**: https://domain.com/index.php?option=com_osmembership&task=api.update&api_key=[API_KEY]

- https://domain.com needs to be replaced with your site domain
- [API_KEY] needs to be replaced with the API key you set in the Api Key config option

**Request Data**: Same with **Add New Subscription**. The only difference is is that you need to pass extra variable:

- id : Contains ID of the subscription record which you want to update

### Get Subscription Details

**Request URL**: https://domain.com/index.php?option=com_osmembership&task=api.get&api_key=[API_KEY]

- https://domain.com needs to be replaced with your site domain
- [API_KEY] needs to be replaced with the API key you set in the Api Key config option

**Request Data**:

- id : Contains ID of the subscription record which you want to get details information of the subscription

**Response**: Json data contains all information of the subscription

### Get Active Plan IDs Of A User
**Request URL**: https://domain.com/index.php?option=com_osmembership&task=api.get_active_plan_ids&api_key=[API_KEY]

- https://domain.com needs to be replaced with your site domain
- [API_KEY] needs to be replaced with the API key you set in the Api Key config option

**Request Data**:

- user_id: ID of Joomla user account which you want to get active plan ids.
- username: Username of the user account which you want to get active plan ids.

Please note that you should only pass user_id or username. If both are passed (which should not), user_id will take higher priority.

### Get Active Subscriptions Of A User
**Request URL**: https://domain.com/index.php?option=com_osmembership&task=api.get_user_active_subscriptions&api_key=[API_KEY]

- https://domain.com needs to be replaced with your site domain
- [API_KEY] needs to be replaced with the API key you set in the Api Key config option

**Request Data**:

- user_id: ID of Joomla user account which you want to get active subscriptions
- username: Username of the user account which you want to get active subscriptions

Please note that you should only pass user_id or username. If both are passed (which should not), user_id will take higher priority.

**Request Data**:

- user_id: ID of Joomla user account which you want to get active subscriptions
- username: Username of the user account which you want to get active subscriptions

Please note that you should only pass user_id or username. If both are passed (which should not), user_id will take higher priority.

**Response**: JSON data contains all the active subscriptions of the requested user

### Add your own API Methods
As you can see, the API here is very basic and limited. So if you want to connect to Membership Pro from external apps, it's very likely you would have to add your own API methods. To do that, you should implement these new api methods using override for api controller and api model

```php
class OSMembershipControllerOverrideApi extends OSMembershipControllerApi
{
    public function your_api_method()
    {
        
    }
}

```php
class OSMembershipModelOverrideApi extends OSMembershipModelApi
{
    public function yourApiMethod()
    {
        
    }
}

See [https://membershipprodoc.joomservices.com/developer-documentation/code-customization-override#override-method-in-a-controller-class](https://membershipprodoc.joomservices.com/developer-documentation/code-customization-override#override-method-in-a-controller-class) and [https://membershipprodoc.joomservices.com/developer-documentation/code-customization-override#override-method-in-a-model-class](https://membershipprodoc.joomservices.com/developer-documentation/code-customization-override#override-method-in-a-model-class) to understand how to create override for controller and model





