# Mudbase::RegisterWithRoleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** |  |  |
| **first_name** | **String** |  |  |
| **last_name** | **String** |  |  |
| **project_id** | **String** |  |  |
| **agreed_to_terms** | **Boolean** | Must be &#x60;true&#x60; - the server rejects the request otherwise. Required to stop a direct API call from creating an account without accepting the Terms of Service and Privacy Policy. |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RegisterWithRoleRequest.new(
  email: null,
  password: null,
  first_name: null,
  last_name: null,
  project_id: null,
  agreed_to_terms: null
)
```

