# Mudbase::RealTimeAnalyticsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**check_user_presence**](RealTimeAnalyticsApi.md#check_user_presence) | **POST** /api/realtime/projects/{projectId}/presence | Check presence status for users |
| [**get_active_users**](RealTimeAnalyticsApi.md#get_active_users) | **GET** /api/realtime/projects/{projectId}/active-users | Get active users for a project |
| [**get_event_throughput**](RealTimeAnalyticsApi.md#get_event_throughput) | **GET** /api/realtime/projects/{projectId}/throughput | Get event throughput metrics |
| [**get_global_analytics**](RealTimeAnalyticsApi.md#get_global_analytics) | **GET** /api/realtime/analytics | Get global real-time analytics |
| [**get_historical_analytics**](RealTimeAnalyticsApi.md#get_historical_analytics) | **GET** /api/realtime/projects/{projectId}/history | Get historical analytics |
| [**get_project_analytics**](RealTimeAnalyticsApi.md#get_project_analytics) | **GET** /api/realtime/projects/{projectId}/analytics | Get project real-time analytics |


## check_user_presence

> <CheckUserPresence200Response> check_user_presence(project_id, check_user_presence_request)

Check presence status for users

Returns online status for specified user IDs

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

api_instance = Mudbase::RealTimeAnalyticsApi.new
project_id = 'project_id_example' # String | 
check_user_presence_request = Mudbase::CheckUserPresenceRequest.new({user_ids: ["685acbe0e129932fbb7a0fc2", "685acbe0e129932fbb7a0fc3"]}) # CheckUserPresenceRequest | 

begin
  # Check presence status for users
  result = api_instance.check_user_presence(project_id, check_user_presence_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->check_user_presence: #{e}"
end
```

#### Using the check_user_presence_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CheckUserPresence200Response>, Integer, Hash)> check_user_presence_with_http_info(project_id, check_user_presence_request)

```ruby
begin
  # Check presence status for users
  data, status_code, headers = api_instance.check_user_presence_with_http_info(project_id, check_user_presence_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CheckUserPresence200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->check_user_presence_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **check_user_presence_request** | [**CheckUserPresenceRequest**](CheckUserPresenceRequest.md) |  |  |

### Return type

[**CheckUserPresence200Response**](CheckUserPresence200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_active_users

> <GetActiveUsers200Response> get_active_users(project_id)

Get active users for a project

Returns list of currently connected users

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

api_instance = Mudbase::RealTimeAnalyticsApi.new
project_id = 'project_id_example' # String | 

begin
  # Get active users for a project
  result = api_instance.get_active_users(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_active_users: #{e}"
end
```

#### Using the get_active_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetActiveUsers200Response>, Integer, Hash)> get_active_users_with_http_info(project_id)

```ruby
begin
  # Get active users for a project
  data, status_code, headers = api_instance.get_active_users_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetActiveUsers200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_active_users_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetActiveUsers200Response**](GetActiveUsers200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_event_throughput

> <GetEventThroughput200Response> get_event_throughput(project_id, opts)

Get event throughput metrics

Returns event throughput for a project

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

api_instance = Mudbase::RealTimeAnalyticsApi.new
project_id = 'project_id_example' # String | 
opts = {
  window: 56 # Integer | Time window in milliseconds
}

begin
  # Get event throughput metrics
  result = api_instance.get_event_throughput(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_event_throughput: #{e}"
end
```

#### Using the get_event_throughput_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetEventThroughput200Response>, Integer, Hash)> get_event_throughput_with_http_info(project_id, opts)

```ruby
begin
  # Get event throughput metrics
  data, status_code, headers = api_instance.get_event_throughput_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetEventThroughput200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_event_throughput_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **window** | **Integer** | Time window in milliseconds | [optional][default to 60000] |

### Return type

[**GetEventThroughput200Response**](GetEventThroughput200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_global_analytics

> <GetGlobalAnalytics200Response> get_global_analytics

Get global real-time analytics

Returns system-wide real-time metrics (admin only)

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

api_instance = Mudbase::RealTimeAnalyticsApi.new

begin
  # Get global real-time analytics
  result = api_instance.get_global_analytics
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_global_analytics: #{e}"
end
```

#### Using the get_global_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetGlobalAnalytics200Response>, Integer, Hash)> get_global_analytics_with_http_info

```ruby
begin
  # Get global real-time analytics
  data, status_code, headers = api_instance.get_global_analytics_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetGlobalAnalytics200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_global_analytics_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetGlobalAnalytics200Response**](GetGlobalAnalytics200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_historical_analytics

> <GetHistoricalAnalytics200Response> get_historical_analytics(project_id, opts)

Get historical analytics

Returns historical analytics for charting

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

api_instance = Mudbase::RealTimeAnalyticsApi.new
project_id = 'project_id_example' # String | 
opts = {
  period: 'hour' # String | Time period for historical data
}

begin
  # Get historical analytics
  result = api_instance.get_historical_analytics(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_historical_analytics: #{e}"
end
```

#### Using the get_historical_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetHistoricalAnalytics200Response>, Integer, Hash)> get_historical_analytics_with_http_info(project_id, opts)

```ruby
begin
  # Get historical analytics
  data, status_code, headers = api_instance.get_historical_analytics_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetHistoricalAnalytics200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_historical_analytics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **period** | **String** | Time period for historical data | [optional][default to &#39;hour&#39;] |

### Return type

[**GetHistoricalAnalytics200Response**](GetHistoricalAnalytics200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_analytics

> <GetProjectAnalytics200Response> get_project_analytics(project_id)

Get project real-time analytics

Returns real-time metrics for a specific project (active connections, events, etc.)

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

api_instance = Mudbase::RealTimeAnalyticsApi.new
project_id = '65f1a2b3c4d5e6f7a8b9c0d1' # String | 

begin
  # Get project real-time analytics
  result = api_instance.get_project_analytics(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_project_analytics: #{e}"
end
```

#### Using the get_project_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectAnalytics200Response>, Integer, Hash)> get_project_analytics_with_http_info(project_id)

```ruby
begin
  # Get project real-time analytics
  data, status_code, headers = api_instance.get_project_analytics_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectAnalytics200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RealTimeAnalyticsApi->get_project_analytics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectAnalytics200Response**](GetProjectAnalytics200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

