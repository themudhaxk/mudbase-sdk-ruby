# Mudbase::GenerateAccessReview200ResponseReport

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  | [optional] |
| **review_period** | **Object** |  | [optional] |
| **users** | **Array&lt;Object&gt;** |  | [optional] |
| **summary** | **Object** |  | [optional] |
| **recommendations** | **Array&lt;String&gt;** |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GenerateAccessReview200ResponseReport.new(
  org_id: null,
  review_period: null,
  users: null,
  summary: null,
  recommendations: null,
  generated_at: null
)
```

