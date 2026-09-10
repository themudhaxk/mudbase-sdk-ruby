# Mudbase::MonitoringApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_monitoring_alert**](MonitoringApi.md#create_monitoring_alert) | **POST** /api/monitoring/alerts | Create monitoring alert |
| [**get_monitoring_analytics**](MonitoringApi.md#get_monitoring_analytics) | **GET** /api/monitoring/analytics | Get usage analytics (time series) |
| [**get_monitoring_errors**](MonitoringApi.md#get_monitoring_errors) | **GET** /api/monitoring/errors | Get error logs |
| [**get_monitoring_latency_insights**](MonitoringApi.md#get_monitoring_latency_insights) | **GET** /api/monitoring/latency-insights | Latency insights (route templates, percentiles, impact scores) |
| [**get_monitoring_logs**](MonitoringApi.md#get_monitoring_logs) | **GET** /api/monitoring/logs | Get audit logs |
| [**get_monitoring_performance**](MonitoringApi.md#get_monitoring_performance) | **GET** /api/monitoring/performance | Get performance metrics |
| [**get_monitoring_queue_metrics**](MonitoringApi.md#get_monitoring_queue_metrics) | **GET** /api/monitoring/queue-metrics | Usage metering queue job counts |
| [**list_monitoring_alerts**](MonitoringApi.md#list_monitoring_alerts) | **GET** /api/monitoring/alerts | List monitoring alerts |


## create_monitoring_alert

> create_monitoring_alert(create_monitoring_alert_request)

Create monitoring alert

Create a monitoring alert (plan limit alertsPerProject enforced).

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new
create_monitoring_alert_request = Mudbase::CreateMonitoringAlertRequest.new # CreateMonitoringAlertRequest | 

begin
  # Create monitoring alert
  api_instance.create_monitoring_alert(create_monitoring_alert_request)
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->create_monitoring_alert: #{e}"
end
```

#### Using the create_monitoring_alert_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_monitoring_alert_with_http_info(create_monitoring_alert_request)

```ruby
begin
  # Create monitoring alert
  data, status_code, headers = api_instance.create_monitoring_alert_with_http_info(create_monitoring_alert_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->create_monitoring_alert_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_monitoring_alert_request** | [**CreateMonitoringAlertRequest**](CreateMonitoringAlertRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_monitoring_analytics

> <MonitoringAnalyticsResponse> get_monitoring_analytics(opts)

Get usage analytics (time series)

Aggregates UsageStat by day/week/month. Optional **projectId** scopes to one project. Query **days** (1–90) for a rolling window (e.g. **days=14**); when set, overrides **period**. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new
opts = {
  project_id: 'project_id_example', # String | 
  period: 'day', # String | 
  granularity: 'day', # String | 
  days: 56 # Integer | Rolling window in days (1–90); when set, period becomes last_N_days
}

begin
  # Get usage analytics (time series)
  result = api_instance.get_monitoring_analytics(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_analytics: #{e}"
end
```

#### Using the get_monitoring_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MonitoringAnalyticsResponse>, Integer, Hash)> get_monitoring_analytics_with_http_info(opts)

```ruby
begin
  # Get usage analytics (time series)
  data, status_code, headers = api_instance.get_monitoring_analytics_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MonitoringAnalyticsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_analytics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  | [optional] |
| **period** | **String** |  | [optional][default to &#39;month&#39;] |
| **granularity** | **String** |  | [optional][default to &#39;day&#39;] |
| **days** | **Integer** | Rolling window in days (1–90); when set, period becomes last_N_days | [optional] |

### Return type

[**MonitoringAnalyticsResponse**](MonitoringAnalyticsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_monitoring_errors

> get_monitoring_errors

Get error logs

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new

begin
  # Get error logs
  api_instance.get_monitoring_errors
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_errors: #{e}"
end
```

#### Using the get_monitoring_errors_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_monitoring_errors_with_http_info

```ruby
begin
  # Get error logs
  data, status_code, headers = api_instance.get_monitoring_errors_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_errors_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_monitoring_latency_insights

> get_monitoring_latency_insights

Latency insights (route templates, percentiles, impact scores)

Per-process snapshot: normalized **routeKey** (METHOD + path template), **p50/p95/p99**, 4xx/5xx counts, **impactScore**, **alertsSuggested**, **rps**, **inFlight**, **eventLoopLagP99Ms**. One buffer per server instance. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new

begin
  # Latency insights (route templates, percentiles, impact scores)
  api_instance.get_monitoring_latency_insights
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_latency_insights: #{e}"
end
```

#### Using the get_monitoring_latency_insights_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_monitoring_latency_insights_with_http_info

```ruby
begin
  # Latency insights (route templates, percentiles, impact scores)
  data, status_code, headers = api_instance.get_monitoring_latency_insights_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_latency_insights_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_monitoring_logs

> <MonitoringLogsResponse> get_monitoring_logs(opts)

Get audit logs

Paginated audit trail for the org. Use **projectId** to scope to one project; **level=all** or **audit** for full activity feed. Each entry includes **activityTitle** and **activityDetail** for dashboard copy. Requires monitoring read permission. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  project_id: 'project_id_example', # String | Filter to this project (must belong to org)
  user_id: 'user_id_example', # String | Filter to this user's audit entries
  level: 'level_example', # String | error|security|all|audit|low|medium|high|critical
  start_date: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  end_date: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  action: 'action_example', # String | 
  resource: 'resource_example' # String | 
}

begin
  # Get audit logs
  result = api_instance.get_monitoring_logs(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_logs: #{e}"
end
```

#### Using the get_monitoring_logs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MonitoringLogsResponse>, Integer, Hash)> get_monitoring_logs_with_http_info(opts)

```ruby
begin
  # Get audit logs
  data, status_code, headers = api_instance.get_monitoring_logs_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MonitoringLogsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_logs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **project_id** | **String** | Filter to this project (must belong to org) | [optional] |
| **user_id** | **String** | Filter to this user&#39;s audit entries | [optional] |
| **level** | **String** | error|security|all|audit|low|medium|high|critical | [optional][default to &#39;error&#39;] |
| **start_date** | **Time** |  | [optional] |
| **end_date** | **Time** |  | [optional] |
| **action** | **String** |  | [optional] |
| **resource** | **String** |  | [optional] |

### Return type

[**MonitoringLogsResponse**](MonitoringLogsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_monitoring_performance

> <MonitoringPerformanceResponse> get_monitoring_performance(opts)

Get performance metrics

Response time stats from AuditLog where available. With **projectId**, falls back to UsageStat latency averages when audit data is sparse (**latencySource** may be **usage_stat**). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new
opts = {
  project_id: 'project_id_example', # String | 
  period: 'hour' # String | 
}

begin
  # Get performance metrics
  result = api_instance.get_monitoring_performance(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_performance: #{e}"
end
```

#### Using the get_monitoring_performance_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MonitoringPerformanceResponse>, Integer, Hash)> get_monitoring_performance_with_http_info(opts)

```ruby
begin
  # Get performance metrics
  data, status_code, headers = api_instance.get_monitoring_performance_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MonitoringPerformanceResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_performance_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  | [optional] |
| **period** | **String** |  | [optional][default to &#39;hour&#39;] |

### Return type

[**MonitoringPerformanceResponse**](MonitoringPerformanceResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_monitoring_queue_metrics

> get_monitoring_queue_metrics

Usage metering queue job counts

BullMQ **usage-events** queue counts when `USE_METERING_QUEUE` and `REDIS_URL` are set.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new

begin
  # Usage metering queue job counts
  api_instance.get_monitoring_queue_metrics
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_queue_metrics: #{e}"
end
```

#### Using the get_monitoring_queue_metrics_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_monitoring_queue_metrics_with_http_info

```ruby
begin
  # Usage metering queue job counts
  data, status_code, headers = api_instance.get_monitoring_queue_metrics_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->get_monitoring_queue_metrics_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_monitoring_alerts

> list_monitoring_alerts

List monitoring alerts

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MonitoringApi.new

begin
  # List monitoring alerts
  api_instance.list_monitoring_alerts
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->list_monitoring_alerts: #{e}"
end
```

#### Using the list_monitoring_alerts_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_monitoring_alerts_with_http_info

```ruby
begin
  # List monitoring alerts
  data, status_code, headers = api_instance.list_monitoring_alerts_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MonitoringApi->list_monitoring_alerts_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

