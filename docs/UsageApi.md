# Mudbase::UsageApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_overage**](UsageApi.md#get_overage) | **GET** /api/usage/overage | Get current overage line items |
| [**get_project_usage_stats**](UsageApi.md#get_project_usage_stats) | **GET** /api/usage/projects/{projectId} | Get project usage |
| [**get_project_usage_summary**](UsageApi.md#get_project_usage_summary) | **GET** /api/usage/projects/{projectId}/summary | Project dashboard usage summary |
| [**get_usage**](UsageApi.md#get_usage) | **GET** /api/usage | Get organization usage |
| [**get_usage_trends**](UsageApi.md#get_usage_trends) | **GET** /api/usage/trends | Get usage trends |
| [**get_usage_warnings**](UsageApi.md#get_usage_warnings) | **GET** /api/usage/warnings | Get usage warnings |


## get_overage

> <GetOverage200Response> get_overage

Get current overage line items

Returns overage line items for the authenticated organization's current billing period (current month). Used by dashboards and billing UIs. Requires org-level JWT (authRequired). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new

begin
  # Get current overage line items
  result = api_instance.get_overage
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_overage: #{e}"
end
```

#### Using the get_overage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOverage200Response>, Integer, Hash)> get_overage_with_http_info

```ruby
begin
  # Get current overage line items
  data, status_code, headers = api_instance.get_overage_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOverage200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_overage_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetOverage200Response**](GetOverage200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_usage_stats

> <ProjectUsageStatsResponse> get_project_usage_stats(project_id, opts)

Get project usage

Get usage statistics for a project (API calls, storage, bandwidth, database operations). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new
project_id = 'project_id_example' # String | 
opts = {
  period: 'day' # String | 
}

begin
  # Get project usage
  result = api_instance.get_project_usage_stats(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_project_usage_stats: #{e}"
end
```

#### Using the get_project_usage_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectUsageStatsResponse>, Integer, Hash)> get_project_usage_stats_with_http_info(project_id, opts)

```ruby
begin
  # Get project usage
  data, status_code, headers = api_instance.get_project_usage_stats_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectUsageStatsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_project_usage_stats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **period** | **String** |  | [optional][default to &#39;month&#39;] |

### Return type

[**ProjectUsageStatsResponse**](ProjectUsageStatsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_usage_summary

> <ProjectUsageSummaryResponse> get_project_usage_summary(project_id)

Project dashboard usage summary

Lightweight dashboard metrics for a project: requests today vs yesterday with % change, active users (24h/7d/30d), 7d active-user trend, 14-day request volume series, per-project openapi-docs latency (today/7d), and uptime (30d) from org HTTP non-5xx when enough samples else DB heartbeats. Same auth as GET /api/usage/projects/{projectId} (org JWT, project JWT, or API key scoped to the project). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new
project_id = 'project_id_example' # String | 

begin
  # Project dashboard usage summary
  result = api_instance.get_project_usage_summary(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_project_usage_summary: #{e}"
end
```

#### Using the get_project_usage_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectUsageSummaryResponse>, Integer, Hash)> get_project_usage_summary_with_http_info(project_id)

```ruby
begin
  # Project dashboard usage summary
  data, status_code, headers = api_instance.get_project_usage_summary_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectUsageSummaryResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_project_usage_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**ProjectUsageSummaryResponse**](ProjectUsageSummaryResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_usage

> <UsageStatsResponse> get_usage(opts)

Get organization usage

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new
opts = {
  period: 'day', # String | 
  start_date: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  end_date: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # Get organization usage
  result = api_instance.get_usage(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage: #{e}"
end
```

#### Using the get_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UsageStatsResponse>, Integer, Hash)> get_usage_with_http_info(opts)

```ruby
begin
  # Get organization usage
  data, status_code, headers = api_instance.get_usage_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UsageStatsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **period** | **String** |  | [optional][default to &#39;month&#39;] |
| **start_date** | **Time** |  | [optional] |
| **end_date** | **Time** |  | [optional] |

### Return type

[**UsageStatsResponse**](UsageStatsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_usage_trends

> <UsageTrendsResponse> get_usage_trends(opts)

Get usage trends

Get usage trends over time for the authenticated organization or project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new
opts = {
  days: 56 # Integer | 
}

begin
  # Get usage trends
  result = api_instance.get_usage_trends(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage_trends: #{e}"
end
```

#### Using the get_usage_trends_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UsageTrendsResponse>, Integer, Hash)> get_usage_trends_with_http_info(opts)

```ruby
begin
  # Get usage trends
  data, status_code, headers = api_instance.get_usage_trends_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UsageTrendsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage_trends_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **days** | **Integer** |  | [optional][default to 30] |

### Return type

[**UsageTrendsResponse**](UsageTrendsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_usage_warnings

> <GetUsageWarnings200Response> get_usage_warnings

Get usage warnings

Returns usage warnings for the authenticated org (e.g. at 80% and 95% of plan limits). Requires org-level JWT.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsageApi.new

begin
  # Get usage warnings
  result = api_instance.get_usage_warnings
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage_warnings: #{e}"
end
```

#### Using the get_usage_warnings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUsageWarnings200Response>, Integer, Hash)> get_usage_warnings_with_http_info

```ruby
begin
  # Get usage warnings
  data, status_code, headers = api_instance.get_usage_warnings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUsageWarnings200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsageApi->get_usage_warnings_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetUsageWarnings200Response**](GetUsageWarnings200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

