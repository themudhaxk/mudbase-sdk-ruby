# Mudbase::FeatureNotAllowedError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **error** | **String** |  |  |
| **resource** | **String** |  | [optional] |
| **action** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FeatureNotAllowedError.new(
  success: false,
  error: feature_not_allowed,
  resource: messaging,
  action: email,
  message: Your role does not have permission to send email for this project.
)
```

