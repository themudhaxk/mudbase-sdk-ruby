# Mudbase::ResendVerificationAuthRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **project_id** | **String** | Optional; for project-scoped signup (sends link with project context) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ResendVerificationAuthRequest.new(
  email: null,
  project_id: null
)
```

