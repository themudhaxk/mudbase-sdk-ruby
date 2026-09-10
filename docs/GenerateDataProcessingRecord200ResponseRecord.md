# Mudbase::GenerateDataProcessingRecord200ResponseRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  | [optional] |
| **record_date** | **Time** |  | [optional] |
| **data_controller** | **Object** |  | [optional] |
| **processing_activities** | **Array&lt;Object&gt;** |  | [optional] |
| **data_subjects** | **Array&lt;String&gt;** |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GenerateDataProcessingRecord200ResponseRecord.new(
  org_id: null,
  record_date: null,
  data_controller: null,
  processing_activities: null,
  data_subjects: null,
  generated_at: null
)
```

