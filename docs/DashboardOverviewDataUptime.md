# Mudbase::DashboardOverviewDataUptime

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **scope** | **String** |  | [optional] |
| **display_pct30d** | **Float** |  | [optional] |
| **display_source** | **String** |  | [optional] |
| **is_preliminary** | **Boolean** |  | [optional] |
| **platform_probe_pct30d** | **Float** |  | [optional] |
| **platform_samples** | **Integer** |  | [optional] |
| **platform_ok_samples** | **Integer** |  | [optional] |
| **org_http_non5xx_pct30d** | **Float** |  | [optional] |
| **org_http_sampled30d** | **Integer** |  | [optional] |
| **org_http5xx30d** | **Integer** | Metered 5xx count from UsageStat (trackApiCall) | [optional] |
| **project_http5xx30d** | **Integer** | This project’s metered 5xx count (30d) | [optional] |
| **global_http_non5xx_pct30d** | **Float** | Deprecated alias for orgHttpNon5xxPct30d | [optional] |
| **global_http_sampled30d** | **Integer** | Deprecated alias for orgHttpSampled30d | [optional] |
| **request_non5xx_pct30d** | **Float** | Deprecated alias for orgHttpNon5xxPct30d | [optional] |
| **request_sampled30d** | **Integer** | Deprecated alias for orgHttpSampled30d | [optional] |
| **project_http_non5xx_pct30d** | **Float** |  | [optional] |
| **project_http_sampled30d** | **Integer** |  | [optional] |
| **help** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewDataUptime.new(
  scope: null,
  display_pct30d: null,
  display_source: null,
  is_preliminary: null,
  platform_probe_pct30d: null,
  platform_samples: null,
  platform_ok_samples: null,
  org_http_non5xx_pct30d: null,
  org_http_sampled30d: null,
  org_http5xx30d: null,
  project_http5xx30d: null,
  global_http_non5xx_pct30d: null,
  global_http_sampled30d: null,
  request_non5xx_pct30d: null,
  request_sampled30d: null,
  project_http_non5xx_pct30d: null,
  project_http_sampled30d: null,
  help: null
)
```

