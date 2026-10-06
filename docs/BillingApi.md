# Mudbase::BillingApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**cancel_subscription**](BillingApi.md#cancel_subscription) | **POST** /api/billing/subscriptions/{subscriptionId}/cancel | Cancel subscription |
| [**check_feature_access**](BillingApi.md#check_feature_access) | **GET** /api/billing/public/projects/{projectId}/feature-access | Check feature access (public) |
| [**check_subscription**](BillingApi.md#check_subscription) | **GET** /api/billing/public/projects/{projectId}/subscription | Check subscription status (public) |
| [**create_checkout_session**](BillingApi.md#create_checkout_session) | **POST** /api/billing/public/projects/{projectId}/checkout | Create checkout session (fiat) |
| [**create_plan**](BillingApi.md#create_plan) | **POST** /api/billing/projects/{projectId}/plans | Create billing plan |
| [**delete_plan**](BillingApi.md#delete_plan) | **DELETE** /api/billing/projects/{projectId}/plans/{planId} | Delete billing plan |
| [**download_invoice**](BillingApi.md#download_invoice) | **GET** /api/billing/projects/{projectId}/invoices/{invoiceId}/download | Download invoice PDF |
| [**enable_payment_processing**](BillingApi.md#enable_payment_processing) | **POST** /api/orgs/{orgId}/payment-processing/enable | Submit payout onboarding for organization |
| [**export_invoice**](BillingApi.md#export_invoice) | **GET** /api/billing/projects/{projectId}/invoices/{invoiceId}/export | Export invoice (e.g. PDF URL or file) |
| [**get_billing_estimate**](BillingApi.md#get_billing_estimate) | **GET** /api/billing/estimate | Get billing estimate and forecast |
| [**get_checkout_payment**](BillingApi.md#get_checkout_payment) | **GET** /api/billing/public/projects/{projectId}/checkout/{paymentId} | Get checkout payment details (not used for fiat billing) |
| [**get_dashboard**](BillingApi.md#get_dashboard) | **GET** /api/billing/projects/{projectId}/dashboard | Get billing dashboard data |
| [**get_fee_breakdown**](BillingApi.md#get_fee_breakdown) | **GET** /api/orgs/{orgId}/payment-processing/fee-breakdown | Preview the fee for a given amount |
| [**get_invoice**](BillingApi.md#get_invoice) | **GET** /api/billing/projects/{projectId}/invoices/{invoiceId} | Get single invoice |
| [**get_invoices**](BillingApi.md#get_invoices) | **GET** /api/billing/projects/{projectId}/invoices | List project invoices |
| [**get_payment_processing_status**](BillingApi.md#get_payment_processing_status) | **GET** /api/orgs/{orgId}/payment-processing/status | Get payout-onboarding status for organization |
| [**get_payment_records**](BillingApi.md#get_payment_records) | **GET** /api/orgs/{orgId}/payment-processing/records | List fiat payment records for organization |
| [**get_payout_banks**](BillingApi.md#get_payout_banks) | **GET** /api/orgs/{orgId}/payment-processing/banks | List settlement banks for a payout country |
| [**get_payout_countries**](BillingApi.md#get_payout_countries) | **GET** /api/orgs/{orgId}/payment-processing/countries | List supported payout countries |
| [**get_plans**](BillingApi.md#get_plans) | **GET** /api/billing/projects/{projectId}/plans | Get billing plans |
| [**get_public_plans**](BillingApi.md#get_public_plans) | **GET** /api/billing/public/projects/{projectId}/plans | Get public plans (no auth required) |
| [**get_subscription_tier_by_id**](BillingApi.md#get_subscription_tier_by_id) | **GET** /api/billing/plans/{planId} | Get one subscription tier by id |
| [**get_subscription_tiers**](BillingApi.md#get_subscription_tiers) | **GET** /api/billing/plans | Get subscription tiers (org-level BaaS plans) |
| [**get_subscriptions**](BillingApi.md#get_subscriptions) | **GET** /api/billing/projects/{projectId}/subscriptions | Get subscriptions |
| [**initialize_org_plan_checkout**](BillingApi.md#initialize_org_plan_checkout) | **POST** /api/billing/org/checkout | Initialize org-level BaaS plan payment (Basic, Starter, Growth, Scale) |
| [**initialize_payment**](BillingApi.md#initialize_payment) | **POST** /api/orgs/{orgId}/payment-processing/initialize-payment | Initialize fiat payment |
| [**initialize_payment_for_project**](BillingApi.md#initialize_payment_for_project) | **POST** /api/projects/{projectId}/payment-processing/initialize-payment | Initialize fiat payment (project-scoped) |
| [**record_usage**](BillingApi.md#record_usage) | **POST** /api/billing/public/projects/{projectId}/usage | Record usage (public) |
| [**update_plan**](BillingApi.md#update_plan) | **PATCH** /api/billing/projects/{projectId}/plans/{planId} | Update billing plan |
| [**verify_org_plan_payment**](BillingApi.md#verify_org_plan_payment) | **POST** /api/billing/org/verify-payment | Verify org-level plan payment |
| [**verify_payment**](BillingApi.md#verify_payment) | **POST** /api/billing/public/projects/{projectId}/verify-payment | Verify payment and create subscription |


## cancel_subscription

> <DeleteRole200Response> cancel_subscription(subscription_id, opts)

Cancel subscription

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

api_instance = Mudbase::BillingApi.new
subscription_id = 'subscription_id_example' # String | 
opts = {
  cancel_subscription_request: Mudbase::CancelSubscriptionRequest.new # CancelSubscriptionRequest | 
}

begin
  # Cancel subscription
  result = api_instance.cancel_subscription(subscription_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->cancel_subscription: #{e}"
end
```

#### Using the cancel_subscription_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteRole200Response>, Integer, Hash)> cancel_subscription_with_http_info(subscription_id, opts)

```ruby
begin
  # Cancel subscription
  data, status_code, headers = api_instance.cancel_subscription_with_http_info(subscription_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->cancel_subscription_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subscription_id** | **String** |  |  |
| **cancel_subscription_request** | [**CancelSubscriptionRequest**](CancelSubscriptionRequest.md) |  | [optional] |

### Return type

[**DeleteRole200Response**](DeleteRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## check_feature_access

> <CheckFeatureAccess200Response> check_feature_access(project_id, email, feature)

Check feature access (public)

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
email = 'email_example' # String | Customer email
feature = 'feature_example' # String | Feature slug to check access for

begin
  # Check feature access (public)
  result = api_instance.check_feature_access(project_id, email, feature)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->check_feature_access: #{e}"
end
```

#### Using the check_feature_access_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CheckFeatureAccess200Response>, Integer, Hash)> check_feature_access_with_http_info(project_id, email, feature)

```ruby
begin
  # Check feature access (public)
  data, status_code, headers = api_instance.check_feature_access_with_http_info(project_id, email, feature)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CheckFeatureAccess200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->check_feature_access_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **email** | **String** | Customer email |  |
| **feature** | **String** | Feature slug to check access for |  |

### Return type

[**CheckFeatureAccess200Response**](CheckFeatureAccess200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## check_subscription

> <CheckSubscription200Response> check_subscription(project_id, email)

Check subscription status (public)

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
email = 'email_example' # String | Customer email to check subscription for

begin
  # Check subscription status (public)
  result = api_instance.check_subscription(project_id, email)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->check_subscription: #{e}"
end
```

#### Using the check_subscription_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CheckSubscription200Response>, Integer, Hash)> check_subscription_with_http_info(project_id, email)

```ruby
begin
  # Check subscription status (public)
  data, status_code, headers = api_instance.check_subscription_with_http_info(project_id, email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CheckSubscription200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->check_subscription_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **email** | **String** | Customer email to check subscription for |  |

### Return type

[**CheckSubscription200Response**](CheckSubscription200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_checkout_session

> <CreateCheckoutSession200Response> create_checkout_session(project_id, create_checkout_session_request)

Create checkout session (fiat)

**Customer subscription flow — Step 2.** Creates a fiat checkout session. Request body must include planId (from GET public plans), billingCycle (monthly|yearly), and customerInfo.email. Redirect the user to **checkoutUrl** (same URL as authorizationUrl). After payment, call verify-payment with **reference** (mudbase_...). Response includes only fiat fields (no paymentAddress, paymentOptions, network, asset, or pmt_ references). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | Project ID
create_checkout_session_request = Mudbase::CreateCheckoutSessionRequest.new({plan_id: 'plan_id_example', billing_cycle: 'monthly', customer_info: Mudbase::CreateCheckoutSessionRequestCustomerInfo.new({email: 'email_example'})}) # CreateCheckoutSessionRequest | 

begin
  # Create checkout session (fiat)
  result = api_instance.create_checkout_session(project_id, create_checkout_session_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->create_checkout_session: #{e}"
end
```

#### Using the create_checkout_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCheckoutSession200Response>, Integer, Hash)> create_checkout_session_with_http_info(project_id, create_checkout_session_request)

```ruby
begin
  # Create checkout session (fiat)
  data, status_code, headers = api_instance.create_checkout_session_with_http_info(project_id, create_checkout_session_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCheckoutSession200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->create_checkout_session_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** | Project ID |  |
| **create_checkout_session_request** | [**CreateCheckoutSessionRequest**](CreateCheckoutSessionRequest.md) |  |  |

### Return type

[**CreateCheckoutSession200Response**](CreateCheckoutSession200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_plan

> <CreatePlan201Response> create_plan(project_id, create_plan_request)

Create billing plan

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
create_plan_request = Mudbase::CreatePlanRequest.new({name: 'name_example', price: 3.56, currency: 'USD', interval: 'month'}) # CreatePlanRequest | 

begin
  # Create billing plan
  result = api_instance.create_plan(project_id, create_plan_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->create_plan: #{e}"
end
```

#### Using the create_plan_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreatePlan201Response>, Integer, Hash)> create_plan_with_http_info(project_id, create_plan_request)

```ruby
begin
  # Create billing plan
  data, status_code, headers = api_instance.create_plan_with_http_info(project_id, create_plan_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreatePlan201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->create_plan_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_plan_request** | [**CreatePlanRequest**](CreatePlanRequest.md) |  |  |

### Return type

[**CreatePlan201Response**](CreatePlan201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_plan

> <MessageResponse> delete_plan(project_id, plan_id)

Delete billing plan

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
plan_id = 'plan_id_example' # String | 

begin
  # Delete billing plan
  result = api_instance.delete_plan(project_id, plan_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->delete_plan: #{e}"
end
```

#### Using the delete_plan_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_plan_with_http_info(project_id, plan_id)

```ruby
begin
  # Delete billing plan
  data, status_code, headers = api_instance.delete_plan_with_http_info(project_id, plan_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->delete_plan_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **plan_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## download_invoice

> File download_invoice(project_id, invoice_id)

Download invoice PDF

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
invoice_id = 'invoice_id_example' # String | 

begin
  # Download invoice PDF
  result = api_instance.download_invoice(project_id, invoice_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->download_invoice: #{e}"
end
```

#### Using the download_invoice_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> download_invoice_with_http_info(project_id, invoice_id)

```ruby
begin
  # Download invoice PDF
  data, status_code, headers = api_instance.download_invoice_with_http_info(project_id, invoice_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->download_invoice_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **invoice_id** | **String** |  |  |

### Return type

**File**

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/pdf, application/json


## enable_payment_processing

> <EnablePaymentProcessing200Response> enable_payment_processing(org_id, enable_payment_processing_request)

Submit payout onboarding for organization

Validates and stores the org's payout account details, then queues the org for platform-admin review. This does not activate payments by itself; initialize-payment only starts succeeding once the org is approved. The required fields depend on the chosen country: call GET /payment-processing/countries first and collect exactly the fields that country's schema returns (bank code + account number for most African markets, plus a BVN for Nigeria, or routing number/sort code + account type + account holder name for the US/UK). Requires owner or admin role.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 
enable_payment_processing_request = Mudbase::EnablePaymentProcessingRequest.new({country: 'country_example', business_name: 'business_name_example'}) # EnablePaymentProcessingRequest | 

begin
  # Submit payout onboarding for organization
  result = api_instance.enable_payment_processing(org_id, enable_payment_processing_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->enable_payment_processing: #{e}"
end
```

#### Using the enable_payment_processing_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EnablePaymentProcessing200Response>, Integer, Hash)> enable_payment_processing_with_http_info(org_id, enable_payment_processing_request)

```ruby
begin
  # Submit payout onboarding for organization
  data, status_code, headers = api_instance.enable_payment_processing_with_http_info(org_id, enable_payment_processing_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EnablePaymentProcessing200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->enable_payment_processing_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **enable_payment_processing_request** | [**EnablePaymentProcessingRequest**](EnablePaymentProcessingRequest.md) |  |  |

### Return type

[**EnablePaymentProcessing200Response**](EnablePaymentProcessing200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_invoice

> <DownloadInvoice200Response> export_invoice(project_id, invoice_id)

Export invoice (e.g. PDF URL or file)

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
invoice_id = 'invoice_id_example' # String | 

begin
  # Export invoice (e.g. PDF URL or file)
  result = api_instance.export_invoice(project_id, invoice_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->export_invoice: #{e}"
end
```

#### Using the export_invoice_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DownloadInvoice200Response>, Integer, Hash)> export_invoice_with_http_info(project_id, invoice_id)

```ruby
begin
  # Export invoice (e.g. PDF URL or file)
  data, status_code, headers = api_instance.export_invoice_with_http_info(project_id, invoice_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DownloadInvoice200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->export_invoice_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **invoice_id** | **String** |  |  |

### Return type

[**DownloadInvoice200Response**](DownloadInvoice200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_billing_estimate

> <GetBillingEstimate200Response> get_billing_estimate

Get billing estimate and forecast

Returns current-month overage estimate and an optional end-of-month forecast for the authenticated organization. Includes spend limit settings (soft/hard) and whether usage is currently blocked. Requires org-level JWT. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new

begin
  # Get billing estimate and forecast
  result = api_instance.get_billing_estimate
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_billing_estimate: #{e}"
end
```

#### Using the get_billing_estimate_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetBillingEstimate200Response>, Integer, Hash)> get_billing_estimate_with_http_info

```ruby
begin
  # Get billing estimate and forecast
  data, status_code, headers = api_instance.get_billing_estimate_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetBillingEstimate200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_billing_estimate_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetBillingEstimate200Response**](GetBillingEstimate200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_checkout_payment

> get_checkout_payment(project_id, payment_id)

Get checkout payment details (not used for fiat billing)

**Fiat-only billing:** checkout is completed on the payment gateway's hosted page; there is no server-side payment intent to poll. The live API returns **404** for this route. Reserved for compatibility; do not rely on a success body for project billing. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
payment_id = 'payment_id_example' # String | Opaque id from checkout (fiat billing does not expose pollable payment state here)

begin
  # Get checkout payment details (not used for fiat billing)
  api_instance.get_checkout_payment(project_id, payment_id)
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_checkout_payment: #{e}"
end
```

#### Using the get_checkout_payment_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_checkout_payment_with_http_info(project_id, payment_id)

```ruby
begin
  # Get checkout payment details (not used for fiat billing)
  data, status_code, headers = api_instance.get_checkout_payment_with_http_info(project_id, payment_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_checkout_payment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **payment_id** | **String** | Opaque id from checkout (fiat billing does not expose pollable payment state here) |  |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_dashboard

> <GetDashboard200Response> get_dashboard(project_id)

Get billing dashboard data

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get billing dashboard data
  result = api_instance.get_dashboard(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_dashboard: #{e}"
end
```

#### Using the get_dashboard_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDashboard200Response>, Integer, Hash)> get_dashboard_with_http_info(project_id)

```ruby
begin
  # Get billing dashboard data
  data, status_code, headers = api_instance.get_dashboard_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDashboard200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_dashboard_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetDashboard200Response**](GetDashboard200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_fee_breakdown

> <GetFeeBreakdown200Response> get_fee_breakdown(org_id, amount, opts)

Preview the fee for a given amount

Returns the single all-in Mudbase fee, its effective rate, and what the org would net for the given amount, without creating a payment. Pass country/method/international to price a specific rail; omitting them uses a generic local-rail estimate. Never returns the underlying rail's own cost or any internal margin split.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 
amount = 8.14 # Float | 
opts = {
  currency: 'currency_example', # String | 
  country: 'country_example', # String | ISO-3166 alpha-2 payout country code, one of the codes from GET /payment-processing/countries.
  method: 'card', # String | 
  international: true # Boolean | Set true for a cross-border/international card, Apple Pay, or Google Pay.
}

begin
  # Preview the fee for a given amount
  result = api_instance.get_fee_breakdown(org_id, amount, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_fee_breakdown: #{e}"
end
```

#### Using the get_fee_breakdown_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetFeeBreakdown200Response>, Integer, Hash)> get_fee_breakdown_with_http_info(org_id, amount, opts)

```ruby
begin
  # Preview the fee for a given amount
  data, status_code, headers = api_instance.get_fee_breakdown_with_http_info(org_id, amount, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetFeeBreakdown200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_fee_breakdown_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **amount** | **Float** |  |  |
| **currency** | **String** |  | [optional][default to &#39;USD&#39;] |
| **country** | **String** | ISO-3166 alpha-2 payout country code, one of the codes from GET /payment-processing/countries. | [optional] |
| **method** | **String** |  | [optional][default to &#39;card&#39;] |
| **international** | **Boolean** | Set true for a cross-border/international card, Apple Pay, or Google Pay. | [optional][default to false] |

### Return type

[**GetFeeBreakdown200Response**](GetFeeBreakdown200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_invoice

> <GetInvoice200Response> get_invoice(project_id, invoice_id)

Get single invoice

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
invoice_id = 'invoice_id_example' # String | 

begin
  # Get single invoice
  result = api_instance.get_invoice(project_id, invoice_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_invoice: #{e}"
end
```

#### Using the get_invoice_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetInvoice200Response>, Integer, Hash)> get_invoice_with_http_info(project_id, invoice_id)

```ruby
begin
  # Get single invoice
  data, status_code, headers = api_instance.get_invoice_with_http_info(project_id, invoice_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetInvoice200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_invoice_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **invoice_id** | **String** |  |  |

### Return type

[**GetInvoice200Response**](GetInvoice200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_invoices

> <GetInvoices200Response> get_invoices(project_id)

List project invoices

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 

begin
  # List project invoices
  result = api_instance.get_invoices(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_invoices: #{e}"
end
```

#### Using the get_invoices_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetInvoices200Response>, Integer, Hash)> get_invoices_with_http_info(project_id)

```ruby
begin
  # List project invoices
  data, status_code, headers = api_instance.get_invoices_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetInvoices200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_invoices_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetInvoices200Response**](GetInvoices200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_payment_processing_status

> <GetPaymentProcessingStatus200Response> get_payment_processing_status(org_id)

Get payout-onboarding status for organization

Returns the current onboarding/approval state for the org's payout account. Poll this after calling enable, or before calling initialize-payment, to confirm the org is actually approved rather than assuming a 200 from enable means payments are live. Never returns the raw payout-account id, only whether one exists.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 

begin
  # Get payout-onboarding status for organization
  result = api_instance.get_payment_processing_status(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payment_processing_status: #{e}"
end
```

#### Using the get_payment_processing_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPaymentProcessingStatus200Response>, Integer, Hash)> get_payment_processing_status_with_http_info(org_id)

```ruby
begin
  # Get payout-onboarding status for organization
  data, status_code, headers = api_instance.get_payment_processing_status_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPaymentProcessingStatus200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payment_processing_status_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**GetPaymentProcessingStatus200Response**](GetPaymentProcessingStatus200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_payment_records

> <GetPaymentRecords200Response> get_payment_records(org_id, opts)

List fiat payment records for organization

Paginated list of FiatPaymentRecord for this org (txRef, amount, orgReceives, status, paidAt).

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  status: 'pending' # String | 
}

begin
  # List fiat payment records for organization
  result = api_instance.get_payment_records(org_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payment_records: #{e}"
end
```

#### Using the get_payment_records_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPaymentRecords200Response>, Integer, Hash)> get_payment_records_with_http_info(org_id, opts)

```ruby
begin
  # List fiat payment records for organization
  data, status_code, headers = api_instance.get_payment_records_with_http_info(org_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPaymentRecords200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payment_records_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **status** | **String** |  | [optional] |

### Return type

[**GetPaymentRecords200Response**](GetPaymentRecords200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_payout_banks

> <GetPayoutBanks200Response> get_payout_banks(org_id, country)

List settlement banks for a payout country

Read-only lookup of the settlement-bank list for a country, only meaningful when that country's entry from GET /payment-processing/countries has banksListSupported: true. For a country where it is false, this returns an empty list and your onboarding form should fall back to the free-text bank/code field the countries response already describes for that country, rather than calling this endpoint.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 
country = 'country_example' # String | ISO-3166 alpha-2 payout country code, one of the codes from GET /payment-processing/countries.

begin
  # List settlement banks for a payout country
  result = api_instance.get_payout_banks(org_id, country)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payout_banks: #{e}"
end
```

#### Using the get_payout_banks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPayoutBanks200Response>, Integer, Hash)> get_payout_banks_with_http_info(org_id, country)

```ruby
begin
  # List settlement banks for a payout country
  data, status_code, headers = api_instance.get_payout_banks_with_http_info(org_id, country)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPayoutBanks200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payout_banks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **country** | **String** | ISO-3166 alpha-2 payout country code, one of the codes from GET /payment-processing/countries. |  |

### Return type

[**GetPayoutBanks200Response**](GetPayoutBanks200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_payout_countries

> <GetPayoutCountries200Response> get_payout_countries(org_id)

List supported payout countries

Returns the full supported payout-country set and each country's payout-account field schema. Drives a dynamic onboarding form: which fields to collect (bank code/routing number/sort code/IBAN, whether a BVN is required, whether a bank list or mobile-money network applies) comes straight from this response, so build your onboarding UI to render from it rather than hardcoding a country list.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 

begin
  # List supported payout countries
  result = api_instance.get_payout_countries(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payout_countries: #{e}"
end
```

#### Using the get_payout_countries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPayoutCountries200Response>, Integer, Hash)> get_payout_countries_with_http_info(org_id)

```ruby
begin
  # List supported payout countries
  data, status_code, headers = api_instance.get_payout_countries_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPayoutCountries200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_payout_countries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**GetPayoutCountries200Response**](GetPayoutCountries200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_plans

> <GetPlans200Response> get_plans(project_id)

Get billing plans

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get billing plans
  result = api_instance.get_plans(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_plans: #{e}"
end
```

#### Using the get_plans_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPlans200Response>, Integer, Hash)> get_plans_with_http_info(project_id)

```ruby
begin
  # Get billing plans
  data, status_code, headers = api_instance.get_plans_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPlans200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_plans_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetPlans200Response**](GetPlans200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_public_plans

> <GetPublicPlans200Response> get_public_plans(project_id)

Get public plans (no auth required)

**Customer subscription flow — Step 1.** Returns all active plans for the project. Use a plan's _id as planId in the checkout request. No authentication required (for pricing/checkout pages). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get public plans (no auth required)
  result = api_instance.get_public_plans(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_public_plans: #{e}"
end
```

#### Using the get_public_plans_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPublicPlans200Response>, Integer, Hash)> get_public_plans_with_http_info(project_id)

```ruby
begin
  # Get public plans (no auth required)
  data, status_code, headers = api_instance.get_public_plans_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPublicPlans200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_public_plans_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetPublicPlans200Response**](GetPublicPlans200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_subscription_tier_by_id

> <GetSubscriptionTierById200Response> get_subscription_tier_by_id(plan_id)

Get one subscription tier by id

Returns a single org-level BaaS plan (free, basic, starter, growth, scale, enterprise). Public; no auth required.

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
plan_id = 'plan_id_example' # String | Plan id (free, basic, starter, growth, scale, enterprise)

begin
  # Get one subscription tier by id
  result = api_instance.get_subscription_tier_by_id(plan_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscription_tier_by_id: #{e}"
end
```

#### Using the get_subscription_tier_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSubscriptionTierById200Response>, Integer, Hash)> get_subscription_tier_by_id_with_http_info(plan_id)

```ruby
begin
  # Get one subscription tier by id
  data, status_code, headers = api_instance.get_subscription_tier_by_id_with_http_info(plan_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSubscriptionTierById200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscription_tier_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan_id** | **String** | Plan id (free, basic, starter, growth, scale, enterprise) |  |

### Return type

[**GetSubscriptionTierById200Response**](GetSubscriptionTierById200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_subscription_tiers

> <GetSubscriptionTiers200Response> get_subscription_tiers

Get subscription tiers (org-level BaaS plans)

**Org-level BaaS plan catalog** (source of truth in paymentService.js). Returns Free, Basic ($12), Starter ($29), Growth ($69), Scale ($199), Enterprise. Use for pricing page and to get plan ids for POST /api/billing/org/checkout. Public; no auth required. Each plan includes id (free|basic|starter|growth|scale|enterprise), name, description, price (cents), priceYearly (cents, 2 months free), currency, limits, overages, enforcement. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new

begin
  # Get subscription tiers (org-level BaaS plans)
  result = api_instance.get_subscription_tiers
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscription_tiers: #{e}"
end
```

#### Using the get_subscription_tiers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSubscriptionTiers200Response>, Integer, Hash)> get_subscription_tiers_with_http_info

```ruby
begin
  # Get subscription tiers (org-level BaaS plans)
  data, status_code, headers = api_instance.get_subscription_tiers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSubscriptionTiers200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscription_tiers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetSubscriptionTiers200Response**](GetSubscriptionTiers200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_subscriptions

> <GetSubscriptions200Response> get_subscriptions(project_id)

Get subscriptions

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 

begin
  # Get subscriptions
  result = api_instance.get_subscriptions(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscriptions: #{e}"
end
```

#### Using the get_subscriptions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSubscriptions200Response>, Integer, Hash)> get_subscriptions_with_http_info(project_id)

```ruby
begin
  # Get subscriptions
  data, status_code, headers = api_instance.get_subscriptions_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSubscriptions200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->get_subscriptions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetSubscriptions200Response**](GetSubscriptions200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## initialize_org_plan_checkout

> <InitializeOrgPlanCheckout200Response> initialize_org_plan_checkout(initialize_org_plan_checkout_request)

Initialize org-level BaaS plan payment (Basic, Starter, Growth, Scale)

**Org plan payment flow — Step 2.** Creates a payment link for the authenticated org to subscribe to a BaaS plan (basic, starter, growth, scale). Enterprise has no price; use contact-sales flow. Redirect the user to the returned link; after payment, call POST /api/billing/org/verify-payment with the tx_ref from the redirect. Requires org-level JWT. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
initialize_org_plan_checkout_request = Mudbase::InitializeOrgPlanCheckoutRequest.new({plan_name: 'basic'}) # InitializeOrgPlanCheckoutRequest | 

begin
  # Initialize org-level BaaS plan payment (Basic, Starter, Growth, Scale)
  result = api_instance.initialize_org_plan_checkout(initialize_org_plan_checkout_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_org_plan_checkout: #{e}"
end
```

#### Using the initialize_org_plan_checkout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InitializeOrgPlanCheckout200Response>, Integer, Hash)> initialize_org_plan_checkout_with_http_info(initialize_org_plan_checkout_request)

```ruby
begin
  # Initialize org-level BaaS plan payment (Basic, Starter, Growth, Scale)
  data, status_code, headers = api_instance.initialize_org_plan_checkout_with_http_info(initialize_org_plan_checkout_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InitializeOrgPlanCheckout200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_org_plan_checkout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **initialize_org_plan_checkout_request** | [**InitializeOrgPlanCheckoutRequest**](InitializeOrgPlanCheckoutRequest.md) |  |  |

### Return type

[**InitializeOrgPlanCheckout200Response**](InitializeOrgPlanCheckout200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## initialize_payment

> <InitializePayment200Response> initialize_payment(org_id, initialize_payment_request)

Initialize fiat payment

Creates a payment link. The customer pays; Mudbase charges a single all-in, cost-plus fee (see GET /payment-processing/fee-breakdown for the exact rate for a given country/method) and the org receives the remainder. Requires payment processing enabled and approved for the org.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BillingApi.new
org_id = 'org_id_example' # String | 
initialize_payment_request = Mudbase::InitializePaymentRequest.new({amount: 3.56, customer: Mudbase::InitializePaymentRequestCustomer.new({email: 'email_example'})}) # InitializePaymentRequest | 

begin
  # Initialize fiat payment
  result = api_instance.initialize_payment(org_id, initialize_payment_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_payment: #{e}"
end
```

#### Using the initialize_payment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InitializePayment200Response>, Integer, Hash)> initialize_payment_with_http_info(org_id, initialize_payment_request)

```ruby
begin
  # Initialize fiat payment
  data, status_code, headers = api_instance.initialize_payment_with_http_info(org_id, initialize_payment_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InitializePayment200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_payment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **initialize_payment_request** | [**InitializePaymentRequest**](InitializePaymentRequest.md) |  |  |

### Return type

[**InitializePayment200Response**](InitializePayment200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## initialize_payment_for_project

> initialize_payment_for_project(project_id, initialize_payment_for_project_request)

Initialize fiat payment (project-scoped)

Same as org-level initialize-payment; projectId from path is used for scope and tx_ref. Resolves project to org and uses org's payment-processing subaccount.

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
initialize_payment_for_project_request = Mudbase::InitializePaymentForProjectRequest.new({amount: 3.56, customer: Mudbase::InitializePaymentRequestCustomer.new({email: 'email_example'})}) # InitializePaymentForProjectRequest | 

begin
  # Initialize fiat payment (project-scoped)
  api_instance.initialize_payment_for_project(project_id, initialize_payment_for_project_request)
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_payment_for_project: #{e}"
end
```

#### Using the initialize_payment_for_project_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> initialize_payment_for_project_with_http_info(project_id, initialize_payment_for_project_request)

```ruby
begin
  # Initialize fiat payment (project-scoped)
  data, status_code, headers = api_instance.initialize_payment_for_project_with_http_info(project_id, initialize_payment_for_project_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->initialize_payment_for_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **initialize_payment_for_project_request** | [**InitializePaymentForProjectRequest**](InitializePaymentForProjectRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## record_usage

> <MessageResponse> record_usage(project_id, record_usage_request)

Record usage (public)

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
record_usage_request = Mudbase::RecordUsageRequest.new({email: 'email_example', metric: 'metric_example', quantity: 3.56}) # RecordUsageRequest | 

begin
  # Record usage (public)
  result = api_instance.record_usage(project_id, record_usage_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->record_usage: #{e}"
end
```

#### Using the record_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> record_usage_with_http_info(project_id, record_usage_request)

```ruby
begin
  # Record usage (public)
  data, status_code, headers = api_instance.record_usage_with_http_info(project_id, record_usage_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->record_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **record_usage_request** | [**RecordUsageRequest**](RecordUsageRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_plan

> <CreatePlan201Response> update_plan(project_id, plan_id, update_plan_request)

Update billing plan

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

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
plan_id = 'plan_id_example' # String | 
update_plan_request = Mudbase::UpdatePlanRequest.new # UpdatePlanRequest | 

begin
  # Update billing plan
  result = api_instance.update_plan(project_id, plan_id, update_plan_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->update_plan: #{e}"
end
```

#### Using the update_plan_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreatePlan201Response>, Integer, Hash)> update_plan_with_http_info(project_id, plan_id, update_plan_request)

```ruby
begin
  # Update billing plan
  data, status_code, headers = api_instance.update_plan_with_http_info(project_id, plan_id, update_plan_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreatePlan201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->update_plan_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **plan_id** | **String** |  |  |
| **update_plan_request** | [**UpdatePlanRequest**](UpdatePlanRequest.md) |  |  |

### Return type

[**CreatePlan201Response**](CreatePlan201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_org_plan_payment

> <VerifyOrgPlanPayment200Response> verify_org_plan_payment(opts)

Verify org-level plan payment

**Org plan payment flow — Step 3.** Call after the user completes payment (redirect or webhook). Pass tx_ref (or reference) from the payment redirect. Updates org plan and billing; idempotent. No auth required (redirect callback can call this). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
opts = {
  tx_ref: 'tx_ref_example', # String | Payment reference (mudbase_org_...) from checkout redirect
  reference: 'reference_example' # String | Alias for tx_ref
}

begin
  # Verify org-level plan payment
  result = api_instance.verify_org_plan_payment(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->verify_org_plan_payment: #{e}"
end
```

#### Using the verify_org_plan_payment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VerifyOrgPlanPayment200Response>, Integer, Hash)> verify_org_plan_payment_with_http_info(opts)

```ruby
begin
  # Verify org-level plan payment
  data, status_code, headers = api_instance.verify_org_plan_payment_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VerifyOrgPlanPayment200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->verify_org_plan_payment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tx_ref** | **String** | Payment reference (mudbase_org_...) from checkout redirect | [optional] |
| **reference** | **String** | Alias for tx_ref | [optional] |

### Return type

[**VerifyOrgPlanPayment200Response**](VerifyOrgPlanPayment200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## verify_payment

> <VerifyPayment200Response> verify_payment(project_id, reference)

Verify payment and create subscription

**Customer subscription flow — Step 3.** Call after the user completes payment. Pass **reference** as query (?reference=mudbase_...). On success, a subscription is created. No auth required when using the platform gateway (mudbase_ refs). Org-level gateway verification may require JWT. References starting with pmt_ are rejected (crypto billing is not enabled on this API). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::BillingApi.new
project_id = 'project_id_example' # String | 
reference = 'reference_example' # String | Payment transaction reference (mudbase_...)

begin
  # Verify payment and create subscription
  result = api_instance.verify_payment(project_id, reference)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->verify_payment: #{e}"
end
```

#### Using the verify_payment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VerifyPayment200Response>, Integer, Hash)> verify_payment_with_http_info(project_id, reference)

```ruby
begin
  # Verify payment and create subscription
  data, status_code, headers = api_instance.verify_payment_with_http_info(project_id, reference)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VerifyPayment200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BillingApi->verify_payment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **reference** | **String** | Payment transaction reference (mudbase_...) |  |

### Return type

[**VerifyPayment200Response**](VerifyPayment200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

