# Mudbase::InternalDomainDnsRecheckBatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **max_orgs** | **Integer** |  | [optional] |
| **recheck_older_than_hours** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InternalDomainDnsRecheckBatchRequest.new(
  max_orgs: null,
  recheck_older_than_hours: null
)
```

