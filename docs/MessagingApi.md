# Mudbase::MessagingApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_message_history**](MessagingApi.md#get_message_history) | **GET** /api/messaging/projects/{projectId}/messaging/history | Get message history |
| [**get_message_stats**](MessagingApi.md#get_message_stats) | **GET** /api/messaging/projects/{projectId}/messaging/stats | Get message statistics |
| [**get_project_fcm_config**](MessagingApi.md#get_project_fcm_config) | **GET** /api/messaging/projects/{projectId}/messaging/push-config | Get bring-your-own push credentials status (masked) |
| [**get_project_sms_byo**](MessagingApi.md#get_project_sms_byo) | **GET** /api/messaging/projects/{projectId}/messaging/sms-provider | Get BYO SMS provider configuration (masked) |
| [**get_project_vapid_public_key**](MessagingApi.md#get_project_vapid_public_key) | **GET** /api/messaging/projects/{projectId}/messaging/web-push/public-key | Get the Web Push public key (public) |
| [**get_project_web_push_config**](MessagingApi.md#get_project_web_push_config) | **GET** /api/messaging/projects/{projectId}/messaging/web-push-config | Get native Web Push (VAPID) configuration |
| [**list_device_tokens**](MessagingApi.md#list_device_tokens) | **GET** /api/messaging/projects/{projectId}/messaging/devices | List registered device tokens |
| [**list_web_push_subscriptions**](MessagingApi.md#list_web_push_subscriptions) | **GET** /api/messaging/projects/{projectId}/messaging/web-push/subscriptions | List registered Web Push subscriptions |
| [**patch_project_fcm_config**](MessagingApi.md#patch_project_fcm_config) | **PATCH** /api/messaging/projects/{projectId}/messaging/push-config | Set or clear your own push service account (optional) |
| [**patch_project_sms_byo**](MessagingApi.md#patch_project_sms_byo) | **PATCH** /api/messaging/projects/{projectId}/messaging/sms-provider | Update BYO SMS provider credentials |
| [**patch_project_web_push_config**](MessagingApi.md#patch_project_web_push_config) | **PATCH** /api/messaging/projects/{projectId}/messaging/web-push-config | Update native Web Push (VAPID) configuration |
| [**register_device_token**](MessagingApi.md#register_device_token) | **POST** /api/messaging/projects/{projectId}/messaging/devices | Register a device push token |
| [**register_web_push_subscription**](MessagingApi.md#register_web_push_subscription) | **POST** /api/messaging/projects/{projectId}/messaging/web-push/subscriptions | Register a browser Web Push subscription |
| [**remove_web_push_subscription**](MessagingApi.md#remove_web_push_subscription) | **DELETE** /api/messaging/projects/{projectId}/messaging/web-push/subscriptions | Unregister a Web Push subscription |
| [**send_email**](MessagingApi.md#send_email) | **POST** /api/messaging/projects/{projectId}/messaging/email | Send email |
| [**send_push_notification**](MessagingApi.md#send_push_notification) | **POST** /api/messaging/projects/{projectId}/messaging/push | Send push notification |
| [**send_sms**](MessagingApi.md#send_sms) | **POST** /api/messaging/projects/{projectId}/messaging/sms | Send SMS |
| [**unregister_device_token**](MessagingApi.md#unregister_device_token) | **DELETE** /api/messaging/projects/{projectId}/messaging/devices | Unregister a device push token |


## get_message_history

> <MessageHistoryResponse> get_message_history(project_id, opts)

Get message history

Get message history (push, email, SMS) with filtering and pagination. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
opts = {
  type: 'push', # String | 
  page: 56, # Integer | 
  limit: 56, # Integer | 
  status: 'sent' # String | 
}

begin
  # Get message history
  result = api_instance.get_message_history(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_message_history: #{e}"
end
```

#### Using the get_message_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageHistoryResponse>, Integer, Hash)> get_message_history_with_http_info(project_id, opts)

```ruby
begin
  # Get message history
  data, status_code, headers = api_instance.get_message_history_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageHistoryResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_message_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **type** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **status** | **String** |  | [optional] |

### Return type

[**MessageHistoryResponse**](MessageHistoryResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_message_stats

> <MessageStatsResponse> get_message_stats(project_id, opts)

Get message statistics

Get messaging statistics including total messages, success rates, and breakdown by type (push, email, SMS). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
opts = {
  start_date: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  end_date: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # Get message statistics
  result = api_instance.get_message_stats(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_message_stats: #{e}"
end
```

#### Using the get_message_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageStatsResponse>, Integer, Hash)> get_message_stats_with_http_info(project_id, opts)

```ruby
begin
  # Get message statistics
  data, status_code, headers = api_instance.get_message_stats_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageStatsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_message_stats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **start_date** | **Time** |  | [optional] |
| **end_date** | **Time** |  | [optional] |

### Return type

[**MessageStatsResponse**](MessageStatsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_fcm_config

> <GetProjectFcmConfig200Response> get_project_fcm_config(project_id)

Get bring-your-own push credentials status (masked)

Returns whether this project has its own push provider credentials stored (encrypted). This is an optional, advanced override - push works out of the box with platform-managed credentials, so when no per-project credentials are stored, push is sent with the platform-managed credentials.

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get bring-your-own push credentials status (masked)
  result = api_instance.get_project_fcm_config(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_fcm_config: #{e}"
end
```

#### Using the get_project_fcm_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectFcmConfig200Response>, Integer, Hash)> get_project_fcm_config_with_http_info(project_id)

```ruby
begin
  # Get bring-your-own push credentials status (masked)
  data, status_code, headers = api_instance.get_project_fcm_config_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectFcmConfig200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_fcm_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectFcmConfig200Response**](GetProjectFcmConfig200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_sms_byo

> <GetProjectSmsByo200Response> get_project_sms_byo(project_id)

Get BYO SMS provider configuration (masked)

Returns enabled flag, provider kind, default sender, and whether credentials are stored. Secrets are never returned. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get BYO SMS provider configuration (masked)
  result = api_instance.get_project_sms_byo(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_sms_byo: #{e}"
end
```

#### Using the get_project_sms_byo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectSmsByo200Response>, Integer, Hash)> get_project_sms_byo_with_http_info(project_id)

```ruby
begin
  # Get BYO SMS provider configuration (masked)
  data, status_code, headers = api_instance.get_project_sms_byo_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectSmsByo200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_sms_byo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectSmsByo200Response**](GetProjectSmsByo200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_vapid_public_key

> <WebPushPublicKeyResponse> get_project_vapid_public_key(project_id)

Get the Web Push public key (public)

Public read of the VAPID application-server public key a browser needs to subscribe with `pushManager.subscribe({ applicationServerKey })`. This is the one Web Push route that needs no authentication - the public key is designed to be exposed to browser clients. It returns only this project's own key.  When the project has not enabled native Web Push, `enabled` is `false` and `publicKey` is `null`. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get the Web Push public key (public)
  result = api_instance.get_project_vapid_public_key(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_vapid_public_key: #{e}"
end
```

#### Using the get_project_vapid_public_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushPublicKeyResponse>, Integer, Hash)> get_project_vapid_public_key_with_http_info(project_id)

```ruby
begin
  # Get the Web Push public key (public)
  data, status_code, headers = api_instance.get_project_vapid_public_key_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushPublicKeyResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_vapid_public_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**WebPushPublicKeyResponse**](WebPushPublicKeyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_web_push_config

> <WebPushConfigResponse> get_project_web_push_config(project_id)

Get native Web Push (VAPID) configuration

Read this project's native Web Push configuration. Native Web Push delivers browser push directly from Mudbase using the VAPID application-server key - no per-project push provider account is required. This returns whether native Web Push is enabled, whether a VAPID keypair has been provisioned, the public application-server key (when enabled), the RFC 8292 contact subject, and when the current keypair was generated. The private key is never returned.  Native Web Push is off until you enable it (`PATCH` this endpoint). It sits alongside the device-token push path - a project can use either or both.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get native Web Push (VAPID) configuration
  result = api_instance.get_project_web_push_config(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_web_push_config: #{e}"
end
```

#### Using the get_project_web_push_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushConfigResponse>, Integer, Hash)> get_project_web_push_config_with_http_info(project_id)

```ruby
begin
  # Get native Web Push (VAPID) configuration
  data, status_code, headers = api_instance.get_project_web_push_config_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushConfigResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->get_project_web_push_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**WebPushConfigResponse**](WebPushConfigResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_device_tokens

> <DeviceListResponse> list_device_tokens(project_id)

List registered device tokens

List the device push tokens registered to a project, most-recently-seen first.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # List registered device tokens
  result = api_instance.list_device_tokens(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->list_device_tokens: #{e}"
end
```

#### Using the list_device_tokens_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeviceListResponse>, Integer, Hash)> list_device_tokens_with_http_info(project_id)

```ruby
begin
  # List registered device tokens
  data, status_code, headers = api_instance.list_device_tokens_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeviceListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->list_device_tokens_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**DeviceListResponse**](DeviceListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_web_push_subscriptions

> <WebPushSubscriptionListResponse> list_web_push_subscriptions(project_id)

List registered Web Push subscriptions

List the browser Web Push subscriptions registered to a project, most-recently-seen first. The encryption keys are never returned - only the endpoint and metadata.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 

begin
  # List registered Web Push subscriptions
  result = api_instance.list_web_push_subscriptions(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->list_web_push_subscriptions: #{e}"
end
```

#### Using the list_web_push_subscriptions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushSubscriptionListResponse>, Integer, Hash)> list_web_push_subscriptions_with_http_info(project_id)

```ruby
begin
  # List registered Web Push subscriptions
  data, status_code, headers = api_instance.list_web_push_subscriptions_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushSubscriptionListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->list_web_push_subscriptions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**WebPushSubscriptionListResponse**](WebPushSubscriptionListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## patch_project_fcm_config

> patch_project_fcm_config(project_id, patch_project_fcm_config_request)

Set or clear your own push service account (optional)

Optional advanced step - push works out of the box with platform-managed credentials, so most projects never call this. Use it only to deliver push from your own push provider account. Body `serviceAccountJson` is the Firebase service account JSON you download from your own Firebase project (stored encrypted). Send `clear: true` to remove it and go back to the platform-managed credentials. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
patch_project_fcm_config_request = Mudbase::PatchProjectFcmConfigRequestOneOf.new({service_account_json: 3.56}) # PatchProjectFcmConfigRequest | 

begin
  # Set or clear your own push service account (optional)
  api_instance.patch_project_fcm_config(project_id, patch_project_fcm_config_request)
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_fcm_config: #{e}"
end
```

#### Using the patch_project_fcm_config_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> patch_project_fcm_config_with_http_info(project_id, patch_project_fcm_config_request)

```ruby
begin
  # Set or clear your own push service account (optional)
  data, status_code, headers = api_instance.patch_project_fcm_config_with_http_info(project_id, patch_project_fcm_config_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_fcm_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **patch_project_fcm_config_request** | [**PatchProjectFcmConfigRequest**](PatchProjectFcmConfigRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## patch_project_sms_byo

> <GetProjectSmsByo200Response> patch_project_sms_byo(project_id, project_sms_byo_patch_request)

Update BYO SMS provider credentials

Body `config` is provider-specific JSON stored encrypted per organization: - **twilio** — `accountSid`, `authToken` (required). Optional `from` sender override used if the send request does not specify `from` and `defaultFrom` is empty. - **termii** — `apiKey` (required). Optional `from` sender name (e.g. brand label). - **africastalking** — `username`, `apiKey` (both required). Optional `from` shortcode or sender ID. On enable, the API validates credentials with a lightweight ping (no SMS sent). See request body **Examples** for sample payloads. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
project_sms_byo_patch_request = Mudbase::ProjectSmsByoPatchRequest.new # ProjectSmsByoPatchRequest | 

begin
  # Update BYO SMS provider credentials
  result = api_instance.patch_project_sms_byo(project_id, project_sms_byo_patch_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_sms_byo: #{e}"
end
```

#### Using the patch_project_sms_byo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectSmsByo200Response>, Integer, Hash)> patch_project_sms_byo_with_http_info(project_id, project_sms_byo_patch_request)

```ruby
begin
  # Update BYO SMS provider credentials
  data, status_code, headers = api_instance.patch_project_sms_byo_with_http_info(project_id, project_sms_byo_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectSmsByo200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_sms_byo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **project_sms_byo_patch_request** | [**ProjectSmsByoPatchRequest**](ProjectSmsByoPatchRequest.md) |  |  |

### Return type

[**GetProjectSmsByo200Response**](GetProjectSmsByo200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## patch_project_web_push_config

> <WebPushConfigResponse> patch_project_web_push_config(project_id, web_push_config_patch_request)

Update native Web Push (VAPID) configuration

Enable or disable native Web Push, rotate the VAPID keypair, or set the contact subject.  - `enabled: true` turns native Web Push on and provisions a VAPID keypair the first time, so the public-key read path has a key to hand clients immediately. `enabled: false` turns it off. - `rotateKeys: true` regenerates the keypair. This invalidates existing browser subscriptions - clients must re-fetch the new public key and re-subscribe. - `subject` sets the RFC 8292 contact URI - a `mailto:` address or an `https` URL.  Returns the same shape as `GET`. The private key is never returned.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
web_push_config_patch_request = Mudbase::WebPushConfigPatchRequest.new # WebPushConfigPatchRequest | 

begin
  # Update native Web Push (VAPID) configuration
  result = api_instance.patch_project_web_push_config(project_id, web_push_config_patch_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_web_push_config: #{e}"
end
```

#### Using the patch_project_web_push_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushConfigResponse>, Integer, Hash)> patch_project_web_push_config_with_http_info(project_id, web_push_config_patch_request)

```ruby
begin
  # Update native Web Push (VAPID) configuration
  data, status_code, headers = api_instance.patch_project_web_push_config_with_http_info(project_id, web_push_config_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushConfigResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->patch_project_web_push_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **web_push_config_patch_request** | [**WebPushConfigPatchRequest**](WebPushConfigPatchRequest.md) |  |  |

### Return type

[**WebPushConfigResponse**](WebPushConfigResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## register_device_token

> <DeviceRegisteredResponse> register_device_token(project_id, device_register_request)

Register a device push token

Register a device's push token with a project so it can receive push notifications. A client registers its token here first; the send endpoint (`/messaging/push`) only delivers to tokens that are registered to the project, so a caller cannot push to arbitrary or other-tenant tokens.  Registration is idempotent - re-registering a token that already exists just refreshes it (updates `platform` and `lastSeenAt`) instead of creating a duplicate. Each project has a cap on the number of registered tokens; when the cap is reached, the least-recently-seen tokens are evicted to make room, so a register-on-launch call never fails.  Push works out of the box with platform-managed credentials - no provider setup is required to start registering tokens and sending push.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
device_register_request = Mudbase::DeviceRegisterRequest.new({token: 'token_example'}) # DeviceRegisterRequest | 

begin
  # Register a device push token
  result = api_instance.register_device_token(project_id, device_register_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->register_device_token: #{e}"
end
```

#### Using the register_device_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeviceRegisteredResponse>, Integer, Hash)> register_device_token_with_http_info(project_id, device_register_request)

```ruby
begin
  # Register a device push token
  data, status_code, headers = api_instance.register_device_token_with_http_info(project_id, device_register_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeviceRegisteredResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->register_device_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **device_register_request** | [**DeviceRegisterRequest**](DeviceRegisterRequest.md) |  |  |

### Return type

[**DeviceRegisteredResponse**](DeviceRegisteredResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## register_web_push_subscription

> <WebPushSubscribeResponse> register_web_push_subscription(project_id, web_push_subscribe_request)

Register a browser Web Push subscription

Register a browser `PushSubscription` (the `endpoint` plus the `p256dh` / `auth` keys returned by `pushManager.subscribe()`) so it becomes eligible to receive native Web Push. The send endpoint (`/messaging/push`) only delivers to subscriptions registered to the project, so a caller cannot push to arbitrary or other-tenant endpoints.  Registration is idempotent - re-registering the same endpoint updates the existing row (keys rotate, `lastSeenAt` bumps) instead of creating a duplicate. Each project has a cap on the number of registered subscriptions; when the cap is reached, the least-recently-seen subscriptions are evicted to make room. Optionally associate the subscription with a `userId` (your end-user id, for targeted sends) and a `deviceId`.  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
web_push_subscribe_request = Mudbase::WebPushSubscribeRequest.new({subscription: Mudbase::WebPushSubscription.new({endpoint: 'endpoint_example', keys: Mudbase::WebPushSubscriptionKeys.new({p256dh: 'p256dh_example', auth: 'auth_example'})})}) # WebPushSubscribeRequest | 

begin
  # Register a browser Web Push subscription
  result = api_instance.register_web_push_subscription(project_id, web_push_subscribe_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->register_web_push_subscription: #{e}"
end
```

#### Using the register_web_push_subscription_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushSubscribeResponse>, Integer, Hash)> register_web_push_subscription_with_http_info(project_id, web_push_subscribe_request)

```ruby
begin
  # Register a browser Web Push subscription
  data, status_code, headers = api_instance.register_web_push_subscription_with_http_info(project_id, web_push_subscribe_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushSubscribeResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->register_web_push_subscription_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **web_push_subscribe_request** | [**WebPushSubscribeRequest**](WebPushSubscribeRequest.md) |  |  |

### Return type

[**WebPushSubscribeResponse**](WebPushSubscribeResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_web_push_subscription

> <WebPushUnsubscribeResponse> remove_web_push_subscription(project_id, web_push_unsubscribe_request)

Unregister a Web Push subscription

Remove a browser Web Push subscription - call this on unsubscribe or logout, so the send endpoint stops delivering to it. The subscription is identified by its `endpoint`, sent in the request body. Removing an endpoint that is not registered is a no-op and still returns 200 (with `removed: false`).  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
web_push_unsubscribe_request = Mudbase::WebPushUnsubscribeRequest.new({endpoint: 'endpoint_example'}) # WebPushUnsubscribeRequest | 

begin
  # Unregister a Web Push subscription
  result = api_instance.remove_web_push_subscription(project_id, web_push_unsubscribe_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->remove_web_push_subscription: #{e}"
end
```

#### Using the remove_web_push_subscription_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebPushUnsubscribeResponse>, Integer, Hash)> remove_web_push_subscription_with_http_info(project_id, web_push_unsubscribe_request)

```ruby
begin
  # Unregister a Web Push subscription
  data, status_code, headers = api_instance.remove_web_push_subscription_with_http_info(project_id, web_push_unsubscribe_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebPushUnsubscribeResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->remove_web_push_subscription_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **web_push_unsubscribe_request** | [**WebPushUnsubscribeRequest**](WebPushUnsubscribeRequest.md) |  |  |

### Return type

[**WebPushUnsubscribeResponse**](WebPushUnsubscribeResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_email

> <MessageSentResponse> send_email(project_id, email_request)

Send email

Send an email message to one or more recipients. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
email_request = Mudbase::EmailRequest.new({to: nil, subject: 'subject_example'}) # EmailRequest | 

begin
  # Send email
  result = api_instance.send_email(project_id, email_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_email: #{e}"
end
```

#### Using the send_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageSentResponse>, Integer, Hash)> send_email_with_http_info(project_id, email_request)

```ruby
begin
  # Send email
  data, status_code, headers = api_instance.send_email_with_http_info(project_id, email_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageSentResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **email_request** | [**EmailRequest**](EmailRequest.md) |  |  |

### Return type

[**MessageSentResponse**](MessageSentResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_push_notification

> <PushSentResponse> send_push_notification(project_id, push_notification_request)

Send push notification

Send a push notification to one or more devices. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
push_notification_request = Mudbase::PushNotificationRequest.new({title: 'title_example', body: 'body_example'}) # PushNotificationRequest | 

begin
  # Send push notification
  result = api_instance.send_push_notification(project_id, push_notification_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_push_notification: #{e}"
end
```

#### Using the send_push_notification_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PushSentResponse>, Integer, Hash)> send_push_notification_with_http_info(project_id, push_notification_request)

```ruby
begin
  # Send push notification
  data, status_code, headers = api_instance.send_push_notification_with_http_info(project_id, push_notification_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PushSentResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_push_notification_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **push_notification_request** | [**PushNotificationRequest**](PushNotificationRequest.md) |  |  |

### Return type

[**PushSentResponse**](PushSentResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_sms

> <MessageSentResponse> send_sms(project_id, sms_request)

Send SMS

Send an SMS message to one or more phone numbers. Uses project BYO SMS when configured; otherwise the platform SMS provider if set. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
sms_request = Mudbase::SMSRequest.new({to: 'to_example', message: 'message_example'}) # SMSRequest | 

begin
  # Send SMS
  result = api_instance.send_sms(project_id, sms_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_sms: #{e}"
end
```

#### Using the send_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageSentResponse>, Integer, Hash)> send_sms_with_http_info(project_id, sms_request)

```ruby
begin
  # Send SMS
  data, status_code, headers = api_instance.send_sms_with_http_info(project_id, sms_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageSentResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->send_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **sms_request** | [**SMSRequest**](SMSRequest.md) |  |  |

### Return type

[**MessageSentResponse**](MessageSentResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## unregister_device_token

> <DeviceUnregisteredResponse> unregister_device_token(project_id, device_unregister_request)

Unregister a device push token

Remove a device push token from a project - call this on logout or when a token rotates, so the send endpoint stops delivering to it.  The token to remove is sent in the request body. Removing a token that is not registered is a no-op and still returns 200 (with `removed: false`).  Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). 

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

api_instance = Mudbase::MessagingApi.new
project_id = 'project_id_example' # String | 
device_unregister_request = Mudbase::DeviceUnregisterRequest.new({token: 'token_example'}) # DeviceUnregisterRequest | 

begin
  # Unregister a device push token
  result = api_instance.unregister_device_token(project_id, device_unregister_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->unregister_device_token: #{e}"
end
```

#### Using the unregister_device_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeviceUnregisteredResponse>, Integer, Hash)> unregister_device_token_with_http_info(project_id, device_unregister_request)

```ruby
begin
  # Unregister a device push token
  data, status_code, headers = api_instance.unregister_device_token_with_http_info(project_id, device_unregister_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeviceUnregisteredResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling MessagingApi->unregister_device_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **device_unregister_request** | [**DeviceUnregisterRequest**](DeviceUnregisterRequest.md) |  |  |

### Return type

[**DeviceUnregisteredResponse**](DeviceUnregisteredResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

