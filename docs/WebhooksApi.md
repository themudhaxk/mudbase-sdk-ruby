# Mudbase::WebhooksApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**configure_webhook**](WebhooksApi.md#configure_webhook) | **PUT** /api/webhooks/projects/{projectId}/config | Create or update project webhook |
| [**get_webhook_config**](WebhooksApi.md#get_webhook_config) | **GET** /api/webhooks/projects/{projectId}/config | Get project webhook configuration |
| [**get_webhook_stats**](WebhooksApi.md#get_webhook_stats) | **GET** /api/webhooks/stats | Get webhook delivery statistics |
| [**list_project_webhook_logs**](WebhooksApi.md#list_project_webhook_logs) | **GET** /api/webhooks/projects/{projectId} | List webhook delivery logs (project) |
| [**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /api/webhooks | List webhook delivery logs (organization) |
| [**retry_webhook**](WebhooksApi.md#retry_webhook) | **POST** /api/webhooks/retry/{webhookId} | Retry a failed webhook delivery |
| [**test_webhook_transformation**](WebhooksApi.md#test_webhook_transformation) | **POST** /api/webhooks/projects/{projectId}/test-transformation | Test webhook transformation |
| [**trigger_webhook**](WebhooksApi.md#trigger_webhook) | **POST** /api/webhooks/trigger | Manually trigger an outbound webhook |


## configure_webhook

> <ConfigureWebhook200Response> configure_webhook(project_id, opts)

Create or update project webhook

Set or update the project webhook URL and options. This is how you **add** or **create** a webhook for a project: provide **webhookUrl** to enable delivery; omit or set to null to disable. Optionally set **webhookSecret**, **webhookEvents**, **webhookVersion**, and **transformations**. Plan limits (webhooks per project) apply when adding a new URL. Requires ProjectBearerAuth (JWT) or ApiKeyAuth (X-API-Key) with project update access. 

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

api_instance = Mudbase::WebhooksApi.new
project_id = 'project_id_example' # String | 
opts = {
  configure_webhook_request: Mudbase::ConfigureWebhookRequest.new # ConfigureWebhookRequest | 
}

begin
  # Create or update project webhook
  result = api_instance.configure_webhook(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->configure_webhook: #{e}"
end
```

#### Using the configure_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConfigureWebhook200Response>, Integer, Hash)> configure_webhook_with_http_info(project_id, opts)

```ruby
begin
  # Create or update project webhook
  data, status_code, headers = api_instance.configure_webhook_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConfigureWebhook200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->configure_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **configure_webhook_request** | [**ConfigureWebhookRequest**](ConfigureWebhookRequest.md) |  | [optional] |

### Return type

[**ConfigureWebhook200Response**](ConfigureWebhook200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_webhook_config

> <GetWebhookConfig200Response> get_webhook_config(project_id)

Get project webhook configuration

Get the current webhook URL, events, version, and transformations for a project. This is **where Mudbase POSTs event payloads**; it does **not** return a `webhookId`. Delivery ids (`WebhookLog._id`) come from **`POST /api/webhooks/trigger`** or automatic deliveries, and from **list logs** endpoints.  Requires ProjectBearerAuth (JWT) or ApiKeyAuth (X-API-Key) with project read access. 

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

api_instance = Mudbase::WebhooksApi.new
project_id = 'project_id_example' # String | 

begin
  # Get project webhook configuration
  result = api_instance.get_webhook_config(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->get_webhook_config: #{e}"
end
```

#### Using the get_webhook_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetWebhookConfig200Response>, Integer, Hash)> get_webhook_config_with_http_info(project_id)

```ruby
begin
  # Get project webhook configuration
  data, status_code, headers = api_instance.get_webhook_config_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetWebhookConfig200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->get_webhook_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetWebhookConfig200Response**](GetWebhookConfig200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_webhook_stats

> <WebhookStatsResponse> get_webhook_stats(opts)

Get webhook delivery statistics

Aggregates **`WebhookLog`** rows for your organization over the last **`days`** (default 7). Optional **`projectId`** filters to a project in your org.  Returns **`statusStats`** (counts and average duration per delivery **status**) and **`eventStats`** (counts and success rate per **event** name).  **Auth:** Organization JWT only (`authRequired`). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::WebhooksApi.new
opts = {
  project_id: 'project_id_example', # String | Optional; limit stats to this project.
  days: 56 # Integer | 
}

begin
  # Get webhook delivery statistics
  result = api_instance.get_webhook_stats(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->get_webhook_stats: #{e}"
end
```

#### Using the get_webhook_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebhookStatsResponse>, Integer, Hash)> get_webhook_stats_with_http_info(opts)

```ruby
begin
  # Get webhook delivery statistics
  data, status_code, headers = api_instance.get_webhook_stats_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebhookStatsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->get_webhook_stats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** | Optional; limit stats to this project. | [optional] |
| **days** | **Integer** |  | [optional][default to 7] |

### Return type

[**WebhookStatsResponse**](WebhookStatsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_project_webhook_logs

> <WebhookListResponse> list_project_webhook_logs(project_id, opts)

List webhook delivery logs (project)

Same **`WebhookLog`** documents as **`GET /api/webhooks`**, scoped to **`projectId`** in the path. Accepts **org JWT**, **project JWT**, or **project API key** with project read access.  Each item’s **`_id`** is the id returned as **`webhookId`** from **`POST /api/webhooks/trigger`** and used in **`POST /api/webhooks/retry/{webhookId}`**. 

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

api_instance = Mudbase::WebhooksApi.new
project_id = 'project_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  status: 'pending', # String | 
  event: 'event_example' # String | 
}

begin
  # List webhook delivery logs (project)
  result = api_instance.list_project_webhook_logs(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->list_project_webhook_logs: #{e}"
end
```

#### Using the list_project_webhook_logs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebhookListResponse>, Integer, Hash)> list_project_webhook_logs_with_http_info(project_id, opts)

```ruby
begin
  # List webhook delivery logs (project)
  data, status_code, headers = api_instance.list_project_webhook_logs_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebhookListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->list_project_webhook_logs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **status** | **String** |  | [optional] |
| **event** | **String** |  | [optional] |

### Return type

[**WebhookListResponse**](WebhookListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_webhooks

> <WebhookListResponse> list_webhooks(opts)

List webhook delivery logs (organization)

Paginated **webhook delivery logs** for your organization (each row is one outbound HTTP attempt). Optional **`projectId`** query filters to a project that belongs to your org.  Use each log document’s **`_id`** (MongoDB ObjectId) as **`webhookId`** when calling **`POST /api/webhooks/retry/{webhookId}`** after a failed delivery. Organization **JWT only** (`OrgBearerAuth`); project API keys are not accepted on this route. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::WebhooksApi.new
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  status: 'pending', # String | 
  event: 'event_example', # String | 
  project_id: 'project_id_example' # String | Optional; restrict logs to this project (must belong to your org).
}

begin
  # List webhook delivery logs (organization)
  result = api_instance.list_webhooks(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks: #{e}"
end
```

#### Using the list_webhooks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebhookListResponse>, Integer, Hash)> list_webhooks_with_http_info(opts)

```ruby
begin
  # List webhook delivery logs (organization)
  data, status_code, headers = api_instance.list_webhooks_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebhookListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **status** | **String** |  | [optional] |
| **event** | **String** |  | [optional] |
| **project_id** | **String** | Optional; restrict logs to this project (must belong to your org). | [optional] |

### Return type

[**WebhookListResponse**](WebhookListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## retry_webhook

> <RetryWebhookResponse> retry_webhook(webhook_id)

Retry a failed webhook delivery

**`webhookId`** (path) = **`WebhookLog._id`** (MongoDB ObjectId)—the same value returned as **`webhookId`** from **`POST /api/webhooks/trigger`** and as **`_id`** on **`GET /api/webhooks`** / **`GET /api/webhooks/projects/{projectId}`**.  **Not** the string **`webhookId`** field stored on the log document (e.g. `manual-173…`); use the document **`_id`** for this path.  Resets a non-success log to **pending** and re-delivers. **400** if status is already **`success`**.  **Auth:** Organization JWT only; project API keys are not accepted. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::WebhooksApi.new
webhook_id = 'webhook_id_example' # String | WebhookLog document `_id` (delivery log id).

begin
  # Retry a failed webhook delivery
  result = api_instance.retry_webhook(webhook_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->retry_webhook: #{e}"
end
```

#### Using the retry_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RetryWebhookResponse>, Integer, Hash)> retry_webhook_with_http_info(webhook_id)

```ruby
begin
  # Retry a failed webhook delivery
  data, status_code, headers = api_instance.retry_webhook_with_http_info(webhook_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RetryWebhookResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->retry_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_id** | **String** | WebhookLog document &#x60;_id&#x60; (delivery log id). |  |

### Return type

[**RetryWebhookResponse**](RetryWebhookResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## test_webhook_transformation

> <TestWebhookTransformation200Response> test_webhook_transformation(project_id, test_webhook_transformation_request)

Test webhook transformation

Apply transformation rules to a sample payload and return original and transformed payloads. Requires ProjectBearerAuth (JWT) or ApiKeyAuth (X-API-Key) with project update access. 

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

api_instance = Mudbase::WebhooksApi.new
project_id = 'project_id_example' # String | 
test_webhook_transformation_request = Mudbase::TestWebhookTransformationRequest.new({payload: 3.56, transformations: [Mudbase::GetWebhookConfig200ResponseDataTransformationsInner.new]}) # TestWebhookTransformationRequest | 

begin
  # Test webhook transformation
  result = api_instance.test_webhook_transformation(project_id, test_webhook_transformation_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->test_webhook_transformation: #{e}"
end
```

#### Using the test_webhook_transformation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TestWebhookTransformation200Response>, Integer, Hash)> test_webhook_transformation_with_http_info(project_id, test_webhook_transformation_request)

```ruby
begin
  # Test webhook transformation
  data, status_code, headers = api_instance.test_webhook_transformation_with_http_info(project_id, test_webhook_transformation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TestWebhookTransformation200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->test_webhook_transformation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **test_webhook_transformation_request** | [**TestWebhookTransformationRequest**](TestWebhookTransformationRequest.md) |  |  |

### Return type

[**TestWebhookTransformation200Response**](TestWebhookTransformation200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## trigger_webhook

> <TriggerWebhookResponse> trigger_webhook(trigger_webhook_request)

Manually trigger an outbound webhook

Queues an HTTP delivery to **`url`** for **`projectId`** (must belong to your org). Creates a **`WebhookLog`** row, runs delivery, and returns the new log’s **`_id`**.  **Response field `webhookId`:** This is the **MongoDB `_id` of the delivery log** (same as the log’s **`_id`** in list endpoints). It is **not** part of the request body and is **not** the project `webhookSecret` from **`PUT .../config`**.  **Auth:** Org JWT, project JWT, or project API key with **project `update`** permission. 

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

api_instance = Mudbase::WebhooksApi.new
trigger_webhook_request = Mudbase::TriggerWebhookRequest.new({project_id: 'project_id_example', url: 'url_example', event: 'event_example', payload: 3.56}) # TriggerWebhookRequest | 

begin
  # Manually trigger an outbound webhook
  result = api_instance.trigger_webhook(trigger_webhook_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->trigger_webhook: #{e}"
end
```

#### Using the trigger_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TriggerWebhookResponse>, Integer, Hash)> trigger_webhook_with_http_info(trigger_webhook_request)

```ruby
begin
  # Manually trigger an outbound webhook
  data, status_code, headers = api_instance.trigger_webhook_with_http_info(trigger_webhook_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TriggerWebhookResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling WebhooksApi->trigger_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **trigger_webhook_request** | [**TriggerWebhookRequest**](TriggerWebhookRequest.md) |  |  |

### Return type

[**TriggerWebhookResponse**](TriggerWebhookResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

