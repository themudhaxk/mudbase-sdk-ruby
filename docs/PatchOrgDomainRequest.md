# Mudbase::PatchOrgDomainRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** | Org self-serve reset only; go-live is via admin activate. | [optional] |
| **regenerate_token** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PatchOrgDomainRequest.new(
  status: null,
  regenerate_token: null
)
```

