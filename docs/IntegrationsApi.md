# Mudbase::IntegrationsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_from_template**](IntegrationsApi.md#create_from_template) | **POST** /api/integrations/projects/{projectId}/integrations/from-template | Create integration from template |
| [**create_integration**](IntegrationsApi.md#create_integration) | **POST** /api/integrations/projects/{projectId}/integrations | Create new integration |
| [**delete_integration**](IntegrationsApi.md#delete_integration) | **DELETE** /api/integrations/projects/{projectId}/integrations/{integrationId} | Delete integration |
| [**execute_integration**](IntegrationsApi.md#execute_integration) | **POST** /api/integrations/projects/{projectId}/integrations/{integrationId}/execute | Execute integration |
| [**export_integration**](IntegrationsApi.md#export_integration) | **GET** /api/integrations/projects/{projectId}/integrations/{integrationId}/export | Export integration |
| [**get_integration**](IntegrationsApi.md#get_integration) | **GET** /api/integrations/projects/{projectId}/integrations/{integrationId} | Get integration details |
| [**get_integrations**](IntegrationsApi.md#get_integrations) | **GET** /api/integrations/projects/{projectId}/integrations | Get project integrations |
| [**get_templates**](IntegrationsApi.md#get_templates) | **GET** /api/integrations/templates | Get integration templates |
| [**get_usage_stats**](IntegrationsApi.md#get_usage_stats) | **GET** /api/integrations/projects/{projectId}/integrations/{integrationId}/usage | Get integration usage statistics |
| [**import_integration**](IntegrationsApi.md#import_integration) | **POST** /api/integrations/projects/{projectId}/integrations/import | Import integration |
| [**test_integration**](IntegrationsApi.md#test_integration) | **POST** /api/integrations/projects/{projectId}/integrations/{integrationId}/test | Test integration |
| [**update_integration**](IntegrationsApi.md#update_integration) | **PATCH** /api/integrations/projects/{projectId}/integrations/{integrationId} | Update integration |


## create_from_template

> <CreateIntegration201Response> create_from_template(project_id, create_from_template_request)

Create integration from template

Create a new integration using a pre-configured template. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
create_from_template_request = Mudbase::CreateFromTemplateRequest.new({template_id: 'template_id_example', credentials: 3.56}) # CreateFromTemplateRequest | 

begin
  # Create integration from template
  result = api_instance.create_from_template(project_id, create_from_template_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->create_from_template: #{e}"
end
```

#### Using the create_from_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateIntegration201Response>, Integer, Hash)> create_from_template_with_http_info(project_id, create_from_template_request)

```ruby
begin
  # Create integration from template
  data, status_code, headers = api_instance.create_from_template_with_http_info(project_id, create_from_template_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateIntegration201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->create_from_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_from_template_request** | [**CreateFromTemplateRequest**](CreateFromTemplateRequest.md) |  |  |

### Return type

[**CreateIntegration201Response**](CreateIntegration201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_integration

> <CreateIntegration201Response> create_integration(project_id, create_integration_request)

Create new integration

Create a new third-party service integration for a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
create_integration_request = Mudbase::CreateIntegrationRequest.new({name: 'name_example', provider: 'provider_example', config: 3.56}) # CreateIntegrationRequest | 

begin
  # Create new integration
  result = api_instance.create_integration(project_id, create_integration_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->create_integration: #{e}"
end
```

#### Using the create_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateIntegration201Response>, Integer, Hash)> create_integration_with_http_info(project_id, create_integration_request)

```ruby
begin
  # Create new integration
  data, status_code, headers = api_instance.create_integration_with_http_info(project_id, create_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateIntegration201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->create_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_integration_request** | [**CreateIntegrationRequest**](CreateIntegrationRequest.md) |  |  |

### Return type

[**CreateIntegration201Response**](CreateIntegration201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_integration

> <MessageResponse> delete_integration(project_id, integration_id)

Delete integration

Delete an integration from a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 

begin
  # Delete integration
  result = api_instance.delete_integration(project_id, integration_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->delete_integration: #{e}"
end
```

#### Using the delete_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_integration_with_http_info(project_id, integration_id)

```ruby
begin
  # Delete integration
  data, status_code, headers = api_instance.delete_integration_with_http_info(project_id, integration_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->delete_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## execute_integration

> <TestIntegration200Response> execute_integration(project_id, integration_id, execute_integration_request)

Execute integration

Execute an integration action (API call) with specified endpoint and parameters. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 
execute_integration_request = Mudbase::ExecuteIntegrationRequest.new({endpoint: 'endpoint_example', method: 'GET'}) # ExecuteIntegrationRequest | 

begin
  # Execute integration
  result = api_instance.execute_integration(project_id, integration_id, execute_integration_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->execute_integration: #{e}"
end
```

#### Using the execute_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TestIntegration200Response>, Integer, Hash)> execute_integration_with_http_info(project_id, integration_id, execute_integration_request)

```ruby
begin
  # Execute integration
  data, status_code, headers = api_instance.execute_integration_with_http_info(project_id, integration_id, execute_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TestIntegration200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->execute_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |
| **execute_integration_request** | [**ExecuteIntegrationRequest**](ExecuteIntegrationRequest.md) |  |  |

### Return type

[**TestIntegration200Response**](TestIntegration200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_integration

> <CreateIntegration201Response> export_integration(project_id, integration_id)

Export integration

Export integration configuration for backup or migration. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 

begin
  # Export integration
  result = api_instance.export_integration(project_id, integration_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->export_integration: #{e}"
end
```

#### Using the export_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateIntegration201Response>, Integer, Hash)> export_integration_with_http_info(project_id, integration_id)

```ruby
begin
  # Export integration
  data, status_code, headers = api_instance.export_integration_with_http_info(project_id, integration_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateIntegration201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->export_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |

### Return type

[**CreateIntegration201Response**](CreateIntegration201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_integration

> <GetIntegration200Response> get_integration(project_id, integration_id)

Get integration details

Get details of a specific integration. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 

begin
  # Get integration details
  result = api_instance.get_integration(project_id, integration_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_integration: #{e}"
end
```

#### Using the get_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetIntegration200Response>, Integer, Hash)> get_integration_with_http_info(project_id, integration_id)

```ruby
begin
  # Get integration details
  data, status_code, headers = api_instance.get_integration_with_http_info(project_id, integration_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetIntegration200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |

### Return type

[**GetIntegration200Response**](GetIntegration200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_integrations

> <GetIntegrations200Response> get_integrations(project_id)

Get project integrations

List all integrations configured for a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 

begin
  # Get project integrations
  result = api_instance.get_integrations(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_integrations: #{e}"
end
```

#### Using the get_integrations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetIntegrations200Response>, Integer, Hash)> get_integrations_with_http_info(project_id)

```ruby
begin
  # Get project integrations
  data, status_code, headers = api_instance.get_integrations_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetIntegrations200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_integrations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetIntegrations200Response**](GetIntegrations200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_templates

> <GetTemplates200Response> get_templates

Get integration templates

Get available integration templates for third-party service connections. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new

begin
  # Get integration templates
  result = api_instance.get_templates
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_templates: #{e}"
end
```

#### Using the get_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetTemplates200Response>, Integer, Hash)> get_templates_with_http_info

```ruby
begin
  # Get integration templates
  data, status_code, headers = api_instance.get_templates_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetTemplates200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_templates_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetTemplates200Response**](GetTemplates200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_usage_stats

> <GetUsageStats200Response> get_usage_stats(project_id, integration_id, opts)

Get integration usage statistics

Get usage statistics for an integration (total calls, success/failure rates). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 
opts = {
  period: 'day' # String | 
}

begin
  # Get integration usage statistics
  result = api_instance.get_usage_stats(project_id, integration_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_usage_stats: #{e}"
end
```

#### Using the get_usage_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUsageStats200Response>, Integer, Hash)> get_usage_stats_with_http_info(project_id, integration_id, opts)

```ruby
begin
  # Get integration usage statistics
  data, status_code, headers = api_instance.get_usage_stats_with_http_info(project_id, integration_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUsageStats200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->get_usage_stats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |
| **period** | **String** |  | [optional][default to &#39;month&#39;] |

### Return type

[**GetUsageStats200Response**](GetUsageStats200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## import_integration

> <CreateIntegration201Response> import_integration(project_id, import_integration_request)

Import integration

Import an integration configuration from exported data. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
import_integration_request = Mudbase::ImportIntegrationRequest.new({integration_data: 3.56}) # ImportIntegrationRequest | 

begin
  # Import integration
  result = api_instance.import_integration(project_id, import_integration_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->import_integration: #{e}"
end
```

#### Using the import_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateIntegration201Response>, Integer, Hash)> import_integration_with_http_info(project_id, import_integration_request)

```ruby
begin
  # Import integration
  data, status_code, headers = api_instance.import_integration_with_http_info(project_id, import_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateIntegration201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->import_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **import_integration_request** | [**ImportIntegrationRequest**](ImportIntegrationRequest.md) |  |  |

### Return type

[**CreateIntegration201Response**](CreateIntegration201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## test_integration

> <TestIntegration200Response> test_integration(project_id, integration_id, test_integration_request)

Test integration

Test an integration connection and configuration. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 
test_integration_request = Mudbase::TestIntegrationRequest.new # TestIntegrationRequest | 

begin
  # Test integration
  result = api_instance.test_integration(project_id, integration_id, test_integration_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->test_integration: #{e}"
end
```

#### Using the test_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TestIntegration200Response>, Integer, Hash)> test_integration_with_http_info(project_id, integration_id, test_integration_request)

```ruby
begin
  # Test integration
  data, status_code, headers = api_instance.test_integration_with_http_info(project_id, integration_id, test_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TestIntegration200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->test_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |
| **test_integration_request** | [**TestIntegrationRequest**](TestIntegrationRequest.md) |  |  |

### Return type

[**TestIntegration200Response**](TestIntegration200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_integration

> <CreateIntegration201Response> update_integration(project_id, integration_id, update_integration_request)

Update integration

Update integration configuration (name, config, credentials). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::IntegrationsApi.new
project_id = 'project_id_example' # String | 
integration_id = 'integration_id_example' # String | 
update_integration_request = Mudbase::UpdateIntegrationRequest.new # UpdateIntegrationRequest | 

begin
  # Update integration
  result = api_instance.update_integration(project_id, integration_id, update_integration_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->update_integration: #{e}"
end
```

#### Using the update_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateIntegration201Response>, Integer, Hash)> update_integration_with_http_info(project_id, integration_id, update_integration_request)

```ruby
begin
  # Update integration
  data, status_code, headers = api_instance.update_integration_with_http_info(project_id, integration_id, update_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateIntegration201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling IntegrationsApi->update_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **integration_id** | **String** |  |  |
| **update_integration_request** | [**UpdateIntegrationRequest**](UpdateIntegrationRequest.md) |  |  |

### Return type

[**CreateIntegration201Response**](CreateIntegration201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

