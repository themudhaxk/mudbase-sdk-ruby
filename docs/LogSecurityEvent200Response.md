# Mudbase::LogSecurityEvent200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **event** | [**LogSecurityEvent200ResponseEvent**](LogSecurityEvent200ResponseEvent.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::LogSecurityEvent200Response.new(
  message: Security event logged,
  event: null
)
```

