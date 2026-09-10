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
  project_id: 685ad30be129932fbb7a1047
)
```

