# Mudbase::EmailTemplateResolved

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **html_body** | **String** |  | [optional] |
| **text_body** | **String** |  | [optional] |
| **variables** | **Array&lt;String&gt;** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **version** | **Integer** |  | [optional] |
| **is_project_override** | **Boolean** |  | [optional] |
| **effective_source** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EmailTemplateResolved.new(
  name: null,
  subject: null,
  html_body: null,
  text_body: null,
  variables: null,
  updated_at: null,
  version: null,
  is_project_override: null,
  effective_source: null
)
```

