# Mudbase::HealthApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**health_check**](HealthApi.md#health_check) | **GET** /health | Health check |
| [**system_status**](HealthApi.md#system_status) | **GET** /api/status | System status |


## health_check

> <HealthResponse> health_check

Health check

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::HealthApi.new

begin
  # Health check
  result = api_instance.health_check
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling HealthApi->health_check: #{e}"
end
```

#### Using the health_check_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<HealthResponse>, Integer, Hash)> health_check_with_http_info

```ruby
begin
  # Health check
  data, status_code, headers = api_instance.health_check_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <HealthResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling HealthApi->health_check_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**HealthResponse**](HealthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## system_status

> <SystemStatusResponse> system_status

System status

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

api_instance = Mudbase::HealthApi.new

begin
  # System status
  result = api_instance.system_status
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling HealthApi->system_status: #{e}"
end
```

#### Using the system_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SystemStatusResponse>, Integer, Hash)> system_status_with_http_info

```ruby
begin
  # System status
  data, status_code, headers = api_instance.system_status_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SystemStatusResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling HealthApi->system_status_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SystemStatusResponse**](SystemStatusResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

