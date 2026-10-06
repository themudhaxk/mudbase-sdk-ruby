# Mudbase::ResetLocalPasswordRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **password** | **String** |  |  |
| **project_id** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ResetLocalPasswordRequest.new(
  password: NewSecurePass123!,
  project_id: 65f1a2b3c4d5e6f7a8b9c0d1
)
```

