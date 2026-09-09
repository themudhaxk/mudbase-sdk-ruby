# Mudbase::RequestLocalPasswordResetRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **project_id** | **String** | Required for project-based reset (sends OTP). Omit for org token link. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RequestLocalPasswordResetRequest.new(
  email: user@example.com,
  project_id: 685ad30be129932fbb7a1047
)
```

