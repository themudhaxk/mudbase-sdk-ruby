# Mudbase::KYCApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**api_kyc_events_get**](KYCApi.md#api_kyc_events_get) | **GET** /api/kyc/events | List recent compliance webhook deliveries |
| [**api_kyc_sessions_post**](KYCApi.md#api_kyc_sessions_post) | **POST** /api/kyc/sessions | Start a platform KYC session |
| [**api_kyc_status_get**](KYCApi.md#api_kyc_status_get) | **GET** /api/kyc/status | Get the organization&#39;s platform KYC status |
| [**api_kyc_verifications_id_get**](KYCApi.md#api_kyc_verifications_id_get) | **GET** /api/kyc/verifications/{id} | Get a single KYC verification record |
| [**api_kyc_webhook_config_get**](KYCApi.md#api_kyc_webhook_config_get) | **GET** /api/kyc/webhook-config | Get white-label KYC webhook config |
| [**api_kyc_webhook_config_put**](KYCApi.md#api_kyc_webhook_config_put) | **PUT** /api/kyc/webhook-config | Set white-label KYC webhook config |
| [**api_kyc_webhook_config_test_post**](KYCApi.md#api_kyc_webhook_config_test_post) | **POST** /api/kyc/webhook-config/test | Send a signed test event to the configured webhook endpoint |
| [**api_kyc_workflows_get**](KYCApi.md#api_kyc_workflows_get) | **GET** /api/kyc/workflows | List available verification workflows |
| [**api_projects_project_id_kyb_sessions_post**](KYCApi.md#api_projects_project_id_kyb_sessions_post) | **POST** /api/projects/{projectId}/kyb/sessions | Start a business verification (KYB) session for one of your business customers |


## api_kyc_events_get

> api_kyc_events_get(opts)

List recent compliance webhook deliveries

Audit trail of compliance webhook events received for this organization and whether Mudbase forwarded each one to the organization's own endpoint. Owner, admin, and developer roles.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new
opts = {
  limit: 56 # Integer | Maximum number of events to return.
}

begin
  # List recent compliance webhook deliveries
  api_instance.api_kyc_events_get(opts)
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_events_get: #{e}"
end
```

#### Using the api_kyc_events_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_kyc_events_get_with_http_info(opts)

```ruby
begin
  # List recent compliance webhook deliveries
  data, status_code, headers = api_instance.api_kyc_events_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_events_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** | Maximum number of events to return. | [optional][default to 25] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## api_kyc_sessions_post

> api_kyc_sessions_post(opts)

Start a platform KYC session

Creates a verification session for the caller's organization. Owner/admin only.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new
opts = {
  api_kyc_sessions_post_request: Mudbase::ApiKycSessionsPostRequest.new # ApiKycSessionsPostRequest | 
}

begin
  # Start a platform KYC session
  api_instance.api_kyc_sessions_post(opts)
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_sessions_post: #{e}"
end
```

#### Using the api_kyc_sessions_post_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_kyc_sessions_post_with_http_info(opts)

```ruby
begin
  # Start a platform KYC session
  data, status_code, headers = api_instance.api_kyc_sessions_post_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_sessions_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_kyc_sessions_post_request** | [**ApiKycSessionsPostRequest**](ApiKycSessionsPostRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## api_kyc_status_get

> api_kyc_status_get

Get the organization's platform KYC status

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new

begin
  # Get the organization's platform KYC status
  api_instance.api_kyc_status_get
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_status_get: #{e}"
end
```

#### Using the api_kyc_status_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_kyc_status_get_with_http_info

```ruby
begin
  # Get the organization's platform KYC status
  data, status_code, headers = api_instance.api_kyc_status_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_status_get_with_http_info: #{e}"
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
- **Accept**: Not defined


## api_kyc_verifications_id_get

> api_kyc_verifications_id_get(id)

Get a single KYC verification record

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new
id = 'id_example' # String | Verification record id.

begin
  # Get a single KYC verification record
  api_instance.api_kyc_verifications_id_get(id)
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_verifications_id_get: #{e}"
end
```

#### Using the api_kyc_verifications_id_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_kyc_verifications_id_get_with_http_info(id)

```ruby
begin
  # Get a single KYC verification record
  data, status_code, headers = api_instance.api_kyc_verifications_id_get_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_verifications_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Verification record id. |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## api_kyc_webhook_config_get

> <ApiKycWebhookConfigGet200Response> api_kyc_webhook_config_get

Get white-label KYC webhook config

Returns the destination URL where the organization's own system receives KYC results and whether a signing secret is set. The secret value itself is never returned. Owner/admin only.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new

begin
  # Get white-label KYC webhook config
  result = api_instance.api_kyc_webhook_config_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_get: #{e}"
end
```

#### Using the api_kyc_webhook_config_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiKycWebhookConfigGet200Response>, Integer, Hash)> api_kyc_webhook_config_get_with_http_info

```ruby
begin
  # Get white-label KYC webhook config
  data, status_code, headers = api_instance.api_kyc_webhook_config_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiKycWebhookConfigGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ApiKycWebhookConfigGet200Response**](ApiKycWebhookConfigGet200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## api_kyc_webhook_config_put

> <ApiKycWebhookConfigPut200Response> api_kyc_webhook_config_put(opts)

Set white-label KYC webhook config

Updates the destination URL and/or signing secret used to deliver KYC results to the organization's own system. The outbound URL is SSRF-validated. When generateSecret is true a new secret is created and returned once. Owner/admin only.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new
opts = {
  api_kyc_webhook_config_put_request: Mudbase::ApiKycWebhookConfigPutRequest.new # ApiKycWebhookConfigPutRequest | 
}

begin
  # Set white-label KYC webhook config
  result = api_instance.api_kyc_webhook_config_put(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_put: #{e}"
end
```

#### Using the api_kyc_webhook_config_put_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiKycWebhookConfigPut200Response>, Integer, Hash)> api_kyc_webhook_config_put_with_http_info(opts)

```ruby
begin
  # Set white-label KYC webhook config
  data, status_code, headers = api_instance.api_kyc_webhook_config_put_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiKycWebhookConfigPut200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_put_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_kyc_webhook_config_put_request** | [**ApiKycWebhookConfigPutRequest**](ApiKycWebhookConfigPutRequest.md) |  | [optional] |

### Return type

[**ApiKycWebhookConfigPut200Response**](ApiKycWebhookConfigPut200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## api_kyc_webhook_config_test_post

> <ApiKycWebhookConfigTestPost200Response> api_kyc_webhook_config_test_post

Send a signed test event to the configured webhook endpoint

Delivers a sample `kyc.test` payload, signed exactly like a real event, so you can confirm your receiver and signature verification work. Ignores your event subscription. Owner/admin only.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new

begin
  # Send a signed test event to the configured webhook endpoint
  result = api_instance.api_kyc_webhook_config_test_post
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_test_post: #{e}"
end
```

#### Using the api_kyc_webhook_config_test_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiKycWebhookConfigTestPost200Response>, Integer, Hash)> api_kyc_webhook_config_test_post_with_http_info

```ruby
begin
  # Send a signed test event to the configured webhook endpoint
  data, status_code, headers = api_instance.api_kyc_webhook_config_test_post_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiKycWebhookConfigTestPost200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_webhook_config_test_post_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ApiKycWebhookConfigTestPost200Response**](ApiKycWebhookConfigTestPost200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## api_kyc_workflows_get

> <ApiKycWorkflowsGet200Response> api_kyc_workflows_get

List available verification workflows

Returns the verification workflows configured on this Mudbase account, split into kyc (individual identity) and kyb (business verification). Used to choose a default workflow in the console instead of pasting a workflow UUID. Owner/admin only.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new

begin
  # List available verification workflows
  result = api_instance.api_kyc_workflows_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_workflows_get: #{e}"
end
```

#### Using the api_kyc_workflows_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiKycWorkflowsGet200Response>, Integer, Hash)> api_kyc_workflows_get_with_http_info

```ruby
begin
  # List available verification workflows
  data, status_code, headers = api_instance.api_kyc_workflows_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiKycWorkflowsGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_kyc_workflows_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ApiKycWorkflowsGet200Response**](ApiKycWorkflowsGet200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## api_projects_project_id_kyb_sessions_post

> api_projects_project_id_kyb_sessions_post(project_id, opts)

Start a business verification (KYB) session for one of your business customers

Creates a KYB session scoped to your project. The workflow is resolved from the request, then the organization's configured default KYB workflow, then the platform default. Results arrive at your configured KYC webhook as `kyb.completed`.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::KYCApi.new
project_id = 'project_id_example' # String | 
opts = {
  api_projects_project_id_kyb_sessions_post_request: Mudbase::ApiProjectsProjectIdKybSessionsPostRequest.new # ApiProjectsProjectIdKybSessionsPostRequest | 
}

begin
  # Start a business verification (KYB) session for one of your business customers
  api_instance.api_projects_project_id_kyb_sessions_post(project_id, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_projects_project_id_kyb_sessions_post: #{e}"
end
```

#### Using the api_projects_project_id_kyb_sessions_post_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_projects_project_id_kyb_sessions_post_with_http_info(project_id, opts)

```ruby
begin
  # Start a business verification (KYB) session for one of your business customers
  data, status_code, headers = api_instance.api_projects_project_id_kyb_sessions_post_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling KYCApi->api_projects_project_id_kyb_sessions_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **api_projects_project_id_kyb_sessions_post_request** | [**ApiProjectsProjectIdKybSessionsPostRequest**](ApiProjectsProjectIdKybSessionsPostRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined

