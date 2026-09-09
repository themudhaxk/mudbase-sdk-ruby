# Mudbase::EmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | [**EmailRequestTo**](EmailRequestTo.md) |  |  |
| **subject** | **String** |  |  |
| **html** | **String** |  | [optional] |
| **text** | **String** |  | [optional] |
| **template_id** | **String** |  | [optional] |
| **template_data** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EmailRequest.new(
  to: null,
  subject: null,
  html: null,
  text: null,
  template_id: null,
  template_data: null
)
```

