# Mudbase::UpdateFunctionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **code** | **String** |  | [optional] |
| **trigger** | [**FunctionTrigger**](FunctionTrigger.md) |  | [optional] |
| **environment** | **Object** |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **limits** | [**UpdateFunctionRequestLimits**](UpdateFunctionRequestLimits.md) |  | [optional] |
| **retry_policy** | [**UpdateFunctionRequestRetryPolicy**](UpdateFunctionRequestRetryPolicy.md) |  | [optional] |
| **version_comment** | **String** | Comment for version when code is updated | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateFunctionRequest.new(
  name: null,
  description: null,
  code: null,
  trigger: null,
  environment: null,
  is_active: null,
  limits: null,
  retry_policy: null,
  version_comment: null
)
```

