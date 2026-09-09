# Mudbase::RestoreBackupRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **restore_mode** | **String** |  | [optional] |
| **collections** | **Array&lt;String&gt;** | Optional: specific collections to restore | [optional] |
| **confirmation** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RestoreBackupRequest.new(
  restore_mode: replace,
  collections: [&quot;products&quot;,&quot;orders&quot;],
  confirmation: RESTORE_DATA
)
```

