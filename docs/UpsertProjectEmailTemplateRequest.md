# Mudbase::UpsertProjectEmailTemplateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subject** | **String** |  |  |
| **html_body** | **String** |  |  |
| **text_body** | **String** |  | [optional] |
| **variables** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpsertProjectEmailTemplateRequest.new(
  subject: null,
  html_body: null,
  text_body: null,
  variables: null
)
```

