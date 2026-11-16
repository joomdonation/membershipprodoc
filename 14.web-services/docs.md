---
title: 'Web Services'
taxonomy:
    category:
        - docs
published: true
---

# Membership Pro Web Services

Membership Pro integrates with the Joomla Web Services (API application). Resources are exposed in the [JSON:API](https://jsonapi.org) format under `/api/index.php/v1/membershippro/...`.

## Requirements

1. Joomla 4.x or later.
2. Enable the plugin **Web Services - Membership Pro** (Extensions > Plugins, folder `webservices`).
3. Enable the Joomla **API Authentication - Token** plugin and **User - Joomla API Token** plugin, then generate an API token for a Super User (or a user with `core.manage`, `core.create`, `core.edit` and `core.delete` permissions on Membership Pro) from the user's *Joomla API Token* tab.

## Authentication and headers

Send the token in every request:

```
X-Joomla-Token: YOUR_API_TOKEN
Accept: application/vnd.api+json
Content-Type: application/json
```

Alternatively, send the token as a ****** in the standard Authorization header.

Base URL used in the examples below: `https://example.com/api/index.php`

## Permissions

| Operation | Required permission on com_osmembership |
|-----------|------------------------------------------|
| List / read | `core.manage` |
| Create | `core.create` |
| Update / publish / unpublish / cancel / refund | `core.edit` |
| Delete | `core.delete` |
| Subscriber endpoints | `core.manage` |

A missing permission returns HTTP `403`; a non-existing record returns `404`; invalid data returns `400`.

## Common request parameters (list endpoints)

| Parameter | Description | Example |
|-----------|-------------|---------|
| `page[limit]` | Number of items per page (default 20, max 100) | `page[limit]=50` |
| `page[offset]` | Number of items to skip | `page[offset]=50` |
| `filter[search]` | Search keyword | `filter[search]=gold` |
| `filter[published]` | Filter by published state | `filter[published]=1` |
| `filter[access]` | Filter by access level ID | `filter[access]=1` |
| `filter[language]` | Filter by language | `filter[language]=en-GB` |
| `list[ordering]` | Column to order by | `list[ordering]=title` |
| `list[direction]` | `asc` or `desc` | `list[direction]=desc` |
| `fields[type]` | Comma separated list of attributes to return, `type` is the resource type (`categories`, `plans`, `subscriptions`...) | `fields[plans]=title,price` |

Pagination info is returned in the `links` (`self`, `next`, `previous`, `first`, `last`) and `meta` (`total-pages`) sections of the response.

## Response format

Single item:

```json
{
  "links": {"self": "https://example.com/api/index.php/v1/membershippro/categories/1"},
  "data": {
    "type": "categories",
    "id": "1",
    "attributes": {"id": 1, "title": "Gold"}
  }
}
```

List:

```json
{
  "links": {"self": "...", "next": "...", "last": "..."},
  "data": [
    {"type": "categories", "id": "1", "attributes": {"id": 1, "title": "Gold"}}
  ],
  "meta": {"total-pages": 3}
}
```

Errors:

```json
{"errors": [{"title": "Item does not exist", "code": 404}]}
```

## Endpoints overview

| Method | URL | Description |
|--------|-----|-------------|
| GET | `/v1/membershippro/categories` | List categories |
| GET | `/v1/membershippro/categories/:id` | Get a category |
| POST | `/v1/membershippro/categories` | Create a category |
| PATCH | `/v1/membershippro/categories/:id` | Update a category |
| DELETE | `/v1/membershippro/categories/:id` | Delete a category |
| GET | `/v1/membershippro/plans` | List plans |
| GET | `/v1/membershippro/plans/:id` | Get a plan |
| POST | `/v1/membershippro/plans` | Create a plan |
| PATCH | `/v1/membershippro/plans/:id` | Update a plan |
| DELETE | `/v1/membershippro/plans/:id` | Delete a plan |
| GET | `/v1/membershippro/subscriptions` | List subscriptions |
| GET | `/v1/membershippro/subscriptions/:id` | Get a subscription |
| POST | `/v1/membershippro/subscriptions` | Create a subscription |
| PATCH | `/v1/membershippro/subscriptions/:id` | Update a subscription |
| DELETE | `/v1/membershippro/subscriptions/:id` | Delete a subscription |
| PATCH | `/v1/membershippro/subscriptions/:id/publish` | Mark subscription as active |
| PATCH | `/v1/membershippro/subscriptions/:id/unpublish` | Mark subscription as unpublished (pending) |
| PATCH | `/v1/membershippro/subscriptions/:id/cancel_subscription` | Cancel a recurring subscription at the payment gateway |
| PATCH | `/v1/membershippro/subscriptions/:id/refund` | Refund a subscription |
| GET | `/v1/membershippro/subscriber/:user_id/activePlanIds` | IDs of plans a user is actively subscribed to |
| GET | `/v1/membershippro/subscriber/:user_id/subscriptions` | Paginated subscriptions of a user |
| GET | `/v1/membershippro/subscriber/:user_id/mysubscriptions` | Plans a user subscribed to, with subscription info |
| GET | `/v1/membershippro/subscriber/:user_id/activesubscriptions` | Active subscriptions of a user |

For POST and PATCH requests the data is sent as a JSON object of field names and values. On PATCH, fields not sent keep their current value. After a successful POST the response has status `201` and contains the created record; DELETE returns `204` with no body.

---

## Categories

Resource type: `categories`. Extra list filters: `filter[search]`, `filter[published]`, `filter[access]`, `filter[language]`.

### List categories

```
GET /v1/membershippro/categories?filter[published]=1&page[limit]=10
```

Attributes returned in list: `id`, `parent_id`, `title`, `alias`, `ordering`, `access`, `published`, `language`, `level`, `number_plans`.

```json
{
  "links": {"self": "https://example.com/api/index.php/v1/membershippro/categories?filter[published]=1&page[limit]=10"},
  "data": [
    {
      "type": "categories",
      "id": "1",
      "attributes": {
        "id": 1, "parent_id": 0, "title": "Gold", "alias": "gold", "ordering": 1,
        "access": 1, "published": 1, "language": "*", "level": 1, "number_plans": 3
      }
    }
  ],
  "meta": {"total-pages": 1}
}
```

### Get a category

```
GET /v1/membershippro/categories/1
```

Attributes: `id`, `parent_id`, `title`, `alias`, `description`, `ordering`, `access`, `published`, `language`, `level`.

### Create a category

```
POST /v1/membershippro/categories
```

```json
{
  "title": "Silver",
  "alias": "silver",
  "parent_id": 0,
  "description": "<p>Silver plans</p>",
  "access": 1,
  "published": 1,
  "language": "*"
}
```

Returns `201` with the created category.

### Update a category

```
PATCH /v1/membershippro/categories/2
```

```json
{"title": "Silver Plus", "published": 0}
```

### Delete a category

```
DELETE /v1/membershippro/categories/2
```

Returns `204`.

---

## Plans

Resource type: `plans`. List filters: `filter[search]`, `filter[published]`, `filter[access]`, `filter[language]`, `filter[category_id]`.

### List plans

```
GET /v1/membershippro/plans?filter[category_id]=1
```

Attributes in list: `id`, `category_id`, `title`, `alias`, `price`, `currency`, `subscription_length`, `subscription_length_unit`, `lifetime_membership`, `recurring_subscription`, `access`, `ordering`, `published`, `category_title`.

```json
{
  "data": [
    {
      "type": "plans",
      "id": "5",
      "attributes": {
        "id": 5, "category_id": 1, "title": "Gold Monthly", "alias": "gold-monthly",
        "price": "10.00", "currency": "USD", "subscription_length": 1,
        "subscription_length_unit": "M", "lifetime_membership": 0,
        "recurring_subscription": 0, "access": 1, "ordering": 1, "published": 1,
        "category_title": "Gold"
      }
    }
  ],
  "meta": {"total-pages": 1}
}
```

### Get a plan

```
GET /v1/membershippro/plans/5
```

Attributes: `id`, `category_id`, `title`, `alias`, `short_description`, `description`, `price`, `setup_fee`, `currency`, `currency_symbol`, `subscription_length`, `subscription_length_unit` (`D`, `W`, `M`, `Y`), `lifetime_membership`, `expired_date`, `recurring_subscription`, `trial_amount`, `trial_duration`, `trial_duration_unit`, `number_payments`, `tax_rate`, `access`, `ordering`, `published`, `publish_up`, `publish_down`, `enable_renewal`, `require_coupon`, `thumb`, `language`, `created_by`, plus the nested arrays `renew_options`, `renewal_discounts` and `upgrade_options`.

```json
{
  "data": {
    "type": "plans",
    "id": "5",
    "attributes": {
      "id": 5, "category_id": 1, "title": "Gold Monthly", "price": "10.00",
      "subscription_length": 1, "subscription_length_unit": "M",
      "renew_options": [
        {"id": 1, "renew_option_length": 1, "renew_option_length_unit": "M", "price": "8.00"}
      ],
      "renewal_discounts": [
        {"id": 1, "number_days": 7, "discount_amount": "10.00", "discount_type": 0}
      ],
      "upgrade_options": [
        {"id": 1, "to_plan_id": 6, "price": "5.00", "upgrade_prorated": 0, "published": 1}
      ]
    }
  }
}
```

### Create a plan

```
POST /v1/membershippro/plans
```

```json
{
  "category_id": 1,
  "title": "Gold Monthly",
  "alias": "gold-monthly",
  "short_description": "Monthly gold membership",
  "price": 10,
  "subscription_length": 1,
  "subscription_length_unit": "M",
  "enable_renewal": 1,
  "access": 1,
  "published": 1,
  "renew_options": [
    {"renew_option_length": 1, "renew_option_length_unit": "M", "price": 8}
  ],
  "renewal_discounts": [
    {"number_days": 7, "discount_amount": 10, "discount_type": 0}
  ],
  "upgrade_options": [
    {"to_plan_id": 6, "price": 5, "upgrade_prorated": 0, "published": 1}
  ]
}
```

### Update a plan

```
PATCH /v1/membershippro/plans/5
```

```json
{"price": 12, "title": "Gold Monthly (new)"}
```

If `renew_options`, `renewal_discounts` or `upgrade_options` are not included in the request, the existing ones are kept. When included, they replace the existing ones.

### Delete a plan

```
DELETE /v1/membershippro/plans/5
```

---

## Subscriptions

Resource type: `subscriptions`.

List filters:

| Filter | Description |
|--------|-------------|
| `filter[search]` | Search by name, email, transaction ID... |
| `filter[plan_id]` | Plan ID |
| `filter[category_id]` | Plan category ID |
| `filter[published]` | Status: `0` pending, `1` active, `2` expired, `3` cancelled. All statuses are returned by default |
| `filter[subscription_type]` | Subscription type (`1` new, `2` renewal, `3` upgrade) |
| `filter[from_date]`, `filter[to_date]` | Created date range |

### List subscriptions

```
GET /v1/membershippro/subscriptions?filter[plan_id]=5&filter[published]=1&list[ordering]=id&list[direction]=desc
```

Attributes in list: `id`, `plan_id`, `plan_title`, `user_id`, `username`, `first_name`, `last_name`, `email`, `created_date`, `from_date`, `to_date`, `published`, `act`, `gross_amount`, `payment_method`, `transaction_id`, `membership_id`, `custom_fields`.

```json
{
  "data": [
    {
      "type": "subscriptions",
      "id": "100",
      "attributes": {
        "id": 100, "plan_id": 5, "plan_title": "Gold Monthly", "user_id": 42,
        "username": "john", "first_name": "John", "last_name": "Doe",
        "email": "john@example.com", "created_date": "2026-01-01 10:00:00",
        "from_date": "2026-01-01 10:00:00", "to_date": "2026-02-01 10:00:00",
        "published": 1, "act": "subscribe", "gross_amount": "10.00",
        "payment_method": "os_paypal", "transaction_id": "ABC123", "membership_id": 1001,
        "custom_fields": {"company_size": "10-50"}
      }
    }
  ],
  "meta": {"total-pages": 1}
}
```

### Get a subscription

```
GET /v1/membershippro/subscriptions/100
```

Attributes: `id`, `plan_id`, `user_id`, `coupon_id`, `first_name`, `last_name`, `organization`, `address`, `address2`, `city`, `state`, `zip`, `country`, `phone`, `fax`, `email`, `comment`, `created_date`, `payment_date`, `from_date`, `to_date`, `published`, `act`, `setup_fee`, `tax_rate`, `amount`, `tax_amount`, `discount_amount`, `gross_amount`, `payment_processing_fee`, `payment_method`, `transaction_id`, `subscription_id`, `payment_currency`, `membership_id`, `invoice_number`, `language`, `recurring_subscription_cancelled`, `refunded`, `group_admin_id`, `custom_fields`.

`custom_fields` is an object of non-core custom field values keyed by field name.

### Create a subscription

```
POST /v1/membershippro/subscriptions
```

`plan_id` is required. Either pass an existing `user_id`, or pass `username`, `password` and `email` to create a Joomla user (all default to empty/0 if omitted).

```json
{
  "plan_id": 5,
  "user_id": 42,
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "from_date": "2026-01-01 10:00:00",
  "to_date": "2026-02-01 10:00:00",
  "amount": 10,
  "gross_amount": 10,
  "payment_method": "os_offline",
  "transaction_id": "MANUAL-1",
  "published": 1
}
```

Returns `201` with the created subscription. Missing `plan_id` returns `400`.

### Update a subscription

```
PATCH /v1/membershippro/subscriptions/100
```

```json
{"to_date": "2026-03-01 10:00:00", "comment": "Extended by admin"}
```

### Delete a subscription

```
DELETE /v1/membershippro/subscriptions/100
```

### Subscription actions

All actions use the `PATCH` method, need no request body, and return the updated subscription.

| Action | URL | Notes |
|--------|-----|-------|
| Publish | `PATCH /v1/membershippro/subscriptions/100/publish` | Sets status to active and triggers the same activation process as the backend |
| Unpublish | `PATCH /v1/membershippro/subscriptions/100/unpublish` | Sets status to pending |
| Cancel recurring | `PATCH /v1/membershippro/subscriptions/100/cancel_subscription` | Only for recurring subscriptions that can be cancelled; otherwise `400` |
| Refund | `PATCH /v1/membershippro/subscriptions/100/refund` | Only when the payment method supports refund and the subscription is refundable; otherwise `400` |

---

## Subscriber endpoints

These read-only endpoints return subscription information of a Joomla user. `:user_id` must be the ID of an existing Joomla user, otherwise `404` is returned.

### Active plan IDs

```
GET /v1/membershippro/subscriber/42/activePlanIds
```

```json
{
  "data": {
    "type": "subscribers",
    "id": "42",
    "attributes": {"id": 42, "active_plan_ids": [5, 7]}
  }
}
```

### Subscriptions of a user

```
GET /v1/membershippro/subscriber/42/subscriptions?page[limit]=20
```

Returns a paginated list of `subscriptions` resources (same attributes as the subscription list). Supports `page[...]` and `list[...]` parameters.

### My subscriptions

```
GET /v1/membershippro/subscriber/42/mysubscriptions
```

Returns one `mysubscriptions` resource per plan the user subscribed to. Attributes: `id`, `category_id`, `title`, `alias`, `subscription_id`, `subscription_status`, `subscription_from_date`, `subscription_to_date`, `recurring_cancelled`, `subscriptions`.

### Active subscriptions

```
GET /v1/membershippro/subscriber/42/activesubscriptions
```

Returns the user's currently active subscriptions as `subscriptions` resources.

---

## cURL example

```bash
curl -X POST "https://example.com/api/index.php/v1/membershippro/categories" \
  -H "X-Joomla-Token: YOUR_API_TOKEN" \
  -H "Accept: application/vnd.api+json" \
  -H "Content-Type: application/json" \
  -d '{"title":"Silver","published":1,"access":1}'
```