# Mudbase::ProvisionEnterpriseRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **provision_request_id** | **String** |  |  |
| **api_base_url** | **String** |  |  |
| **db_ref** | **String** |  |  |
| **server_id** | **String** |  |  |
| **region** | **String** |  | [optional] |
| **version** | **String** |  | [optional] |
| **force_override** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProvisionEnterpriseRequest.new(
  org_id: null,
  provision_request_id: null,
  api_base_url: null,
  db_ref: null,
  server_id: null,
  region: null,
  version: null,
  force_override: null
)
```

