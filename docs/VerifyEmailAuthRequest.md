# Mudbase::VerifyEmailAuthRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | Verification token from the email link |  |
| **project_id** | **String** | Optional; for project signup context (redirect hint) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::VerifyEmailAuthRequest.new(
  token: null,
  project_id: null
)
```

