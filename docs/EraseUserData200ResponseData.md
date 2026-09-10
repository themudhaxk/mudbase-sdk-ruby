# Mudbase::EraseUserData200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **already_erased** | **Boolean** |  | [optional] |
| **subject_id** | **String** |  | [optional] |
| **anonymized** | **Boolean** |  | [optional] |
| **sessions_revoked** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EraseUserData200ResponseData.new(
  already_erased: false,
  subject_id: 685acbe0e129932fbb7a0fc2,
  anonymized: true,
  sessions_revoked: true
)
```

