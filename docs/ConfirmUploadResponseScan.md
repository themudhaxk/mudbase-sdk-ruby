# Mudbase::ConfirmUploadResponseScan

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **detections** | **Integer** |  | [optional] |
| **analysis** | **Object** | Raw analysis object returned by the scanner (e.g., VirusTotal) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfirmUploadResponseScan.new(
  status: null,
  provider: null,
  detections: null,
  analysis: null
)
```

