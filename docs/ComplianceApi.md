# Mudbase::ComplianceApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**api_gdpr_erase_post**](ComplianceApi.md#api_gdpr_erase_post) | **POST** /api/gdpr/erase | Erase my personal data (GDPR Art. 17) |
| [**api_gdpr_export_get**](ComplianceApi.md#api_gdpr_export_get) | **GET** /api/gdpr/export | Export my personal data (GDPR Art. 15) |
| [**generate_access_review**](ComplianceApi.md#generate_access_review) | **POST** /api/compliance/access-review | Generate access review report (SOC 2) |
| [**generate_data_processing_record**](ComplianceApi.md#generate_data_processing_record) | **POST** /api/compliance/data-processing-record | Generate data processing record (GDPR Article 30) |
| [**get_compliance_summary**](ComplianceApi.md#get_compliance_summary) | **GET** /api/compliance/summary | Get compliance summary |
| [**log_security_event**](ComplianceApi.md#log_security_event) | **POST** /api/compliance/security-event | Log security event |


## api_gdpr_erase_post

> <ApplyRoleFeaturePreset200Response> api_gdpr_erase_post(api_gdpr_erase_post_request)

Erase my personal data (GDPR Art. 17)

Anonymizes the subject's PII, revokes sessions/tokens, and anonymizes (never hard-deletes) financial/legal-retention records. Idempotent and self-scoped.  Requires re-proving your current password (skipped only for OAuth-only accounts with no password set) and, if 2FA is enabled, a fresh TOTP code - the same step-up re-authentication already required by the less-destructive `PATCH /api/users/password` and `POST /api/users/2fa/disable`. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::ComplianceApi.new
api_gdpr_erase_post_request = Mudbase::ApiGdprErasePostRequest.new({confirm: 'DELETE'}) # ApiGdprErasePostRequest | 

begin
  # Erase my personal data (GDPR Art. 17)
  result = api_instance.api_gdpr_erase_post(api_gdpr_erase_post_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->api_gdpr_erase_post: #{e}"
end
```

#### Using the api_gdpr_erase_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> api_gdpr_erase_post_with_http_info(api_gdpr_erase_post_request)

```ruby
begin
  # Erase my personal data (GDPR Art. 17)
  data, status_code, headers = api_instance.api_gdpr_erase_post_with_http_info(api_gdpr_erase_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->api_gdpr_erase_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_gdpr_erase_post_request** | [**ApiGdprErasePostRequest**](ApiGdprErasePostRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## api_gdpr_export_get

> Object api_gdpr_export_get

Export my personal data (GDPR Art. 15)

Returns the authenticated subject's personal data as a downloadable JSON attachment. Self-scoped — a caller can only export their own data.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::ComplianceApi.new

begin
  # Export my personal data (GDPR Art. 15)
  result = api_instance.api_gdpr_export_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->api_gdpr_export_get: #{e}"
end
```

#### Using the api_gdpr_export_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> api_gdpr_export_get_with_http_info

```ruby
begin
  # Export my personal data (GDPR Art. 15)
  data, status_code, headers = api_instance.api_gdpr_export_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->api_gdpr_export_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## generate_access_review

> <GenerateAccessReview200Response> generate_access_review(generate_access_review_request)

Generate access review report (SOC 2)

Generate access review report for compliance audits (SOC 2, ISO 27001, etc.). Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::ComplianceApi.new
generate_access_review_request = Mudbase::GenerateAccessReviewRequest.new({org_id: '685acbe0e129932fbb7a0fc3', review_period: Mudbase::GenerateAccessReviewRequestReviewPeriod.new({start: Time.parse('2024-10-01T00:00Z'), _end: Time.parse('2024-12-31T23:59:59Z')})}) # GenerateAccessReviewRequest | 

begin
  # Generate access review report (SOC 2)
  result = api_instance.generate_access_review(generate_access_review_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->generate_access_review: #{e}"
end
```

#### Using the generate_access_review_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GenerateAccessReview200Response>, Integer, Hash)> generate_access_review_with_http_info(generate_access_review_request)

```ruby
begin
  # Generate access review report (SOC 2)
  data, status_code, headers = api_instance.generate_access_review_with_http_info(generate_access_review_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GenerateAccessReview200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->generate_access_review_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **generate_access_review_request** | [**GenerateAccessReviewRequest**](GenerateAccessReviewRequest.md) |  |  |

### Return type

[**GenerateAccessReview200Response**](GenerateAccessReview200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## generate_data_processing_record

> <GenerateDataProcessingRecord200Response> generate_data_processing_record(generate_data_processing_record_request)

Generate data processing record (GDPR Article 30)

Generate GDPR Article 30 compliant data processing record

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

api_instance = Mudbase::ComplianceApi.new
generate_data_processing_record_request = Mudbase::GenerateDataProcessingRecordRequest.new({org_id: '685acbe0e129932fbb7a0fc3'}) # GenerateDataProcessingRecordRequest | 

begin
  # Generate data processing record (GDPR Article 30)
  result = api_instance.generate_data_processing_record(generate_data_processing_record_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->generate_data_processing_record: #{e}"
end
```

#### Using the generate_data_processing_record_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GenerateDataProcessingRecord200Response>, Integer, Hash)> generate_data_processing_record_with_http_info(generate_data_processing_record_request)

```ruby
begin
  # Generate data processing record (GDPR Article 30)
  data, status_code, headers = api_instance.generate_data_processing_record_with_http_info(generate_data_processing_record_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GenerateDataProcessingRecord200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->generate_data_processing_record_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **generate_data_processing_record_request** | [**GenerateDataProcessingRecordRequest**](GenerateDataProcessingRecordRequest.md) |  |  |

### Return type

[**GenerateDataProcessingRecord200Response**](GenerateDataProcessingRecord200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_compliance_summary

> <GetComplianceSummary200Response> get_compliance_summary

Get compliance summary

Get compliance dashboard data (GDPR, SOC 2, security status). Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations.

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

api_instance = Mudbase::ComplianceApi.new

begin
  # Get compliance summary
  result = api_instance.get_compliance_summary
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->get_compliance_summary: #{e}"
end
```

#### Using the get_compliance_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetComplianceSummary200Response>, Integer, Hash)> get_compliance_summary_with_http_info

```ruby
begin
  # Get compliance summary
  data, status_code, headers = api_instance.get_compliance_summary_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetComplianceSummary200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->get_compliance_summary_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetComplianceSummary200Response**](GetComplianceSummary200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## log_security_event

> <LogSecurityEvent200Response> log_security_event(log_security_event_request)

Log security event

Log a security event for compliance and audit purposes

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

api_instance = Mudbase::ComplianceApi.new
log_security_event_request = Mudbase::LogSecurityEventRequest.new({event_type: 'unauthorized_access_attempt', severity: 'low'}) # LogSecurityEventRequest | 

begin
  # Log security event
  result = api_instance.log_security_event(log_security_event_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->log_security_event: #{e}"
end
```

#### Using the log_security_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<LogSecurityEvent200Response>, Integer, Hash)> log_security_event_with_http_info(log_security_event_request)

```ruby
begin
  # Log security event
  data, status_code, headers = api_instance.log_security_event_with_http_info(log_security_event_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <LogSecurityEvent200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ComplianceApi->log_security_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **log_security_event_request** | [**LogSecurityEventRequest**](LogSecurityEventRequest.md) |  |  |

### Return type

[**LogSecurityEvent200Response**](LogSecurityEvent200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

