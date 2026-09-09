# Mudbase::GeneratePresignedUploadRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket** | **String** |  | [optional][default to &#39;default&#39;] |
| **original_name** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **is_public** | **Boolean** |  | [optional][default to false] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GeneratePresignedUploadRequest.new(
  project_id: null,
  bucket: null,
  original_name: null,
  content_type: null,
  is_public: null
)
```

