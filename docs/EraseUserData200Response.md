# Mudbase::EraseUserData200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  | [optional] |
| **message** | **String** |  | [optional] |
| **data** | [**EraseUserData200ResponseData**](EraseUserData200ResponseData.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EraseUserData200Response.new(
  success: true,
  message: User data anonymized and account disabled,
  data: null
)
```

