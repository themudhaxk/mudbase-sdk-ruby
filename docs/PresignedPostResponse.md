# Mudbase::PresignedPostResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** | Object key clients should upload to | [optional] |
| **url** | **String** | Presigned URL to PUT the file body to directly | [optional] |
| **method** | **String** | HTTP method the client must use against &#x60;url&#x60; (always PUT - the object storage backend does not implement a POST-based upload API) | [optional] |
| **headers** | **Object** | Headers the client must send with the PUT request (e.g. Content-Type) - mismatching these from what was signed causes a SignatureDoesNotMatch error | [optional] |
| **expires_in** | **Integer** | Expiration of the presigned URL in seconds | [optional] |
| **max_file_upload_bytes** | **Integer** | Maximum upload size in bytes for this org plan. Not enforced by the presigned URL itself (PUT has no content-length-range equivalent) - checked server-side by /api/files/upload/confirm after the upload completes | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PresignedPostResponse.new(
  key: null,
  url: null,
  method: null,
  headers: null,
  expires_in: null,
  max_file_upload_bytes: null
)
```

