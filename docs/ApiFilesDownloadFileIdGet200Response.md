# Mudbase::ApiFilesDownloadFileIdGet200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url** | **String** |  | [optional] |
| **expires_in** | **Integer** | Seconds until the signed URL expires; null for public files. | [optional] |
| **is_public** | **Boolean** | Present and true only when the file is public. | [optional] |
| **warning** | **String** | Present only for public files — explains the URL is permanent and unprotected. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiFilesDownloadFileIdGet200Response.new(
  url: null,
  expires_in: null,
  is_public: null,
  warning: null
)
```

