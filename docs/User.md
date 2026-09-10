# Mudbase::User

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **first_name** | **String** |  | [optional] |
| **last_name** | **String** |  | [optional] |
| **full_name** | **String** |  | [optional] |
| **avatar** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |
| **custom_role** | **String** | Application-level role slug from the project&#39;s Multi-Role feature (e.g. \&quot;customer\&quot;, \&quot;seller\&quot;). Null for org-level (org/admin/member/viewer) users who aren&#39;t project end-users. | [optional] |
| **is_anonymous** | **Boolean** | True for a guest session created via POST /api/auth/anonymous that hasn&#39;t been converted to a full account yet. | [optional] |
| **email_verified** | **Boolean** |  | [optional] |
| **phone_verified** | **Boolean** |  | [optional] |
| **two_factor_enabled** | **Boolean** |  | [optional] |
| **last_login** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **org** | [**OrganizationSummary**](OrganizationSummary.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::User.new(
  _id: null,
  email: null,
  first_name: null,
  last_name: null,
  full_name: null,
  avatar: null,
  role: null,
  custom_role: null,
  is_anonymous: null,
  email_verified: null,
  phone_verified: null,
  two_factor_enabled: null,
  last_login: null,
  created_at: null,
  updated_at: null,
  org: null
)
```

