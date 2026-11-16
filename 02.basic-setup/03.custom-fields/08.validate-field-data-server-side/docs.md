---
title: 'Validate Field Data - Server Side'
---

Beside [client side validation](http://membershipprodoc.joomservices.com/basic-setup/custom-fields/validate-field-data-client-side), from version 2.14.0 of Membership Pro, you can also validate custom fields data using server side validation (using PHP code). You can use both built-in validators and implement custom validators yourself. To use server side validation, you can edit the custom field, enter the rules you want to use into **Server Validation Rules**
## Built-in validators

We use **Valitron Validation** library - the most awesome validation engine ever created for PHP for validating custom fields data in Events Booking. See https://github.com/vlucas/valitron#built-in-validation-rules for list of supported validators you can use. 

The syntax which you can enter into **Server Validation Rules** is **rule1|rule2:param1,param2**. Basically:
- You can add many rules you want to validate data for the filed. Each rule must be separated by | character
- You can add parameters to rule by adding : character after rule name, list of parameters separated by comma

Examples:
* **min:10**: will force the field to be a a number greater than or equal 10
* **max:10**: will force the field to be a a number smaller than or equal 10
* **length:10**: will force the field to be a string with exactly 10 characters
* **lengthMin:10**: will force the field to be a string has at least 10 characters
* **lengthMax:10**: will force the field to be a string has maximum 10 characters
* **lengthBetween:5,15**: will force the field to be a string with minimum 5 characters and maximum 15 characters
* **age:18,40**: will force the field to be a date time with age between 18 and 40 (usually use for birthday field)

## Build custom validators

Sometime, you will need to build custom validator to validate the custom field data using the logic you want. To do that:

1. Create a field **validator.php** and upload it to **components/com_osmembership/helper** folder on your site
2. Edit that file, add the code like below to the file:

```php
<?php
/**
 * @package            Joomla
 * @subpackage         Membership Pro
 * @author             Tuan Pham Ngoc
 * @copyright          Copyright (C) 2010 - 2018 Ossolution Team
 * @license            GNU/GPL, see LICENSE.php
 */

defined('_JEXEC') or die;

Valitron\Validator::addRule('my_custom_rule', function($field, $value, array $params, array $fields) {
    if (strlen($value) != 9)
	{
			return false;
	}
	
    return true;
}, 'The field must has exactly 9 characters');

Valitron\Validator::addRule('my_custom_rule2', function($field, $value, array $params, array $fields) {
    if ($value != 9)
	{
			return false;
	}
	
    return true;
}, 'The field must has value = 9');


```
Each rule contains a block of code like that with the following parameters:
- $field: Name of the field which the rule is applied
- $value: Value of that field
- $params: Array of parameters which users passed to the rule when setup the server validation rules
- $fields: Array contains data of other fields in the form

See [https://github.com/vlucas/valitron#adding-custom-validation-rules](https://github.com/vlucas/valitron#adding-custom-validation-rules) for more detailed instructions from the original library

4. To use this custom rule, you just need to edit the field and enter **my_custom_rule** into **Server Validation Rules** setting of the field. Now, when the form is submitted, the system will use the code in your  my_custom_rule to validate data of that field.

## Custom error message
When data for a field is not valid, the system will show an error message to registrants so that they will know about the error and correct it. Yoi should setup a clear error message for the field in **Validation error message** setting like [FIELD_NAME] must be a string with maximum 20 characters..., [FIELD_NAME] must be a integer number between 10 and 20....