# Mudbase::ConfirmUploadResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **scan** | [**ConfirmUploadResponseScan**](ConfirmUploadResponseScan.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfirmUploadResponse.new(
  file_id: null,
  status: null,
  scan: null
)
```

