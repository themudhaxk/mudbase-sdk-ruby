# Mudbase::WebPushConfigPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **rotate_keys** | **Boolean** |  | [optional] |
| **subject** | **String** | A &#x60;mailto:&#x60; address or an &#x60;https&#x60; URL. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushConfigPatchRequest.new(
  enabled: null,
  rotate_keys: null,
  subject: null
)
```

