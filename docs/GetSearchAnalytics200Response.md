# Mudbase::GetSearchAnalytics200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_searches** | **Integer** |  | [optional] |
| **top_queries** | [**Array&lt;GetSearchAnalytics200ResponseTopQueriesInner&gt;**](GetSearchAnalytics200ResponseTopQueriesInner.md) |  | [optional] |
| **searches_by_collection** | **Object** |  | [optional] |
| **average_response_time** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetSearchAnalytics200Response.new(
  total_searches: null,
  top_queries: null,
  searches_by_collection: null,
  average_response_time: null
)
```

