# Mudbase::EmailTemplateCatalogItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **is_customized** | **Boolean** | True if this project has a stored override for this template name. | [optional] |
| **effective_source** | **String** | Which layer is used at send time for this name. | [optional] |
| **subject_snippet** | **String** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **version** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EmailTemplateCatalogItem.new(
  name: null,
  is_customized: null,
  effective_source: null,
  subject_snippet: null,
  updated_at: null,
  version: null
)
```

