# Mudbase::ApiProjectsProjectIdKybSessionsPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workflow_id** | **String** | Overrides the organization&#39;s default KYB workflow. | [optional] |
| **vendor_business_id** | **String** | Your own identifier for the business being verified. | [optional] |
| **vendor_data** | **String** | Arbitrary reference echoed back on webhooks. | [optional] |
| **callback** | **String** | Where to redirect the business user after the hosted flow. | [optional] |
| **language** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiProjectsProjectIdKybSessionsPostRequest.new(
  workflow_id: null,
  vendor_business_id: null,
  vendor_data: null,
  callback: null,
  language: null
)
```

