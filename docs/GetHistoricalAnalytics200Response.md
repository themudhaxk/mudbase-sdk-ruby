# Mudbase::GetHistoricalAnalytics200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  | [optional] |
| **period** | **String** |  | [optional] |
| **data** | [**Array&lt;GetHistoricalAnalytics200ResponseDataInner&gt;**](GetHistoricalAnalytics200ResponseDataInner.md) |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetHistoricalAnalytics200Response.new(
  project_id: null,
  period: null,
  data: null,
  generated_at: null
)
```

