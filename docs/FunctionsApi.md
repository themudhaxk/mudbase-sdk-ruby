# Mudbase::FunctionsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**activate_function**](FunctionsApi.md#activate_function) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/activate | Activate function |
| [**create_function**](FunctionsApi.md#create_function) | **POST** /api/functions/projects/{projectId}/functions | Create function |
| [**deactivate_function**](FunctionsApi.md#deactivate_function) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/deactivate | Deactivate function |
| [**delete_function**](FunctionsApi.md#delete_function) | **DELETE** /api/functions/projects/{projectId}/functions/{functionId} | Delete function |
| [**execute_function**](FunctionsApi.md#execute_function) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/execute | Execute function |
| [**get_function**](FunctionsApi.md#get_function) | **GET** /api/functions/projects/{projectId}/functions/{functionId} | Get function |
| [**get_function_execution**](FunctionsApi.md#get_function_execution) | **GET** /api/functions/projects/{projectId}/functions/{functionId}/executions/{executionId} | Get execution status |
| [**get_function_logs**](FunctionsApi.md#get_function_logs) | **GET** /api/functions/projects/{projectId}/functions/{functionId}/logs | Get function execution logs |
| [**get_function_versions**](FunctionsApi.md#get_function_versions) | **GET** /api/functions/projects/{projectId}/functions/{functionId}/versions | Get function versions |
| [**list_functions**](FunctionsApi.md#list_functions) | **GET** /api/functions/projects/{projectId}/functions | List functions |
| [**retry_function_execution**](FunctionsApi.md#retry_function_execution) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/retry/{executionIndex} | Retry failed execution |
| [**rollback_function**](FunctionsApi.md#rollback_function) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/rollback | Rollback to previous version |
| [**simulate_function_trigger**](FunctionsApi.md#simulate_function_trigger) | **POST** /api/functions/projects/{projectId}/functions/{functionId}/simulate | Simulate trigger |
| [**trigger_function_webhook**](FunctionsApi.md#trigger_function_webhook) | **POST** /api/functions/webhook/{projectId} | Trigger webhook functions |
| [**update_function**](FunctionsApi.md#update_function) | **PUT** /api/functions/projects/{projectId}/functions/{functionId} | Update function |


## activate_function

> <FunctionResponse> activate_function(project_id, function_id)

Activate function

Activate a deactivated function. Active functions can be triggered.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 

begin
  # Activate function
  result = api_instance.activate_function(project_id, function_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->activate_function: #{e}"
end
```

#### Using the activate_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> activate_function_with_http_info(project_id, function_id)

```ruby
begin
  # Activate function
  data, status_code, headers = api_instance.activate_function_with_http_info(project_id, function_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->activate_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_function

> <FunctionResponse> create_function(project_id, create_function_request)

Create function

Create a new serverless function. Trigger types: http, document, file, webhook, cron, messaging. Sandbox globals available today: `payload`, `context`, `env`, `console`. Function code runs in an isolated worker with no ambient network or database access — it can only read its trigger payload, the `env` vars you configure, and return a JSON-serializable result; it cannot yet call back into your project's database, storage, or messaging APIs from inside the function body. If you need to read or write project data from a function, call the regular REST API (with your own API key) from your own backend in response to the function's returned result, rather than from within the function's own code. 

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
create_function_request = Mudbase::CreateFunctionRequest.new({name: 'name_example', code: 'code_example', trigger: Mudbase::FunctionTrigger.new({type: 'http'})}) # CreateFunctionRequest | 

begin
  # Create function
  result = api_instance.create_function(project_id, create_function_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->create_function: #{e}"
end
```

#### Using the create_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> create_function_with_http_info(project_id, create_function_request)

```ruby
begin
  # Create function
  data, status_code, headers = api_instance.create_function_with_http_info(project_id, create_function_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->create_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_function_request** | [**CreateFunctionRequest**](CreateFunctionRequest.md) |  |  |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## deactivate_function

> <FunctionResponse> deactivate_function(project_id, function_id)

Deactivate function

Deactivate a function. Deactivated functions will not be triggered.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 

begin
  # Deactivate function
  result = api_instance.deactivate_function(project_id, function_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->deactivate_function: #{e}"
end
```

#### Using the deactivate_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> deactivate_function_with_http_info(project_id, function_id)

```ruby
begin
  # Deactivate function
  data, status_code, headers = api_instance.deactivate_function_with_http_info(project_id, function_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->deactivate_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_function

> <DeleteFunction200Response> delete_function(project_id, function_id)

Delete function

Delete a function permanently. This is a destructive operation.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 

begin
  # Delete function
  result = api_instance.delete_function(project_id, function_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->delete_function: #{e}"
end
```

#### Using the delete_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteFunction200Response>, Integer, Hash)> delete_function_with_http_info(project_id, function_id)

```ruby
begin
  # Delete function
  data, status_code, headers = api_instance.delete_function_with_http_info(project_id, function_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteFunction200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->delete_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |

### Return type

[**DeleteFunction200Response**](DeleteFunction200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## execute_function

> <FunctionExecutionResponse> execute_function(project_id, function_id, opts)

Execute function

Manually execute a function with custom payload. Payload is merged with auto-injected trigger context. Rate limited (data mutation rate limiter). Enforces maxExecutionsPerMinute/maxExecutionsPerHour.  This endpoint is asynchronous: it returns 202 immediately with an `executionId`, before the function has necessarily finished running. Poll `GET /api/functions/projects/{projectId}/functions/{functionId}/executions/{executionId}` until `status` leaves `queued`/`running` to get the real result, error, and duration. 

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
opts = {
  execute_function_request: Mudbase::ExecuteFunctionRequest.new # ExecuteFunctionRequest | 
}

begin
  # Execute function
  result = api_instance.execute_function(project_id, function_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->execute_function: #{e}"
end
```

#### Using the execute_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionExecutionResponse>, Integer, Hash)> execute_function_with_http_info(project_id, function_id, opts)

```ruby
begin
  # Execute function
  data, status_code, headers = api_instance.execute_function_with_http_info(project_id, function_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionExecutionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->execute_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **execute_function_request** | [**ExecuteFunctionRequest**](ExecuteFunctionRequest.md) |  | [optional] |

### Return type

[**FunctionExecutionResponse**](FunctionExecutionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_function

> <FunctionResponse> get_function(project_id, function_id)

Get function

Get function details by ID including createdBy/updatedBy.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 

begin
  # Get function
  result = api_instance.get_function(project_id, function_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function: #{e}"
end
```

#### Using the get_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> get_function_with_http_info(project_id, function_id)

```ruby
begin
  # Get function
  data, status_code, headers = api_instance.get_function_with_http_info(project_id, function_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_function_execution

> <FunctionExecutionStatusResponse> get_function_execution(project_id, function_id, execution_id)

Get execution status

Poll this after Execute function or Simulate trigger to get the real outcome — both of those endpoints return 202 immediately and do not carry the result themselves. `status` is one of `queued`, `provisioning`, `running`, `success`, `failed`, `timeout`; `result`/`error`/`durationMs`/`logs` are only populated once `status` leaves `queued`/`running`. 

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
execution_id = 'execution_id_example' # String | 

begin
  # Get execution status
  result = api_instance.get_function_execution(project_id, function_id, execution_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_execution: #{e}"
end
```

#### Using the get_function_execution_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionExecutionStatusResponse>, Integer, Hash)> get_function_execution_with_http_info(project_id, function_id, execution_id)

```ruby
begin
  # Get execution status
  data, status_code, headers = api_instance.get_function_execution_with_http_info(project_id, function_id, execution_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionExecutionStatusResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_execution_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **execution_id** | **String** |  |  |

### Return type

[**FunctionExecutionStatusResponse**](FunctionExecutionStatusResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_function_logs

> <FunctionLogsResponse> get_function_logs(project_id, function_id, opts)

Get function execution logs

Get execution logs with pagination. Includes stats (totalExecutions, successful, failed, successRate, avgExecutionTime, lastRun).

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
opts = {
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # Get function execution logs
  result = api_instance.get_function_logs(project_id, function_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_logs: #{e}"
end
```

#### Using the get_function_logs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionLogsResponse>, Integer, Hash)> get_function_logs_with_http_info(project_id, function_id, opts)

```ruby
begin
  # Get function execution logs
  data, status_code, headers = api_instance.get_function_logs_with_http_info(project_id, function_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionLogsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_logs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**FunctionLogsResponse**](FunctionLogsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_function_versions

> <GetFunctionVersions200Response> get_function_versions(project_id, function_id)

Get function versions

List all code versions for a function. Used for rollback.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 

begin
  # Get function versions
  result = api_instance.get_function_versions(project_id, function_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_versions: #{e}"
end
```

#### Using the get_function_versions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetFunctionVersions200Response>, Integer, Hash)> get_function_versions_with_http_info(project_id, function_id)

```ruby
begin
  # Get function versions
  data, status_code, headers = api_instance.get_function_versions_with_http_info(project_id, function_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetFunctionVersions200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->get_function_versions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |

### Return type

[**GetFunctionVersions200Response**](GetFunctionVersions200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_functions

> <FunctionListResponse> list_functions(project_id, opts)

List functions

List serverless functions in a project with optional search and filters. Supports trigger types: http, event, document, file, webhook, cron, messaging. 

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  search: 'search_example', # String | Search by name or description
  trigger_type: 'http', # String | Filter by trigger type
  is_active: true # Boolean | Filter by active status (true/false)
}

begin
  # List functions
  result = api_instance.list_functions(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->list_functions: #{e}"
end
```

#### Using the list_functions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionListResponse>, Integer, Hash)> list_functions_with_http_info(project_id, opts)

```ruby
begin
  # List functions
  data, status_code, headers = api_instance.list_functions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->list_functions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **search** | **String** | Search by name or description | [optional] |
| **trigger_type** | **String** | Filter by trigger type | [optional] |
| **is_active** | **Boolean** | Filter by active status (true/false) | [optional] |

### Return type

[**FunctionListResponse**](FunctionListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## retry_function_execution

> <FunctionExecutionResponse> retry_function_execution(project_id, function_id, execution_index)

Retry failed execution

Retry a failed execution by its index (0-based) in the logs. Cannot retry successful executions.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
execution_index = 56 # Integer | 0-based index of the execution in logs

begin
  # Retry failed execution
  result = api_instance.retry_function_execution(project_id, function_id, execution_index)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->retry_function_execution: #{e}"
end
```

#### Using the retry_function_execution_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionExecutionResponse>, Integer, Hash)> retry_function_execution_with_http_info(project_id, function_id, execution_index)

```ruby
begin
  # Retry failed execution
  data, status_code, headers = api_instance.retry_function_execution_with_http_info(project_id, function_id, execution_index)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionExecutionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->retry_function_execution_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **execution_index** | **Integer** | 0-based index of the execution in logs |  |

### Return type

[**FunctionExecutionResponse**](FunctionExecutionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## rollback_function

> <FunctionResponse> rollback_function(project_id, function_id, rollback_function_request)

Rollback to previous version

Rollback function code to a previous version. Version number is required.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
rollback_function_request = Mudbase::RollbackFunctionRequest.new({version: 37}) # RollbackFunctionRequest | 

begin
  # Rollback to previous version
  result = api_instance.rollback_function(project_id, function_id, rollback_function_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->rollback_function: #{e}"
end
```

#### Using the rollback_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> rollback_function_with_http_info(project_id, function_id, rollback_function_request)

```ruby
begin
  # Rollback to previous version
  data, status_code, headers = api_instance.rollback_function_with_http_info(project_id, function_id, rollback_function_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->rollback_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **rollback_function_request** | [**RollbackFunctionRequest**](RollbackFunctionRequest.md) |  |  |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## simulate_function_trigger

> <FunctionExecutionResponse> simulate_function_trigger(project_id, function_id, opts)

Simulate trigger

Test a function with simulated trigger context. Use to verify document, file, webhook, or cron payloads. Executes the function with the provided eventContext merged into the payload.  Asynchronous, same pattern as Execute function: returns 202 immediately with an `executionId`. Poll `GET /api/functions/projects/{projectId}/functions/{functionId}/executions/{executionId}` for the real result. 

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
opts = {
  simulate_function_trigger_request: Mudbase::SimulateFunctionTriggerRequest.new # SimulateFunctionTriggerRequest | 
}

begin
  # Simulate trigger
  result = api_instance.simulate_function_trigger(project_id, function_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->simulate_function_trigger: #{e}"
end
```

#### Using the simulate_function_trigger_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionExecutionResponse>, Integer, Hash)> simulate_function_trigger_with_http_info(project_id, function_id, opts)

```ruby
begin
  # Simulate trigger
  data, status_code, headers = api_instance.simulate_function_trigger_with_http_info(project_id, function_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionExecutionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->simulate_function_trigger_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **simulate_function_trigger_request** | [**SimulateFunctionTriggerRequest**](SimulateFunctionTriggerRequest.md) |  | [optional] |

### Return type

[**FunctionExecutionResponse**](FunctionExecutionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## trigger_function_webhook

> <TriggerFunctionWebhook200Response> trigger_function_webhook(project_id, opts)

Trigger webhook functions

Public endpoint for external services to trigger functions with `trigger.type: webhook`. No authentication required. Optionally verify using `X-Webhook-Secret` header (configure per project or via FUNCTION_WEBHOOK_SECRET). Rate limited to 120 requests per 15 minutes per IP (per-org adjustable). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
opts = {
  x_webhook_secret: 'x_webhook_secret_example', # String | Optional webhook secret for verification
  body: { ... } # Object | 
}

begin
  # Trigger webhook functions
  result = api_instance.trigger_function_webhook(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->trigger_function_webhook: #{e}"
end
```

#### Using the trigger_function_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TriggerFunctionWebhook200Response>, Integer, Hash)> trigger_function_webhook_with_http_info(project_id, opts)

```ruby
begin
  # Trigger webhook functions
  data, status_code, headers = api_instance.trigger_function_webhook_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TriggerFunctionWebhook200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->trigger_function_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **x_webhook_secret** | **String** | Optional webhook secret for verification | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**TriggerFunctionWebhook200Response**](TriggerFunctionWebhook200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json, application/x-www-form-urlencoded, text/plain
- **Accept**: application/json


## update_function

> <FunctionResponse> update_function(project_id, function_id, opts)

Update function

Update function configuration. Code changes are versioned automatically.

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

api_instance = Mudbase::FunctionsApi.new
project_id = 'project_id_example' # String | 
function_id = 'function_id_example' # String | 
opts = {
  update_function_request: Mudbase::UpdateFunctionRequest.new # UpdateFunctionRequest | 
}

begin
  # Update function
  result = api_instance.update_function(project_id, function_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->update_function: #{e}"
end
```

#### Using the update_function_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FunctionResponse>, Integer, Hash)> update_function_with_http_info(project_id, function_id, opts)

```ruby
begin
  # Update function
  data, status_code, headers = api_instance.update_function_with_http_info(project_id, function_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FunctionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FunctionsApi->update_function_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **function_id** | **String** |  |  |
| **update_function_request** | [**UpdateFunctionRequest**](UpdateFunctionRequest.md) |  | [optional] |

### Return type

[**FunctionResponse**](FunctionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

