# Mudbase::AddOnsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**api_addons_get**](AddOnsApi.md#api_addons_get) | **GET** /api/addons | List the add-on catalog |
| [**api_projects_project_id_addons_addon_invoke_post**](AddOnsApi.md#api_projects_project_id_addons_addon_invoke_post) | **POST** /api/projects/{projectId}/addons/{addon}/invoke | Invoke an add-on for a project |
| [**api_projects_project_id_addons_jobs_id_get**](AddOnsApi.md#api_projects_project_id_addons_jobs_id_get) | **GET** /api/projects/{projectId}/addons/jobs/{id} | Get an add-on job status |


## api_addons_get

> <ApiAddonsGet200Response> api_addons_get

List the add-on catalog

Returns the available add-ons (key, metadata, pricing) the caller can invoke.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::AddOnsApi.new

begin
  # List the add-on catalog
  result = api_instance.api_addons_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_addons_get: #{e}"
end
```

#### Using the api_addons_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiAddonsGet200Response>, Integer, Hash)> api_addons_get_with_http_info

```ruby
begin
  # List the add-on catalog
  data, status_code, headers = api_instance.api_addons_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiAddonsGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_addons_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ApiAddonsGet200Response**](ApiAddonsGet200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## api_projects_project_id_addons_addon_invoke_post

> <ApiProjectsProjectIdAddonsAddonInvokePost200Response> api_projects_project_id_addons_addon_invoke_post(project_id, addon, opts)

Invoke an add-on for a project

Runs the named add-on against the project. Returns the job synchronously (200) when it completes immediately, or 202 with a pending job when processing continues in the background.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::AddOnsApi.new
project_id = 'project_id_example' # String | 
addon = 'addon_example' # String | Add-on key from the catalog.
opts = {
  body: { ... } # Object | 
}

begin
  # Invoke an add-on for a project
  result = api_instance.api_projects_project_id_addons_addon_invoke_post(project_id, addon, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_projects_project_id_addons_addon_invoke_post: #{e}"
end
```

#### Using the api_projects_project_id_addons_addon_invoke_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiProjectsProjectIdAddonsAddonInvokePost200Response>, Integer, Hash)> api_projects_project_id_addons_addon_invoke_post_with_http_info(project_id, addon, opts)

```ruby
begin
  # Invoke an add-on for a project
  data, status_code, headers = api_instance.api_projects_project_id_addons_addon_invoke_post_with_http_info(project_id, addon, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiProjectsProjectIdAddonsAddonInvokePost200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_projects_project_id_addons_addon_invoke_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **addon** | **String** | Add-on key from the catalog. |  |
| **body** | **Object** |  | [optional] |

### Return type

[**ApiProjectsProjectIdAddonsAddonInvokePost200Response**](ApiProjectsProjectIdAddonsAddonInvokePost200Response.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## api_projects_project_id_addons_jobs_id_get

> <ApiProjectsProjectIdAddonsAddonInvokePost200Response> api_projects_project_id_addons_jobs_id_get(project_id, id)

Get an add-on job status

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::AddOnsApi.new
project_id = 'project_id_example' # String | 
id = 'id_example' # String | Add-on job id.

begin
  # Get an add-on job status
  result = api_instance.api_projects_project_id_addons_jobs_id_get(project_id, id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_projects_project_id_addons_jobs_id_get: #{e}"
end
```

#### Using the api_projects_project_id_addons_jobs_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiProjectsProjectIdAddonsAddonInvokePost200Response>, Integer, Hash)> api_projects_project_id_addons_jobs_id_get_with_http_info(project_id, id)

```ruby
begin
  # Get an add-on job status
  data, status_code, headers = api_instance.api_projects_project_id_addons_jobs_id_get_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiProjectsProjectIdAddonsAddonInvokePost200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AddOnsApi->api_projects_project_id_addons_jobs_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **id** | **String** | Add-on job id. |  |

### Return type

[**ApiProjectsProjectIdAddonsAddonInvokePost200Response**](ApiProjectsProjectIdAddonsAddonInvokePost200Response.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

