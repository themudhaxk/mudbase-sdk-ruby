# Mudbase::ConfirmDirectUploadRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** | The object key returned when the presigned PUT URL was issued |  |
| **project_id** | **String** |  |  |
| **original_name** | **String** |  | [optional] |
| **content_type** | **String** |  | [optional] |
| **size** | **Integer** |  | [optional] |
| **bucket** | **String** |  | [optional] |
| **is_public** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfirmDirectUploadRequest.new(
  key: null,
  project_id: null,
  original_name: null,
  content_type: null,
  size: null,
  bucket: null,
  is_public: null
)
```

