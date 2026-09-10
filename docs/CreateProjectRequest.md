# Mudbase::CreateProjectRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateProjectRequest.new(
  name: Mudbase Platform,
  description: Main platform for Mudbase services,
  slug: mudbase-platform
)
```

