# Mudbase::SignedUrlResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  | [optional] |
| **url** | **String** | Signed URL for file access | [optional] |
| **expires_at** | **Time** | Expiration time of the signed URL (optional - some endpoints return expiresIn instead) | [optional] |
| **expires_in** | **Integer** | Time-to-live in seconds for the signed URL (optional) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SignedUrlResponse.new(
  success: null,
  url: null,
  expires_at: null,
  expires_in: null
)
```

