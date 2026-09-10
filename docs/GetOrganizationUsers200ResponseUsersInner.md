# Mudbase::GetOrganizationUsers200ResponseUsersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **first_name** | **String** |  | [optional] |
| **last_name** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **avatar** | **String** |  | [optional] |
| **email_verified** | **Boolean** |  | [optional] |
| **role** | **String** |  | [optional] |
| **custom_role** | **String** |  | [optional] |
| **phone** | **String** |  | [optional] |
| **phone_verified** | **Boolean** |  | [optional] |
| **last_login** | **Time** |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **account_status** | **String** |  | [optional] |
| **is_anonymous** | **Boolean** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **project** | [**GetOrganizationUsers200ResponseUsersInnerProject**](GetOrganizationUsers200ResponseUsersInnerProject.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetOrganizationUsers200ResponseUsersInner.new(
  _id: null,
  first_name: null,
  last_name: null,
  email: null,
  avatar: null,
  email_verified: null,
  role: null,
  custom_role: null,
  phone: null,
  phone_verified: null,
  last_login: null,
  is_active: null,
  account_status: null,
  is_anonymous: null,
  created_at: null,
  project: null
)
```

