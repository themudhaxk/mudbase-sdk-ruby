# Mudbase::EmailApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**enqueue_project_email**](EmailApi.md#enqueue_project_email) | **POST** /api/projects/{projectId}/email/send | Enqueue project email (worker delivery) |
| [**get_project_email_analytics**](EmailApi.md#get_project_email_analytics) | **GET** /api/projects/{projectId}/analytics/email | Email analytics for a project |
| [**get_project_email_smtp**](EmailApi.md#get_project_email_smtp) | **GET** /api/projects/{projectId}/email/smtp | Get project SMTP settings (masked) |
| [**get_project_email_template**](EmailApi.md#get_project_email_template) | **GET** /api/projects/{projectId}/email/templates/{name} | Get one email template (effective content) |
| [**list_project_email_templates**](EmailApi.md#list_project_email_templates) | **GET** /api/projects/{projectId}/email/templates | List email templates (full catalog for the project) |
| [**patch_project_email_smtp**](EmailApi.md#patch_project_email_smtp) | **PATCH** /api/projects/{projectId}/email/smtp | Update project SMTP relay (BYO) |
| [**preview_project_email_template**](EmailApi.md#preview_project_email_template) | **POST** /api/projects/{projectId}/email/templates/{name}/preview | Render template preview (sanitized HTML, no send) |
| [**restore_default_project_email_template**](EmailApi.md#restore_default_project_email_template) | **POST** /api/projects/{projectId}/email/templates/{name}/restore-default | Restore from platform global default or remove project override |
| [**test_project_email_smtp**](EmailApi.md#test_project_email_smtp) | **POST** /api/projects/{projectId}/email/smtp/test | Verify SMTP and send a test message |
| [**upsert_project_email_template**](EmailApi.md#upsert_project_email_template) | **PUT** /api/projects/{projectId}/email/templates/{name} | Upsert project email template (HTML sanitized; variables must cover {{placeholders}}) |
| [**verify_project_email_smtp_domain**](EmailApi.md#verify_project_email_smtp_domain) | **POST** /api/projects/{projectId}/email/smtp/verify-domain | Check DNS (MX + SPF) for sending domain |


## enqueue_project_email

> <EnqueueProjectEmail202Response> enqueue_project_email(project_id, project_email_send_request)

Enqueue project email (worker delivery)

Queues a transactional email for sending through the email worker and configured provider (platform or per-project SMTP). Provide either `template` (with `data`) or both `subject` and `html`. Returns **202** with `jobId` when accepted. 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
project_email_send_request = Mudbase::ProjectEmailSendRequest.new # ProjectEmailSendRequest | 

begin
  # Enqueue project email (worker delivery)
  result = api_instance.enqueue_project_email(project_id, project_email_send_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->enqueue_project_email: #{e}"
end
```

#### Using the enqueue_project_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EnqueueProjectEmail202Response>, Integer, Hash)> enqueue_project_email_with_http_info(project_id, project_email_send_request)

```ruby
begin
  # Enqueue project email (worker delivery)
  data, status_code, headers = api_instance.enqueue_project_email_with_http_info(project_id, project_email_send_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EnqueueProjectEmail202Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->enqueue_project_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **project_email_send_request** | [**ProjectEmailSendRequest**](ProjectEmailSendRequest.md) |  |  |

### Return type

[**EnqueueProjectEmail202Response**](EnqueueProjectEmail202Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_project_email_analytics

> <GetProjectEmailAnalytics200Response> get_project_email_analytics(project_id, opts)

Email analytics for a project

Aggregated email log stats for the project. Optional `from` and `to` query params filter by date range (ISO 8601). 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
opts = {
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # Email analytics for a project
  result = api_instance.get_project_email_analytics(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_analytics: #{e}"
end
```

#### Using the get_project_email_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectEmailAnalytics200Response>, Integer, Hash)> get_project_email_analytics_with_http_info(project_id, opts)

```ruby
begin
  # Email analytics for a project
  data, status_code, headers = api_instance.get_project_email_analytics_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectEmailAnalytics200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_analytics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |

### Return type

[**GetProjectEmailAnalytics200Response**](GetProjectEmailAnalytics200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_email_smtp

> <GetProjectEmailSmtp200Response> get_project_email_smtp(project_id)

Get project SMTP settings (masked)

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 

begin
  # Get project SMTP settings (masked)
  result = api_instance.get_project_email_smtp(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_smtp: #{e}"
end
```

#### Using the get_project_email_smtp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectEmailSmtp200Response>, Integer, Hash)> get_project_email_smtp_with_http_info(project_id)

```ruby
begin
  # Get project SMTP settings (masked)
  data, status_code, headers = api_instance.get_project_email_smtp_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectEmailSmtp200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_smtp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectEmailSmtp200Response**](GetProjectEmailSmtp200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_email_template

> <GetProjectEmailTemplate200Response> get_project_email_template(project_id, name)

Get one email template (effective content)

Returns the template body that would be used when sending: project override if present, else global default, else built-in fallback. **`isProjectOverride`** is true only when this project has a stored row; **`effectiveSource`** is `project`, `global`, or `builtin`. 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
name = 'name_example' # String | 

begin
  # Get one email template (effective content)
  result = api_instance.get_project_email_template(project_id, name)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_template: #{e}"
end
```

#### Using the get_project_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectEmailTemplate200Response>, Integer, Hash)> get_project_email_template_with_http_info(project_id, name)

```ruby
begin
  # Get one email template (effective content)
  data, status_code, headers = api_instance.get_project_email_template_with_http_info(project_id, name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectEmailTemplate200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->get_project_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **name** | **String** |  |  |

### Return type

[**GetProjectEmailTemplate200Response**](GetProjectEmailTemplate200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_project_email_templates

> <ListProjectEmailTemplates200Response> list_project_email_templates(project_id)

List email templates (full catalog for the project)

Returns every template name the worker can resolve for this project: **built-in** defaults, **global** platform rows (`project: null` in DB), and **project** overrides. Use **`isCustomized`** to see if this project has its own stored copy; **`effectiveSource`** shows which layer would be used at send time (`project` wins over `global` over `builtin`). 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 

begin
  # List email templates (full catalog for the project)
  result = api_instance.list_project_email_templates(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->list_project_email_templates: #{e}"
end
```

#### Using the list_project_email_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListProjectEmailTemplates200Response>, Integer, Hash)> list_project_email_templates_with_http_info(project_id)

```ruby
begin
  # List email templates (full catalog for the project)
  data, status_code, headers = api_instance.list_project_email_templates_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListProjectEmailTemplates200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->list_project_email_templates_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**ListProjectEmailTemplates200Response**](ListProjectEmailTemplates200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## patch_project_email_smtp

> <GetProjectEmailSmtp200Response> patch_project_email_smtp(project_id, project_smtp_patch_request)

Update project SMTP relay (BYO)

Set `authPass` in the body to store an encrypted password (never returned on GET). Validates host/user when enabling. 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
project_smtp_patch_request = Mudbase::ProjectSmtpPatchRequest.new # ProjectSmtpPatchRequest | 

begin
  # Update project SMTP relay (BYO)
  result = api_instance.patch_project_email_smtp(project_id, project_smtp_patch_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->patch_project_email_smtp: #{e}"
end
```

#### Using the patch_project_email_smtp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectEmailSmtp200Response>, Integer, Hash)> patch_project_email_smtp_with_http_info(project_id, project_smtp_patch_request)

```ruby
begin
  # Update project SMTP relay (BYO)
  data, status_code, headers = api_instance.patch_project_email_smtp_with_http_info(project_id, project_smtp_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectEmailSmtp200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->patch_project_email_smtp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **project_smtp_patch_request** | [**ProjectSmtpPatchRequest**](ProjectSmtpPatchRequest.md) |  |  |

### Return type

[**GetProjectEmailSmtp200Response**](GetProjectEmailSmtp200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## preview_project_email_template

> preview_project_email_template(project_id, name, opts)

Render template preview (sanitized HTML, no send)

Body **`sampleData`** is merged with layout defaults; keys should match `{{placeholders}}` in the template (see **Email** tag for the catalog). 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
name = 'name_example' # String | 
opts = {
  preview_project_email_template_request: Mudbase::PreviewProjectEmailTemplateRequest.new # PreviewProjectEmailTemplateRequest | 
}

begin
  # Render template preview (sanitized HTML, no send)
  api_instance.preview_project_email_template(project_id, name, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->preview_project_email_template: #{e}"
end
```

#### Using the preview_project_email_template_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> preview_project_email_template_with_http_info(project_id, name, opts)

```ruby
begin
  # Render template preview (sanitized HTML, no send)
  data, status_code, headers = api_instance.preview_project_email_template_with_http_info(project_id, name, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->preview_project_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **name** | **String** |  |  |
| **preview_project_email_template_request** | [**PreviewProjectEmailTemplateRequest**](PreviewProjectEmailTemplateRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## restore_default_project_email_template

> restore_default_project_email_template(project_id, name)

Restore from platform global default or remove project override

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
name = 'name_example' # String | 

begin
  # Restore from platform global default or remove project override
  api_instance.restore_default_project_email_template(project_id, name)
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->restore_default_project_email_template: #{e}"
end
```

#### Using the restore_default_project_email_template_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> restore_default_project_email_template_with_http_info(project_id, name)

```ruby
begin
  # Restore from platform global default or remove project override
  data, status_code, headers = api_instance.restore_default_project_email_template_with_http_info(project_id, name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->restore_default_project_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **name** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## test_project_email_smtp

> <DeleteFunction200Response> test_project_email_smtp(project_id, project_smtp_test_request)

Verify SMTP and send a test message

Rate-limited. With `useSaved: true` (default), uses stored credentials; otherwise pass `host`, `authUser`, `authPass`, etc. 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
project_smtp_test_request = Mudbase::ProjectSmtpTestRequest.new({to: 'to_example'}) # ProjectSmtpTestRequest | 

begin
  # Verify SMTP and send a test message
  result = api_instance.test_project_email_smtp(project_id, project_smtp_test_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->test_project_email_smtp: #{e}"
end
```

#### Using the test_project_email_smtp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteFunction200Response>, Integer, Hash)> test_project_email_smtp_with_http_info(project_id, project_smtp_test_request)

```ruby
begin
  # Verify SMTP and send a test message
  data, status_code, headers = api_instance.test_project_email_smtp_with_http_info(project_id, project_smtp_test_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteFunction200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->test_project_email_smtp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **project_smtp_test_request** | [**ProjectSmtpTestRequest**](ProjectSmtpTestRequest.md) |  |  |

### Return type

[**DeleteFunction200Response**](DeleteFunction200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## upsert_project_email_template

> upsert_project_email_template(project_id, name, upsert_project_email_template_request)

Upsert project email template (HTML sanitized; variables must cover {{placeholders}})

Saves a **project override** for `name`. HTML is sanitized. **`variables`** must list every `{{token}}` used in `subject`, `htmlBody`, and `textBody` (see **Email** tag description for the full placeholder catalog). 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
name = 'name_example' # String | 
upsert_project_email_template_request = Mudbase::UpsertProjectEmailTemplateRequest.new({subject: 'subject_example', html_body: 'html_body_example'}) # UpsertProjectEmailTemplateRequest | 

begin
  # Upsert project email template (HTML sanitized; variables must cover {{placeholders}})
  api_instance.upsert_project_email_template(project_id, name, upsert_project_email_template_request)
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->upsert_project_email_template: #{e}"
end
```

#### Using the upsert_project_email_template_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> upsert_project_email_template_with_http_info(project_id, name, upsert_project_email_template_request)

```ruby
begin
  # Upsert project email template (HTML sanitized; variables must cover {{placeholders}})
  data, status_code, headers = api_instance.upsert_project_email_template_with_http_info(project_id, name, upsert_project_email_template_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->upsert_project_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **name** | **String** |  |  |
| **upsert_project_email_template_request** | [**UpsertProjectEmailTemplateRequest**](UpsertProjectEmailTemplateRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_project_email_smtp_domain

> verify_project_email_smtp_domain(project_id, opts)

Check DNS (MX + SPF) for sending domain

Resolves the domain from `domain`, `fromEmail`, or saved `emailSmtp.fromEmail`. Returns whether MX and SPF TXT exist. With `persist: true` and checks passed, sets `emailSmtp.domainVerifiedAt`. 

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

api_instance = Mudbase::EmailApi.new
project_id = 'project_id_example' # String | 
opts = {
  verify_project_email_smtp_domain_request: Mudbase::VerifyProjectEmailSmtpDomainRequest.new # VerifyProjectEmailSmtpDomainRequest | 
}

begin
  # Check DNS (MX + SPF) for sending domain
  api_instance.verify_project_email_smtp_domain(project_id, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->verify_project_email_smtp_domain: #{e}"
end
```

#### Using the verify_project_email_smtp_domain_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> verify_project_email_smtp_domain_with_http_info(project_id, opts)

```ruby
begin
  # Check DNS (MX + SPF) for sending domain
  data, status_code, headers = api_instance.verify_project_email_smtp_domain_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling EmailApi->verify_project_email_smtp_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **verify_project_email_smtp_domain_request** | [**VerifyProjectEmailSmtpDomainRequest**](VerifyProjectEmailSmtpDomainRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

