# Mudbase::ProjectsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**configure_o_auth_provider**](ProjectsApi.md#configure_o_auth_provider) | **POST** /api/auth/oauth/projects/{projectId}/providers/{provider} | Configure OAuth provider for a project |
| [**create_project**](ProjectsApi.md#create_project) | **POST** /api/projects/{orgId}/projects | Create new project |
| [**delete_project**](ProjectsApi.md#delete_project) | **DELETE** /api/projects/{orgId}/projects/{id} | Delete project |
| [**get_o_auth_provider_config**](ProjectsApi.md#get_o_auth_provider_config) | **GET** /api/auth/oauth/projects/{projectId}/providers/{provider} | Get OAuth provider configuration |
| [**get_project**](ProjectsApi.md#get_project) | **GET** /api/projects/{orgId}/projects/{id} | Get single project |
| [**get_project_captcha_config**](ProjectsApi.md#get_project_captcha_config) | **GET** /api/projects/{orgId}/projects/{id}/auth/captcha | Get project CAPTCHA configuration |
| [**get_project_dashboard_overview**](ProjectsApi.md#get_project_dashboard_overview) | **GET** /api/projects/{projectId}/dashboard/overview | Project dashboard overview |
| [**get_project_o_auth_providers**](ProjectsApi.md#get_project_o_auth_providers) | **GET** /api/auth/oauth/projects/{projectId}/providers | Get configured OAuth providers for a project |
| [**get_project_usage**](ProjectsApi.md#get_project_usage) | **GET** /api/projects/{orgId}/projects/{id}/usage | Get project usage statistics |
| [**list_projects**](ProjectsApi.md#list_projects) | **GET** /api/projects/{orgId}/projects | List all projects |
| [**update_o_auth_provider_config**](ProjectsApi.md#update_o_auth_provider_config) | **PATCH** /api/auth/oauth/projects/{projectId}/providers/{provider} | Update OAuth provider configuration |
| [**update_project**](ProjectsApi.md#update_project) | **PATCH** /api/projects/{orgId}/projects/{id} | Update project |
| [**upload_project_logo**](ProjectsApi.md#upload_project_logo) | **POST** /api/projects/{id}/logo | Upload project logo (by project ID) |
| [**upload_project_logo_by_org**](ProjectsApi.md#upload_project_logo_by_org) | **POST** /api/projects/{orgId}/projects/{id}/logo | Upload project logo (by org and project ID) |


## configure_o_auth_provider

> <ConfigureOAuthProvider200Response> configure_o_auth_provider(project_id, provider, configure_o_auth_provider_request)

Configure OAuth provider for a project

Creates or updates the configuration for an OAuth provider for the specified project

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

api_instance = Mudbase::ProjectsApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
provider = 'google' # String | 
configure_o_auth_provider_request = Mudbase::ConfigureOAuthProviderRequest.new({enabled: true, client_id: '123456789-abcdefghijklmnop.apps.googleusercontent.com', client_secret: 'GOCSPX-abcdefghijklmnopqrstuvwxyz'}) # ConfigureOAuthProviderRequest | 

begin
  # Configure OAuth provider for a project
  result = api_instance.configure_o_auth_provider(project_id, provider, configure_o_auth_provider_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->configure_o_auth_provider: #{e}"
end
```

#### Using the configure_o_auth_provider_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConfigureOAuthProvider200Response>, Integer, Hash)> configure_o_auth_provider_with_http_info(project_id, provider, configure_o_auth_provider_request)

```ruby
begin
  # Configure OAuth provider for a project
  data, status_code, headers = api_instance.configure_o_auth_provider_with_http_info(project_id, provider, configure_o_auth_provider_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConfigureOAuthProvider200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->configure_o_auth_provider_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **provider** | **String** |  |  |
| **configure_o_auth_provider_request** | [**ConfigureOAuthProviderRequest**](ConfigureOAuthProviderRequest.md) |  |  |

### Return type

[**ConfigureOAuthProvider200Response**](ConfigureOAuthProvider200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_project

> <CreateProject201Response> create_project(org_id, create_project_request)

Create new project

Create a new project in an organization. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
create_project_request = Mudbase::CreateProjectRequest.new({name: 'Mudbase Platform'}) # CreateProjectRequest | 

begin
  # Create new project
  result = api_instance.create_project(org_id, create_project_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->create_project: #{e}"
end
```

#### Using the create_project_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateProject201Response>, Integer, Hash)> create_project_with_http_info(org_id, create_project_request)

```ruby
begin
  # Create new project
  data, status_code, headers = api_instance.create_project_with_http_info(org_id, create_project_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateProject201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->create_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **create_project_request** | [**CreateProjectRequest**](CreateProjectRequest.md) |  |  |

### Return type

[**CreateProject201Response**](CreateProject201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_project

> <MessageResponse> delete_project(org_id, id)

Delete project

Delete a project permanently. This is a destructive operation. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID

begin
  # Delete project
  result = api_instance.delete_project(org_id, id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->delete_project: #{e}"
end
```

#### Using the delete_project_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_project_with_http_info(org_id, id)

```ruby
begin
  # Delete project
  data, status_code, headers = api_instance.delete_project_with_http_info(org_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->delete_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_o_auth_provider_config

> <GetOAuthProviderConfig200Response> get_o_auth_provider_config(project_id, provider)

Get OAuth provider configuration

Returns the configuration for a specific OAuth provider for the project (without sensitive data)

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

api_instance = Mudbase::ProjectsApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
provider = 'google' # String | 

begin
  # Get OAuth provider configuration
  result = api_instance.get_o_auth_provider_config(project_id, provider)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_o_auth_provider_config: #{e}"
end
```

#### Using the get_o_auth_provider_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOAuthProviderConfig200Response>, Integer, Hash)> get_o_auth_provider_config_with_http_info(project_id, provider)

```ruby
begin
  # Get OAuth provider configuration
  data, status_code, headers = api_instance.get_o_auth_provider_config_with_http_info(project_id, provider)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOAuthProviderConfig200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_o_auth_provider_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **provider** | **String** |  |  |

### Return type

[**GetOAuthProviderConfig200Response**](GetOAuthProviderConfig200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project

> <Project> get_project(org_id, id)

Get single project

Get project details by ID. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID

begin
  # Get single project
  result = api_instance.get_project(org_id, id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project: #{e}"
end
```

#### Using the get_project_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Project>, Integer, Hash)> get_project_with_http_info(org_id, id)

```ruby
begin
  # Get single project
  data, status_code, headers = api_instance.get_project_with_http_info(org_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Project>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |

### Return type

[**Project**](Project.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_captcha_config

> <GetProjectCaptchaConfig200Response> get_project_captcha_config(org_id, id)

Get project CAPTCHA configuration

Get CAPTCHA configuration for a project. This is a public endpoint that returns the site key  and settings needed for frontend integration. Secret key is never returned. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID

begin
  # Get project CAPTCHA configuration
  result = api_instance.get_project_captcha_config(org_id, id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_captcha_config: #{e}"
end
```

#### Using the get_project_captcha_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectCaptchaConfig200Response>, Integer, Hash)> get_project_captcha_config_with_http_info(org_id, id)

```ruby
begin
  # Get project CAPTCHA configuration
  data, status_code, headers = api_instance.get_project_captcha_config_with_http_info(org_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectCaptchaConfig200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_captcha_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |

### Return type

[**GetProjectCaptchaConfig200Response**](GetProjectCaptchaConfig200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_dashboard_overview

> <ProjectDashboardOverviewResponse> get_project_dashboard_overview(project_id)

Project dashboard overview

Single response for the project overview UI: project info, request counts and day-over-day % change, active users (distinct JWT users with project activity; realtime socket count when available), **Uptime** (30d headline) is organization-wide when enough HTTP samples exist, else DB heartbeat probes. **Average latency** (today / 7d) is **per project** and counts only routes documented in `openapi-docs.yaml` for customer/project API (excludes auth, `/api/users`, `/api/orgs`, role-elevation, and multi-role admin routes). Request volume and active users remain per-project. 14-day API call volume and recent audit activity are per-project. See docs/dashboard-overview-api.md. 

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

api_instance = Mudbase::ProjectsApi.new
project_id = '685ad30be129932fbb7a1047' # String | 

begin
  # Project dashboard overview
  result = api_instance.get_project_dashboard_overview(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_dashboard_overview: #{e}"
end
```

#### Using the get_project_dashboard_overview_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectDashboardOverviewResponse>, Integer, Hash)> get_project_dashboard_overview_with_http_info(project_id)

```ruby
begin
  # Project dashboard overview
  data, status_code, headers = api_instance.get_project_dashboard_overview_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectDashboardOverviewResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_dashboard_overview_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**ProjectDashboardOverviewResponse**](ProjectDashboardOverviewResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_o_auth_providers

> <GetProjectOAuthProviders200Response> get_project_o_auth_providers(project_id)

Get configured OAuth providers for a project

Returns a list of OAuth providers that are configured and enabled for the specified project

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

api_instance = Mudbase::ProjectsApi.new
project_id = '685ad30be129932fbb7a1047' # String | 

begin
  # Get configured OAuth providers for a project
  result = api_instance.get_project_o_auth_providers(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_o_auth_providers: #{e}"
end
```

#### Using the get_project_o_auth_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectOAuthProviders200Response>, Integer, Hash)> get_project_o_auth_providers_with_http_info(project_id)

```ruby
begin
  # Get configured OAuth providers for a project
  data, status_code, headers = api_instance.get_project_o_auth_providers_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectOAuthProviders200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_o_auth_providers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetProjectOAuthProviders200Response**](GetProjectOAuthProviders200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_usage

> <ProjectUsageResponse> get_project_usage(org_id, id)

Get project usage statistics

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

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID

begin
  # Get project usage statistics
  result = api_instance.get_project_usage(org_id, id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_usage: #{e}"
end
```

#### Using the get_project_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectUsageResponse>, Integer, Hash)> get_project_usage_with_http_info(org_id, id)

```ruby
begin
  # Get project usage statistics
  data, status_code, headers = api_instance.get_project_usage_with_http_info(org_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectUsageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->get_project_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |

### Return type

[**ProjectUsageResponse**](ProjectUsageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_projects

> <ListProjects200Response> list_projects(org_id)

List all projects

List all projects in an organization. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID

begin
  # List all projects
  result = api_instance.list_projects(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->list_projects: #{e}"
end
```

#### Using the list_projects_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListProjects200Response>, Integer, Hash)> list_projects_with_http_info(org_id)

```ruby
begin
  # List all projects
  data, status_code, headers = api_instance.list_projects_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListProjects200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->list_projects_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_o_auth_provider_config

> <ConfigureOAuthProvider200Response> update_o_auth_provider_config(project_id, provider, update_o_auth_provider_config_request)

Update OAuth provider configuration

Updates the configuration for an OAuth provider for the specified project

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

api_instance = Mudbase::ProjectsApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
provider = 'google' # String | 
update_o_auth_provider_config_request = Mudbase::UpdateOAuthProviderConfigRequest.new # UpdateOAuthProviderConfigRequest | 

begin
  # Update OAuth provider configuration
  result = api_instance.update_o_auth_provider_config(project_id, provider, update_o_auth_provider_config_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->update_o_auth_provider_config: #{e}"
end
```

#### Using the update_o_auth_provider_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConfigureOAuthProvider200Response>, Integer, Hash)> update_o_auth_provider_config_with_http_info(project_id, provider, update_o_auth_provider_config_request)

```ruby
begin
  # Update OAuth provider configuration
  data, status_code, headers = api_instance.update_o_auth_provider_config_with_http_info(project_id, provider, update_o_auth_provider_config_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConfigureOAuthProvider200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->update_o_auth_provider_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **provider** | **String** |  |  |
| **update_o_auth_provider_config_request** | [**UpdateOAuthProviderConfigRequest**](UpdateOAuthProviderConfigRequest.md) |  |  |

### Return type

[**ConfigureOAuthProvider200Response**](ConfigureOAuthProvider200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_project

> <CreateProject201Response> update_project(org_id, id, update_project_request)

Update project

Update project configuration (name, description, settings). **Settings toggles:** **requireEmailVerification** (default true) — when on, new email signups do not get a token until they verify; login is blocked until verified. **requirePhoneVerification** (default false) — when on, phone/OTP users must verify before token. **defaultUserAccountStatus** — **active** (default) or **pending**; when pending, new users must be approved by org owner/admin before they can perform data/storage operations. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID
update_project_request = Mudbase::UpdateProjectRequest.new # UpdateProjectRequest | 

begin
  # Update project
  result = api_instance.update_project(org_id, id, update_project_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->update_project: #{e}"
end
```

#### Using the update_project_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateProject201Response>, Integer, Hash)> update_project_with_http_info(org_id, id, update_project_request)

```ruby
begin
  # Update project
  data, status_code, headers = api_instance.update_project_with_http_info(org_id, id, update_project_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateProject201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->update_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |
| **update_project_request** | [**UpdateProjectRequest**](UpdateProjectRequest.md) |  |  |

### Return type

[**CreateProject201Response**](CreateProject201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## upload_project_logo

> <UploadProjectLogo200Response> upload_project_logo(id, logo)

Upload project logo (by project ID)

Upload a logo image for a project. File is stored in the platform storage under **logo/project/{projectId}/**. The public URL is saved to the project's **logoUrl** field and used in project-related emails and UI. Project is resolved from the authenticated user's org. Use multipart/form-data with field name **logo**. Allowed types: PNG, JPEG, GIF, WebP. Max size 2MB. 

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

api_instance = Mudbase::ProjectsApi.new
id = 'id_example' # String | Project ID
logo = File.new('/path/to/some/file') # File | Logo image (PNG, JPEG, GIF, or WebP; max 2MB)

begin
  # Upload project logo (by project ID)
  result = api_instance.upload_project_logo(id, logo)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->upload_project_logo: #{e}"
end
```

#### Using the upload_project_logo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UploadProjectLogo200Response>, Integer, Hash)> upload_project_logo_with_http_info(id, logo)

```ruby
begin
  # Upload project logo (by project ID)
  data, status_code, headers = api_instance.upload_project_logo_with_http_info(id, logo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UploadProjectLogo200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->upload_project_logo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Project ID |  |
| **logo** | **File** | Logo image (PNG, JPEG, GIF, or WebP; max 2MB) |  |

### Return type

[**UploadProjectLogo200Response**](UploadProjectLogo200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json


## upload_project_logo_by_org

> <UploadProjectLogo200Response> upload_project_logo_by_org(org_id, id, logo)

Upload project logo (by org and project ID)

Upload a logo image for a project. File is stored in the platform storage under **logo/project/{projectId}/**. The public URL is saved to the project's **logoUrl** field. Use multipart/form-data with field name **logo**. Allowed types: PNG, JPEG, GIF, WebP. Max size 2MB. Requires project update permission and membership in the organization. 

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

api_instance = Mudbase::ProjectsApi.new
org_id = 'org_id_example' # String | Organization ID
id = 'id_example' # String | Project ID
logo = File.new('/path/to/some/file') # File | Logo image (PNG, JPEG, GIF, or WebP; max 2MB)

begin
  # Upload project logo (by org and project ID)
  result = api_instance.upload_project_logo_by_org(org_id, id, logo)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->upload_project_logo_by_org: #{e}"
end
```

#### Using the upload_project_logo_by_org_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UploadProjectLogo200Response>, Integer, Hash)> upload_project_logo_by_org_with_http_info(org_id, id, logo)

```ruby
begin
  # Upload project logo (by org and project ID)
  data, status_code, headers = api_instance.upload_project_logo_by_org_with_http_info(org_id, id, logo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UploadProjectLogo200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ProjectsApi->upload_project_logo_by_org_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** | Organization ID |  |
| **id** | **String** | Project ID |  |
| **logo** | **File** | Logo image (PNG, JPEG, GIF, or WebP; max 2MB) |  |

### Return type

[**UploadProjectLogo200Response**](UploadProjectLogo200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

