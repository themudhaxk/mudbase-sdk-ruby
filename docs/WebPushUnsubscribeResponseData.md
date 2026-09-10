# Mudbase::WebPushUnsubscribeResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **removed** | **Boolean** | True if a matching subscription was removed; false if none was registered.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushUnsubscribeResponseData.new(
  removed: null
)
```

