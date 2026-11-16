---
title: 'Develop Membership Pro plugin'
taxonomy:
    category:
        - docs
---

Membership Pro allows you to develop plugins to extend it's features. Infact, it has many plugins come with it by defualt which you can see in the foldder **plugins/osmembership** on your site.

Membership Pro supports the following events trigger which you can write plugin to handle to add more features to the extension:

## onEditSubscriptionPlan

This event is triggered on add/edit subscription plan. It usually used to allows you to display a form to allow admin control the necessary settings for your plan. A sample is the Joomla Groups plugin which allows admin to select which user groups subscriber of the plan will be added to when membership active and what user groups he will removed from when the subscription is expired

```php
public function onEditSubscriptionPlan($row)
{
	
}
```

- **$row**: The table object (instance of **OSMembershipTablePlan** class) stores information of plan being adding/editing. 

## onAfterSaveSubscriptionPlan

This event is triggered after the subscription plan is saved to database. It is usually used to save the settings data which you displayed on subscription add/edit screen so that you can used that settings data later

```php
public function onAfterSaveSubscriptionPlan($context, $row, $data, $isNew)
{
	
}
```
- **$row**: The table object (instance of **OSMembershipTablePlan** class) stores information of plan being saved.
- **$data**: Array contains all post data from add/edit plan form.
- **$isNew**: True if new plan is being added, false if existing plan is being updated.
## onAfterStoreSubscription

This event is triggered after the subscription record is saved to database (before payment is processed) 

```php
public function onAfterStoreSubscription($row)
{
	
}
```
- **$row**: The table object (instance of **OSMembershipTableSubscriber** class) stores information of the subscription record. From $row object, you can access to any fields from **osmembership_subscribers** table:

+ $row->id : ID of subscription record
+ $row->pkan_id: ID subscribed plan
+ $row->user_id : ID of user who subscribed for the event
+ $row->first_name: First Name of subscriber
+ $row->last_name: Last Name of subscriber
+ $row->email: Email of subscriber
+ $row->payment_method: The payment method subscriber uses to make payment
+ $row->transaction_id: Transaction ID of payment for the subscription.

## onMembershipActive
This event is triggered when a subscription record become active (when payment for the subscription complete or admin approve the subscription record manually from backend)

```php
public function onMembershipActive($row)
{
	
}
```

- **$row**: The table object (instance of **OSMembershipTableSubscriber** class) stores information of the subscription record. From $row object, you can access to any fields from **osmembership_subscribers** table. You can see explanation from **onAfterStoreSubscription**  above to see how to access to the necessary information from your plugin.

## onMembershipExpire

This event is triggered when a subscription record become expired (the current date is greater than the subscription end date of the record)
```php
public function onMembershipExpire($row)
{
	
}
```
- **$row**: The table object (instance of **OSMembershipTableSubscriber** class) stores information of the subscription record. From $row object, you can access to any fields from **osmembership_subscribers** table. You can see explanation from **onAfterStoreSubscription**  above to see how to access to the necessary information from your plugin.

## Get Subscription Information

```php
JLoader::register('OSMembershipModelApi', 
                  JPATH_ROOT . '/components/com_osmembership/model/api.php');

/* @var OSMembershipModelApi $model */
$model = MPFModel::getTempInstance('Api', 'OSMembershipModel');

$data = $model->getSubscriptionData($row->id);

echo $data['first_name']; // Return value of first_name
echo $data['last_name']; // Return value of last_name
echo $data['name_of_field']; // Return value of a custom field name_of_field.
```

## Create a new subscription
```php
require_once JPATH_ADMINISTRATOR . '/components/com_osmembership/loader.php';

$data = [
			'plan_id'    => $planId,
			'user_id'    => $userId,
			'first_name' => $firstName,
			'last_name'  => $lastName,
			'email'      => $email,
		];

JLoader::register('OSMembershipModelApi', 
                  JPATH_ROOT . '/components/com_osmembership/model/api.php');

/* @var OSMembershipModelApi $model */
$model = MPFModel::getTempInstance('Api', 'OSMembershipModel');
$row = $model->store($data); // $row contains data of stored subscription
