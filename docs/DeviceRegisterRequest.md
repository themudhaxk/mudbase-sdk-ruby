# Mudbase::DeviceRegisterRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | The device push token issued to your app by its push client. |  |
| **platform** | **String** | The device platform. Defaults to &#x60;unknown&#x60; when omitted or unrecognized. | [optional][default to &#39;unknown&#39;] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DeviceRegisterRequest.new(
  token: null,
  platform: null
)
```

