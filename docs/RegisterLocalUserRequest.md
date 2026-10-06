# Mudbase::RegisterLocalUserRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** |  |  |
| **first_name** | **String** |  |  |
| **last_name** | **String** |  |  |
| **project_id** | **String** |  |  |
| **agreed_to_terms** | **Boolean** | Optional. End users signing up inside a customer&#39;s app have never seen or agreed to Mudbase&#39;s own Terms of Service, so this field is not required here and is never recorded as platform ToS acceptance. A generated-app form may send it if the app has its own ToS checkbox, but Mudbase does not write it to any consent record.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RegisterLocalUserRequest.new(
  email: null,
  password: null,
  first_name: null,
  last_name: null,
  project_id: null,
  agreed_to_terms: null
)
```

