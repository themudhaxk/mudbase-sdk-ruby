# Mudbase::APIKeysApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_api_key**](APIKeysApi.md#create_api_key) | **POST** /api/api-keys | Create API key |
| [**delete_api_key**](APIKeysApi.md#delete_api_key) | **DELETE** /api/api-keys/{id} | Delete API key |
| [**get_api_key_usage**](APIKeysApi.md#get_api_key_usage) | **GET** /api/api-keys/{id}/usage | Get API key usage |
| [**list_api_keys**](APIKeysApi.md#list_api_keys) | **GET** /api/api-keys | List API keys |
| [**regenerate_api_key**](APIKeysApi.md#regenerate_api_key) | **POST** /api/api-keys/{id}/regenerate | Regenerate API key secret |
| [**update_api_key**](APIKeysApi.md#update_api_key) | **PATCH** /api/api-keys/{id} | Update API key |


## create_api_key

> <CreateApiKey201Response> create_api_key(create_api_key_request)

Create API key

Create a new API key for a project with specified permissions. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::APIKeysApi.new
create_api_key_request = Mudbase::CreateApiKeyRequest.new({name: 'name_example', project_id: 'project_id_example'}) # CreateApiKeyRequest | 

begin
  # Create API key
  result = api_instance.create_api_key(create_api_key_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->create_api_key: #{e}"
end
```

#### Using the create_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateApiKey201Response>, Integer, Hash)> create_api_key_with_http_info(create_api_key_request)

```ruby
begin
  # Create API key
  data, status_code, headers = api_instance.create_api_key_with_http_info(create_api_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateApiKey201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->create_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_api_key_request** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md) |  |  |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_api_key

> <MessageResponse> delete_api_key(id)

Delete API key

Delete an API key. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::APIKeysApi.new
id = 'id_example' # String | 

begin
  # Delete API key
  result = api_instance.delete_api_key(id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->delete_api_key: #{e}"
end
```

#### Using the delete_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_api_key_with_http_info(id)

```ruby
begin
  # Delete API key
  data, status_code, headers = api_instance.delete_api_key_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->delete_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_api_key_usage

> <ApiKeyUsageResponse> get_api_key_usage(id)

Get API key usage

Get usage statistics for a specific API key including request count, rate limit status, and last used timestamp. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::APIKeysApi.new
id = 'id_example' # String | 

begin
  # Get API key usage
  result = api_instance.get_api_key_usage(id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->get_api_key_usage: #{e}"
end
```

#### Using the get_api_key_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiKeyUsageResponse>, Integer, Hash)> get_api_key_usage_with_http_info(id)

```ruby
begin
  # Get API key usage
  data, status_code, headers = api_instance.get_api_key_usage_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiKeyUsageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->get_api_key_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**ApiKeyUsageResponse**](ApiKeyUsageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_api_keys

> <ListApiKeys200Response> list_api_keys

List API keys

List all API keys for the authenticated organization. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::APIKeysApi.new

begin
  # List API keys
  result = api_instance.list_api_keys
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->list_api_keys: #{e}"
end
```

#### Using the list_api_keys_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListApiKeys200Response>, Integer, Hash)> list_api_keys_with_http_info

```ruby
begin
  # List API keys
  data, status_code, headers = api_instance.list_api_keys_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListApiKeys200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->list_api_keys_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## regenerate_api_key

> <RegenerateApiKey200Response> regenerate_api_key(id)

Regenerate API key secret

Regenerate the secret for an API key. The old secret will be invalidated immediately. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::APIKeysApi.new
id = 'id_example' # String | 

begin
  # Regenerate API key secret
  result = api_instance.regenerate_api_key(id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->regenerate_api_key: #{e}"
end
```

#### Using the regenerate_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RegenerateApiKey200Response>, Integer, Hash)> regenerate_api_key_with_http_info(id)

```ruby
begin
  # Regenerate API key secret
  data, status_code, headers = api_instance.regenerate_api_key_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RegenerateApiKey200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->regenerate_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**RegenerateApiKey200Response**](RegenerateApiKey200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_api_key

> <UpdateApiKey200Response> update_api_key(id, update_api_key_request)

Update API key

Update an API key's configuration (name, permissions, status). Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::APIKeysApi.new
id = 'id_example' # String | 
update_api_key_request = Mudbase::UpdateApiKeyRequest.new # UpdateApiKeyRequest | 

begin
  # Update API key
  result = api_instance.update_api_key(id, update_api_key_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->update_api_key: #{e}"
end
```

#### Using the update_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateApiKey200Response>, Integer, Hash)> update_api_key_with_http_info(id, update_api_key_request)

```ruby
begin
  # Update API key
  data, status_code, headers = api_instance.update_api_key_with_http_info(id, update_api_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateApiKey200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling APIKeysApi->update_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_api_key_request** | [**UpdateApiKeyRequest**](UpdateApiKeyRequest.md) |  |  |

### Return type

[**UpdateApiKey200Response**](UpdateApiKey200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

