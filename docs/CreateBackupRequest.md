# Mudbase::CreateBackupRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **description** | **String** |  | [optional] |
| **include_files** | **Boolean** |  | [optional][default to true] |
| **include_wallets** | **Boolean** |  | [optional][default to false] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateBackupRequest.new(
  description: Pre-deployment backup,
  include_files: true,
  include_wallets: false
)
```

