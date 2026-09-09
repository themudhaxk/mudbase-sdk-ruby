# Mudbase::GetComplianceSummary200ResponseComplianceSecurity

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **password_policy** | **String** |  | [optional] |
| **virus_scanning** | **Boolean** |  | [optional] |
| **encryption_at_rest** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetComplianceSummary200ResponseComplianceSecurity.new(
  password_policy: null,
  virus_scanning: null,
  encryption_at_rest: null
)
```

