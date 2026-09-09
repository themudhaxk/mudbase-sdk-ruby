# Mudbase::CreatePlanRequestFeaturesInnerOneOf

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **included** | **Boolean** |  | [optional][default to true] |
| **limit** | **Float** | Usage cap for this feature; omit or null for unlimited. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreatePlanRequestFeaturesInnerOneOf.new(
  name: null,
  description: null,
  included: null,
  limit: null
)
```

