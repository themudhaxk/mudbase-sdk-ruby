# Mudbase::CreateBucketRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | The name of the bucket |  |
| **is_public** | **Boolean** | Whether the bucket is publicly accessible | [optional][default to false] |
| **settings** | **Object** | Additional bucket settings | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateBucketRequest.new(
  name: null,
  is_public: null,
  settings: null
)
```

