# Mudbase::ListBackups200ResponseBackupsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **size** | **Integer** |  | [optional] |
| **collections** | **Array&lt;String&gt;** |  | [optional] |
| **file_count** | **Integer** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **completed_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ListBackups200ResponseBackupsInner.new(
  _id: null,
  description: null,
  status: null,
  size: null,
  collections: null,
  file_count: null,
  created_at: null,
  completed_at: null
)
```

