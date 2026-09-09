# Mudbase::GenerateSignedUrlRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **expires_in** | **Integer** |  | [optional][default to 3600] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GenerateSignedUrlRequest.new(
  expires_in: 3600
)
```

