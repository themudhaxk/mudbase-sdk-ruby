# Mudbase::ProjectFeesApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**confirm_address_verification**](ProjectFeesApi.md#confirm_address_verification) | **POST** /api/projects/{projectId}/fee-settings/{currency}/confirm-verification | ~~Confirm address verification~~ (deprecated) |
| [**create_or_update_fee_settings**](ProjectFeesApi.md#create_or_update_fee_settings) | **POST** /api/projects/{projectId}/fee-settings | ~~Create or update project fee settings~~ (deprecated) |
| [**get_currency_fee_balance**](ProjectFeesApi.md#get_currency_fee_balance) | **GET** /api/projects/{projectId}/fee-balances/{currency} | ~~Get currency fee balance~~ (deprecated) |
| [**get_fee_balances**](ProjectFeesApi.md#get_fee_balances) | **GET** /api/projects/{projectId}/fee-balances | ~~Get all fee balances~~ (deprecated) |
| [**get_fee_settings**](ProjectFeesApi.md#get_fee_settings) | **GET** /api/projects/{projectId}/fee-settings | ~~Get project fee settings~~ (deprecated) |
| [**get_payout_history**](ProjectFeesApi.md#get_payout_history) | **GET** /api/projects/{projectId}/payout-history | ~~Get payout history~~ (deprecated) |
| [**get_project_fee_dashboard**](ProjectFeesApi.md#get_project_fee_dashboard) | **GET** /api/projects/{projectId}/fee-dashboard | ~~Get fee dashboard~~ (deprecated) |
| [**initiate_address_verification**](ProjectFeesApi.md#initiate_address_verification) | **POST** /api/projects/{projectId}/fee-settings/{currency}/verify-address | ~~Initiate address verification~~ (deprecated) |
| [**request_manual_payout**](ProjectFeesApi.md#request_manual_payout) | **POST** /api/projects/{projectId}/payouts/request-manual | ~~Request manual payout~~ (deprecated) |
| [**update_currency_fee_settings**](ProjectFeesApi.md#update_currency_fee_settings) | **PATCH** /api/projects/{projectId}/fee-settings/{currency} | ~~Update currency fee settings~~ (deprecated) |


## confirm_address_verification

> <ConfirmAddressVerification200Response> confirm_address_verification(project_id, currency, confirm_address_verification_request)

~~Confirm address verification~~ (deprecated)

Confirm address verification by providing the transaction hash of the test transaction sent to the payout address. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
currency = 'currency_example' # String | 
confirm_address_verification_request = Mudbase::ConfirmAddressVerificationRequest.new({tx_hash: 'tx_hash_example'}) # ConfirmAddressVerificationRequest | 

begin
  # ~~Confirm address verification~~ (deprecated)
  result = api_instance.confirm_address_verification(project_id, currency, confirm_address_verification_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->confirm_address_verification: #{e}"
end
```

#### Using the confirm_address_verification_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConfirmAddressVerification200Response>, Integer, Hash)> confirm_address_verification_with_http_info(project_id, currency, confirm_address_verification_request)

```ruby
begin
  # ~~Confirm address verification~~ (deprecated)
  data, status_code, headers = api_instance.confirm_address_verification_with_http_info(project_id, currency, confirm_address_verification_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConfirmAddressVerification200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->confirm_address_verification_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **currency** | **String** |  |  |
| **confirm_address_verification_request** | [**ConfirmAddressVerificationRequest**](ConfirmAddressVerificationRequest.md) |  |  |

### Return type

[**ConfirmAddressVerification200Response**](ConfirmAddressVerification200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_or_update_fee_settings

> <ApplyRoleFeaturePreset200Response> create_or_update_fee_settings(project_id, create_or_update_fee_settings_request)

~~Create or update project fee settings~~ (deprecated)

Create or update fee settings for a project. Configure transaction fees, payout addresses, and thresholds for supported cryptocurrencies. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
create_or_update_fee_settings_request = Mudbase::CreateOrUpdateFeeSettingsRequest.new({currency: 'BTC'}) # CreateOrUpdateFeeSettingsRequest | 

begin
  # ~~Create or update project fee settings~~ (deprecated)
  result = api_instance.create_or_update_fee_settings(project_id, create_or_update_fee_settings_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->create_or_update_fee_settings: #{e}"
end
```

#### Using the create_or_update_fee_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> create_or_update_fee_settings_with_http_info(project_id, create_or_update_fee_settings_request)

```ruby
begin
  # ~~Create or update project fee settings~~ (deprecated)
  data, status_code, headers = api_instance.create_or_update_fee_settings_with_http_info(project_id, create_or_update_fee_settings_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->create_or_update_fee_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_or_update_fee_settings_request** | [**CreateOrUpdateFeeSettingsRequest**](CreateOrUpdateFeeSettingsRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_currency_fee_balance

> <GetCurrencyFeeBalance200Response> get_currency_fee_balance(project_id, currency)

~~Get currency fee balance~~ (deprecated)

Get fee balance for a specific cryptocurrency in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
currency = 'currency_example' # String | 

begin
  # ~~Get currency fee balance~~ (deprecated)
  result = api_instance.get_currency_fee_balance(project_id, currency)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_currency_fee_balance: #{e}"
end
```

#### Using the get_currency_fee_balance_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetCurrencyFeeBalance200Response>, Integer, Hash)> get_currency_fee_balance_with_http_info(project_id, currency)

```ruby
begin
  # ~~Get currency fee balance~~ (deprecated)
  data, status_code, headers = api_instance.get_currency_fee_balance_with_http_info(project_id, currency)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetCurrencyFeeBalance200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_currency_fee_balance_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **currency** | **String** |  |  |

### Return type

[**GetCurrencyFeeBalance200Response**](GetCurrencyFeeBalance200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_fee_balances

> <GetFeeBalances200Response> get_fee_balances(project_id)

~~Get all fee balances~~ (deprecated)

Get fee balances for all currencies in a project, including collected amounts, thresholds, and payout status. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 

begin
  # ~~Get all fee balances~~ (deprecated)
  result = api_instance.get_fee_balances(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_fee_balances: #{e}"
end
```

#### Using the get_fee_balances_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetFeeBalances200Response>, Integer, Hash)> get_fee_balances_with_http_info(project_id)

```ruby
begin
  # ~~Get all fee balances~~ (deprecated)
  data, status_code, headers = api_instance.get_fee_balances_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetFeeBalances200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_fee_balances_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetFeeBalances200Response**](GetFeeBalances200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_fee_settings

> <TestIntegration200Response> get_fee_settings(project_id)

~~Get project fee settings~~ (deprecated)

Get all fee settings configured for a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 

begin
  # ~~Get project fee settings~~ (deprecated)
  result = api_instance.get_fee_settings(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_fee_settings: #{e}"
end
```

#### Using the get_fee_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TestIntegration200Response>, Integer, Hash)> get_fee_settings_with_http_info(project_id)

```ruby
begin
  # ~~Get project fee settings~~ (deprecated)
  data, status_code, headers = api_instance.get_fee_settings_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TestIntegration200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_fee_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**TestIntegration200Response**](TestIntegration200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_payout_history

> <GetPayoutHistory200Response> get_payout_history(project_id, opts)

~~Get payout history~~ (deprecated)

Get historical payout records for a project with pagination. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
opts = {
  limit: 56, # Integer | 
  page: 56, # Integer | 
  currency: 'currency_example', # String | 
  status: 'scheduled' # String | 
}

begin
  # ~~Get payout history~~ (deprecated)
  result = api_instance.get_payout_history(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_payout_history: #{e}"
end
```

#### Using the get_payout_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPayoutHistory200Response>, Integer, Hash)> get_payout_history_with_http_info(project_id, opts)

```ruby
begin
  # ~~Get payout history~~ (deprecated)
  data, status_code, headers = api_instance.get_payout_history_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPayoutHistory200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_payout_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **limit** | **Integer** |  | [optional][default to 20] |
| **page** | **Integer** |  | [optional][default to 1] |
| **currency** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |

### Return type

[**GetPayoutHistory200Response**](GetPayoutHistory200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_fee_dashboard

> <GetProjectFeeDashboard200Response> get_project_fee_dashboard(project_id)

~~Get fee dashboard~~ (deprecated)

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 

begin
  # ~~Get fee dashboard~~ (deprecated)
  result = api_instance.get_project_fee_dashboard(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_project_fee_dashboard: #{e}"
end
```

#### Using the get_project_fee_dashboard_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectFeeDashboard200Response>, Integer, Hash)> get_project_fee_dashboard_with_http_info(project_id)

```ruby
begin
  # ~~Get fee dashboard~~ (deprecated)
  data, status_code, headers = api_instance.get_project_fee_dashboard_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectFeeDashboard200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->get_project_fee_dashboard_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectFeeDashboard200Response**](GetProjectFeeDashboard200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## initiate_address_verification

> <InitiateAddressVerification200Response> initiate_address_verification(project_id, currency)

~~Initiate address verification~~ (deprecated)

Initiate verification process for a payout address. Requires sending a small test transaction to verify ownership. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
currency = 'currency_example' # String | 

begin
  # ~~Initiate address verification~~ (deprecated)
  result = api_instance.initiate_address_verification(project_id, currency)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->initiate_address_verification: #{e}"
end
```

#### Using the initiate_address_verification_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InitiateAddressVerification200Response>, Integer, Hash)> initiate_address_verification_with_http_info(project_id, currency)

```ruby
begin
  # ~~Initiate address verification~~ (deprecated)
  data, status_code, headers = api_instance.initiate_address_verification_with_http_info(project_id, currency)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InitiateAddressVerification200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->initiate_address_verification_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **currency** | **String** |  |  |

### Return type

[**InitiateAddressVerification200Response**](InitiateAddressVerification200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## request_manual_payout

> <ApplyRoleFeaturePreset200Response> request_manual_payout(project_id, request_manual_payout_request)

~~Request manual payout~~ (deprecated)

Request a manual payout for collected fees. Requires sufficient balance above the threshold. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
request_manual_payout_request = Mudbase::RequestManualPayoutRequest.new({currency: 'currency_example'}) # RequestManualPayoutRequest | 

begin
  # ~~Request manual payout~~ (deprecated)
  result = api_instance.request_manual_payout(project_id, request_manual_payout_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->request_manual_payout: #{e}"
end
```

#### Using the request_manual_payout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> request_manual_payout_with_http_info(project_id, request_manual_payout_request)

```ruby
begin
  # ~~Request manual payout~~ (deprecated)
  data, status_code, headers = api_instance.request_manual_payout_with_http_info(project_id, request_manual_payout_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->request_manual_payout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **request_manual_payout_request** | [**RequestManualPayoutRequest**](RequestManualPayoutRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_currency_fee_settings

> <ApplyRoleFeaturePreset200Response> update_currency_fee_settings(project_id, currency, update_currency_fee_settings_request)

~~Update currency fee settings~~ (deprecated)

Update fee settings for a specific cryptocurrency in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectFeesApi.new
project_id = 'project_id_example' # String | 
currency = 'BTC' # String | 
update_currency_fee_settings_request = Mudbase::UpdateCurrencyFeeSettingsRequest.new # UpdateCurrencyFeeSettingsRequest | 

begin
  # ~~Update currency fee settings~~ (deprecated)
  result = api_instance.update_currency_fee_settings(project_id, currency, update_currency_fee_settings_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->update_currency_fee_settings: #{e}"
end
```

#### Using the update_currency_fee_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> update_currency_fee_settings_with_http_info(project_id, currency, update_currency_fee_settings_request)

```ruby
begin
  # ~~Update currency fee settings~~ (deprecated)
  data, status_code, headers = api_instance.update_currency_fee_settings_with_http_info(project_id, currency, update_currency_fee_settings_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectFeesApi->update_currency_fee_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **currency** | **String** |  |  |
| **update_currency_fee_settings_request** | [**UpdateCurrencyFeeSettingsRequest**](UpdateCurrencyFeeSettingsRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

