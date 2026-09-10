# Mudbase::UpdateUserAccountStatusRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_status** | **String** | active &#x3D; full access; suspended &#x3D; blocked from using the app |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateUserAccountStatusRequest.new(
  account_status: null
)
```

