# Mudbase::CreateFunctionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **code** | **String** | Function body (async, has access to payload, db, files, messaging, utils, env, console) |  |
| **trigger** | [**FunctionTrigger**](FunctionTrigger.md) |  |  |
| **environment** | **Hash&lt;String, String&gt;** | Per-function env vars injected into sandbox | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateFunctionRequest.new(
  name: null,
  description: null,
  code: null,
  trigger: null,
  environment: null
)
```

