# Mudbase::DeviceUnregisteredResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **removed** | **Boolean** | True if a matching token was removed; false if none was registered. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DeviceUnregisteredResponseData.new(
  removed: null
)
```

