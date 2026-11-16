---
title: 'Useful Helper Methods'
published: true
---

There are some useful API methods which could be helpful in case you develop custom code to integrate with Membership Pro. If your code is not in Membership Pro context, you will first need to add the line of code below to load Membership Pro API (before you can use it's API methods)

```php
require_once JPATH_ADMINISTRATOR . '/components/com_osmembership/loader.php';
```

### Get IDs of all active subscription plans of a user

```php
// The code below returns ids of active subscription plans of the current logged in user
$planIds = OSMembershipHelperSubscription::getActivePlanIdsForUser();

// The code below returns ids of active subscription plans of the user with ID = 100
$planIds = OSMembershipHelperSubscription::getActivePlanIdsForUser(100);
```
### Get data from all custom fields for certain subscription records
```php
$data = OSMembershipHelperSubscription::getSubscriptionData(100);

echo $data['first_name'];
echo $data['last_name'];
echo $data['name_of_certain_field'];
```

### Get value for a none-core custom fields from a certain subscription

```php
$id         = 100; // ID of a subscription record
$fieldId    = 30; // ID of the none core field which you want to get value from
$fieldValue = OSMembershipHelperSubscription::getFieldValue($id, $fieldId);
```

### Get field value for a core field from first subscription of certain user

```php
$userId     = 100;
$fieldName  = 'first_name'; // Name of the core field to get value from
$planId     = 0; // Optional, can set to ID of the plan you want
$fieldValue = OSMembershipHelperSubscription::getFirstCoreFieldValue($userId, $fieldName, $planId);
```

### Get field value for a core field from last subscription of certain user

```php
$userId = 100;
$fieldName = 'first_name'; // Name of the core field to get value from
$planId = 0; // Optional, can set to ID of the plan you want
$fieldValue = OSMembershipHelperSubscription::getLastCoreFieldValue($userId, $fieldName, $planId);
```

### Get field value for a none core field from first subscription of certain user

```php
$userId = 100;
$fieldName = 'first_name'; // Name of the core field to get value from
$planId = 0; // Optional, can set to ID of the plan you want
$fieldValue = OSMembershipHelperSubscription::getFirstFieldValue($userId, $fieldName, $planId);
```

### Get field value for a none core field from last subscription of certain user

```php
$userId = 100;
$fieldName = 'first_name'; // Name of the core field to get value from
$planId = 0; // Optional, can set to ID of the plan you want
$fieldValue = OSMembershipHelperSubscription::getLastCoreFieldValue($userId, $fieldName, $planId);
```

### Create a subscription record for certain user
```php
$data = [
	'plan_id'    => $planId,
	'user_id'    => $userId,
	'first_name' => $firstName,
	'last_name'  => $lastName,
	'email'      => $user['email'],
    // You can add any other custom fields and other data here
];

$model = new OSMembershipModelApi();

try
{
	$model->store($data);
}
catch (Exception $e)
{
	// Ignore error for now
}
```
The system will renew subscription if there is an existing subscription for the user for the plan.
