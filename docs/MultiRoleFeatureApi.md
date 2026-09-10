# Mudbase::MultiRoleFeatureApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_custom_role**](MultiRoleFeatureApi.md#add_custom_role) | **POST** /api/projects/{projectId}/multi-role/roles | Add custom role |
| [**apply_role_feature_preset**](MultiRoleFeatureApi.md#apply_role_feature_preset) | **POST** /api/projects/{projectId}/multi-role/roles/{roleSlug}/apply-preset | Apply Admin / User / Viewer feature permission preset |
| [**get_available_roles**](MultiRoleFeatureApi.md#get_available_roles) | **GET** /api/projects/{projectId}/multi-role/roles/available | Get available roles for signup |
| [**get_multi_role_config**](MultiRoleFeatureApi.md#get_multi_role_config) | **GET** /api/projects/{projectId}/multi-role | Get multi-role feature configuration |
| [**get_permissions_matrix**](MultiRoleFeatureApi.md#get_permissions_matrix) | **GET** /api/projects/{projectId}/permissions-matrix | Get permissions matrix (collections + featurePermissions) |
| [**oauth_signup_with_role**](MultiRoleFeatureApi.md#oauth_signup_with_role) | **GET** /api/auth/oauth/signup/{role}/{provider}/{projectId} | OAuth signup with specific role |
| [**register_with_role**](MultiRoleFeatureApi.md#register_with_role) | **POST** /api/auth/local/signup/{role} | Register user with specific role (Local Auth) |
| [**simulate_app_permissions**](MultiRoleFeatureApi.md#simulate_app_permissions) | **POST** /api/projects/{projectId}/multi-role/simulate-permissions | Simulate app-role feature permission for a path |
| [**toggle_role**](MultiRoleFeatureApi.md#toggle_role) | **PATCH** /api/projects/{projectId}/multi-role/roles/{roleSlug}/toggle | Toggle role on/off |
| [**update_collection_permissions**](MultiRoleFeatureApi.md#update_collection_permissions) | **PATCH** /api/projects/{projectId}/multi-role/roles/{roleSlug}/collections/{collectionId}/permissions | Update collection permissions for a role |
| [**update_multi_role_settings**](MultiRoleFeatureApi.md#update_multi_role_settings) | **PATCH** /api/projects/{projectId}/multi-role/settings | Update multi-role feature settings |
| [**update_project_role**](MultiRoleFeatureApi.md#update_project_role) | **PATCH** /api/projects/{projectId}/multi-role/roles/{roleSlug} | Update role configuration |


## add_custom_role

> <ApplyRoleFeaturePreset200Response> add_custom_role(project_id, add_custom_role_request)

Add custom role

Add a custom role to a project with specific permissions and signup endpoint. Optional **`featurePermissions`** must align with app JWT gates — see `components/schemas/AppRoleFeaturePermissions` and `services/appRoleFeatureMap.js`. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
add_custom_role_request = Mudbase::AddCustomRoleRequest.new({slug: 'seller', name: 'Seller', signup_endpoint: 'seller'}) # AddCustomRoleRequest | 

begin
  # Add custom role
  result = api_instance.add_custom_role(project_id, add_custom_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->add_custom_role: #{e}"
end
```

#### Using the add_custom_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> add_custom_role_with_http_info(project_id, add_custom_role_request)

```ruby
begin
  # Add custom role
  data, status_code, headers = api_instance.add_custom_role_with_http_info(project_id, add_custom_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->add_custom_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **add_custom_role_request** | [**AddCustomRoleRequest**](AddCustomRoleRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## apply_role_feature_preset

> <ApplyRoleFeaturePreset200Response> apply_role_feature_preset(project_id, role_slug, apply_role_feature_preset_request)

Apply Admin / User / Viewer feature permission preset

Sets `featurePermissions` on the role from a bundled preset (`admin`, `user`, `viewer`). Does not change collection CRUD or `dataScope`; use collection permission APIs for those. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = 'project_id_example' # String | 
role_slug = 'role_slug_example' # String | 
apply_role_feature_preset_request = Mudbase::ApplyRoleFeaturePresetRequest.new({preset: 'admin'}) # ApplyRoleFeaturePresetRequest | 

begin
  # Apply Admin / User / Viewer feature permission preset
  result = api_instance.apply_role_feature_preset(project_id, role_slug, apply_role_feature_preset_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->apply_role_feature_preset: #{e}"
end
```

#### Using the apply_role_feature_preset_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> apply_role_feature_preset_with_http_info(project_id, role_slug, apply_role_feature_preset_request)

```ruby
begin
  # Apply Admin / User / Viewer feature permission preset
  data, status_code, headers = api_instance.apply_role_feature_preset_with_http_info(project_id, role_slug, apply_role_feature_preset_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->apply_role_feature_preset_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **role_slug** | **String** |  |  |
| **apply_role_feature_preset_request** | [**ApplyRoleFeaturePresetRequest**](ApplyRoleFeaturePresetRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_available_roles

> <GetAvailableRoles200Response> get_available_roles(project_id)

Get available roles for signup

Get all available roles for user signup in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 

begin
  # Get available roles for signup
  result = api_instance.get_available_roles(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_available_roles: #{e}"
end
```

#### Using the get_available_roles_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAvailableRoles200Response>, Integer, Hash)> get_available_roles_with_http_info(project_id)

```ruby
begin
  # Get available roles for signup
  data, status_code, headers = api_instance.get_available_roles_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAvailableRoles200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_available_roles_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetAvailableRoles200Response**](GetAvailableRoles200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_multi_role_config

> <GetMultiRoleConfig200Response> get_multi_role_config(project_id)

Get multi-role feature configuration

Returns project app roles (default one editable `customer` starter until you add more) and settings

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 

begin
  # Get multi-role feature configuration
  result = api_instance.get_multi_role_config(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_multi_role_config: #{e}"
end
```

#### Using the get_multi_role_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetMultiRoleConfig200Response>, Integer, Hash)> get_multi_role_config_with_http_info(project_id)

```ruby
begin
  # Get multi-role feature configuration
  data, status_code, headers = api_instance.get_multi_role_config_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetMultiRoleConfig200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_multi_role_config_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetMultiRoleConfig200Response**](GetMultiRoleConfig200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_permissions_matrix

> <GetPermissionsMatrix200Response> get_permissions_matrix(project_id)

Get permissions matrix (collections + featurePermissions)

Dashboard helper: per-collection permission rows (role actions, `dataScope`, conditions) and a per-role `featurePermissions` snapshot used by app-role feature gates (messaging, integrations, storage, etc.). 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 

begin
  # Get permissions matrix (collections + featurePermissions)
  result = api_instance.get_permissions_matrix(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_permissions_matrix: #{e}"
end
```

#### Using the get_permissions_matrix_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPermissionsMatrix200Response>, Integer, Hash)> get_permissions_matrix_with_http_info(project_id)

```ruby
begin
  # Get permissions matrix (collections + featurePermissions)
  data, status_code, headers = api_instance.get_permissions_matrix_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPermissionsMatrix200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->get_permissions_matrix_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**GetPermissionsMatrix200Response**](GetPermissionsMatrix200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## oauth_signup_with_role

> oauth_signup_with_role(role, provider, project_id, opts)

OAuth signup with specific role

Public endpoint that initiates OAuth signup flow with a specific role assigned during registration. The OAuth provider must be configured and enabled for the project first. The role must be available for signup in the project's multi-role configuration. After successful OAuth authentication, the user will be created with the specified role. No authentication required - this is a public signup endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::MultiRoleFeatureApi.new
role = 'customer' # String | Path segment must match the role's `signupEndpoint` (default `customer`; use each role's configured endpoint).
provider = 'google' # String | 
project_id = '685ad30be129932fbb7a1047' # String | 
opts = {
  redirect_url: 'https://client.app/auth/callback' # String | The URL to redirect to after authentication
}

begin
  # OAuth signup with specific role
  api_instance.oauth_signup_with_role(role, provider, project_id, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->oauth_signup_with_role: #{e}"
end
```

#### Using the oauth_signup_with_role_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> oauth_signup_with_role_with_http_info(role, provider, project_id, opts)

```ruby
begin
  # OAuth signup with specific role
  data, status_code, headers = api_instance.oauth_signup_with_role_with_http_info(role, provider, project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->oauth_signup_with_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **role** | **String** | Path segment must match the role&#39;s &#x60;signupEndpoint&#x60; (default &#x60;customer&#x60;; use each role&#39;s configured endpoint). |  |
| **provider** | **String** |  |  |
| **project_id** | **String** |  |  |
| **redirect_url** | **String** | The URL to redirect to after authentication | [optional] |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## register_with_role

> <RegisterWithRole201Response> register_with_role(role, register_with_role_request)

Register user with specific role (Local Auth)

Public endpoint for user registration with a specific role. The path segment must match a role's `signupEndpoint` (default starter is `customer`; add more roles via multi-role API). No authentication required - this is a public signup endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::MultiRoleFeatureApi.new
role = 'customer' # String | Must match the role's `signupEndpoint` (default `customer`; other values for roles you add).
register_with_role_request = Mudbase::RegisterWithRoleRequest.new({email: 'email_example', password: 'password_example', first_name: 'first_name_example', last_name: 'last_name_example', project_id: 'project_id_example', agreed_to_terms: false}) # RegisterWithRoleRequest | 

begin
  # Register user with specific role (Local Auth)
  result = api_instance.register_with_role(role, register_with_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->register_with_role: #{e}"
end
```

#### Using the register_with_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RegisterWithRole201Response>, Integer, Hash)> register_with_role_with_http_info(role, register_with_role_request)

```ruby
begin
  # Register user with specific role (Local Auth)
  data, status_code, headers = api_instance.register_with_role_with_http_info(role, register_with_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RegisterWithRole201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->register_with_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **role** | **String** | Must match the role&#39;s &#x60;signupEndpoint&#x60; (default &#x60;customer&#x60;; other values for roles you add). |  |
| **register_with_role_request** | [**RegisterWithRoleRequest**](RegisterWithRoleRequest.md) |  |  |

### Return type

[**RegisterWithRole201Response**](RegisterWithRole201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## simulate_app_permissions

> <SimulateAppPermissions200Response> simulate_app_permissions(project_id, simulate_app_permissions_request)

Simulate app-role feature permission for a path

Dashboard-only. Given an app role slug and either an OpenAPI `operationId` **or** HTTP method + pathname, returns whether the role's `featurePermissions` would allow the operation for paths that have a feature gate. Unmapped paths or unknown operation IDs return `allowed: true` with reason `no_feature_gate_for_path` or `no_feature_gate_for_operation_id`. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = 'project_id_example' # String | 
simulate_app_permissions_request = Mudbase::SimulateAppPermissionsRequest.new({role: 'customer'}) # SimulateAppPermissionsRequest | 

begin
  # Simulate app-role feature permission for a path
  result = api_instance.simulate_app_permissions(project_id, simulate_app_permissions_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->simulate_app_permissions: #{e}"
end
```

#### Using the simulate_app_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SimulateAppPermissions200Response>, Integer, Hash)> simulate_app_permissions_with_http_info(project_id, simulate_app_permissions_request)

```ruby
begin
  # Simulate app-role feature permission for a path
  data, status_code, headers = api_instance.simulate_app_permissions_with_http_info(project_id, simulate_app_permissions_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SimulateAppPermissions200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->simulate_app_permissions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **simulate_app_permissions_request** | [**SimulateAppPermissionsRequest**](SimulateAppPermissionsRequest.md) |  |  |

### Return type

[**SimulateAppPermissions200Response**](SimulateAppPermissions200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## toggle_role

> <ApplyRoleFeaturePreset200Response> toggle_role(project_id, role_slug, toggle_role_request)

Toggle role on/off

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
role_slug = 'customer' # String | Role slug to toggle (e.g. starter `customer` or a role you added).
toggle_role_request = Mudbase::ToggleRoleRequest.new({is_enabled: true}) # ToggleRoleRequest | 

begin
  # Toggle role on/off
  result = api_instance.toggle_role(project_id, role_slug, toggle_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->toggle_role: #{e}"
end
```

#### Using the toggle_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> toggle_role_with_http_info(project_id, role_slug, toggle_role_request)

```ruby
begin
  # Toggle role on/off
  data, status_code, headers = api_instance.toggle_role_with_http_info(project_id, role_slug, toggle_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->toggle_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **role_slug** | **String** | Role slug to toggle (e.g. starter &#x60;customer&#x60; or a role you added). |  |
| **toggle_role_request** | [**ToggleRoleRequest**](ToggleRoleRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_collection_permissions

> <ApplyRoleFeaturePreset200Response> update_collection_permissions(project_id, role_slug, collection_id, update_collection_permissions_request)

Update collection permissions for a role

Update collection-specific permissions for a role in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
role_slug = 'customer' # String | Role slug (e.g. starter `customer` or a role you added).
collection_id = '696ba6e4f4a9422ac4be4f74' # String | 
update_collection_permissions_request = Mudbase::UpdateCollectionPermissionsRequest.new # UpdateCollectionPermissionsRequest | 

begin
  # Update collection permissions for a role
  result = api_instance.update_collection_permissions(project_id, role_slug, collection_id, update_collection_permissions_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_collection_permissions: #{e}"
end
```

#### Using the update_collection_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> update_collection_permissions_with_http_info(project_id, role_slug, collection_id, update_collection_permissions_request)

```ruby
begin
  # Update collection permissions for a role
  data, status_code, headers = api_instance.update_collection_permissions_with_http_info(project_id, role_slug, collection_id, update_collection_permissions_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_collection_permissions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **role_slug** | **String** | Role slug (e.g. starter &#x60;customer&#x60; or a role you added). |  |
| **collection_id** | **String** |  |  |
| **update_collection_permissions_request** | [**UpdateCollectionPermissionsRequest**](UpdateCollectionPermissionsRequest.md) |  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_multi_role_settings

> <UpdateMultiRoleSettings200Response> update_multi_role_settings(project_id, update_multi_role_settings_request)

Update multi-role feature settings

Update multi-role feature settings for a project: enable/disable the feature, set which app role is the default at signup, and tune `settings` (`allowMultipleRoles`, `requireRoleSelection`, `autoAssignDefault`). This endpoint does **not** edit role definitions or permissions — use `POST/PATCH .../multi-role/roles` for that (same shape as **Add custom role**). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
update_multi_role_settings_request = Mudbase::UpdateMultiRoleSettingsRequest.new # UpdateMultiRoleSettingsRequest | 

begin
  # Update multi-role feature settings
  result = api_instance.update_multi_role_settings(project_id, update_multi_role_settings_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_multi_role_settings: #{e}"
end
```

#### Using the update_multi_role_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateMultiRoleSettings200Response>, Integer, Hash)> update_multi_role_settings_with_http_info(project_id, update_multi_role_settings_request)

```ruby
begin
  # Update multi-role feature settings
  data, status_code, headers = api_instance.update_multi_role_settings_with_http_info(project_id, update_multi_role_settings_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateMultiRoleSettings200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_multi_role_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **update_multi_role_settings_request** | [**UpdateMultiRoleSettingsRequest**](UpdateMultiRoleSettingsRequest.md) |  |  |

### Return type

[**UpdateMultiRoleSettings200Response**](UpdateMultiRoleSettings200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_project_role

> <ApplyRoleFeaturePreset200Response> update_project_role(project_id, role_slug, update_project_role_request)

Update role configuration

Partial update of an app role. **`featurePermissions`** keys must match the app-role gate map (`services/appRoleFeatureMap.js`); schema: `components/schemas/AppRoleFeaturePermissions`. 

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

api_instance = Mudbase::MultiRoleFeatureApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
role_slug = 'customer' # String | Role slug to update (e.g. starter `customer` or a role you added).
update_project_role_request = Mudbase::UpdateProjectRoleRequest.new # UpdateProjectRoleRequest | Same fields as **Add custom role** — send only fields you want to change. `defaultPermissions` / `collectionPermissions` are normalized the same way as on create. **`featurePermissions`:** `components/schemas/AppRoleFeaturePermissions` (aligned with `services/appRoleFeatureMap.js`). 

begin
  # Update role configuration
  result = api_instance.update_project_role(project_id, role_slug, update_project_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_project_role: #{e}"
end
```

#### Using the update_project_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApplyRoleFeaturePreset200Response>, Integer, Hash)> update_project_role_with_http_info(project_id, role_slug, update_project_role_request)

```ruby
begin
  # Update role configuration
  data, status_code, headers = api_instance.update_project_role_with_http_info(project_id, role_slug, update_project_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApplyRoleFeaturePreset200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MultiRoleFeatureApi->update_project_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **role_slug** | **String** | Role slug to update (e.g. starter &#x60;customer&#x60; or a role you added). |  |
| **update_project_role_request** | [**UpdateProjectRoleRequest**](UpdateProjectRoleRequest.md) | Same fields as **Add custom role** — send only fields you want to change. &#x60;defaultPermissions&#x60; / &#x60;collectionPermissions&#x60; are normalized the same way as on create. **&#x60;featurePermissions&#x60;:** &#x60;components/schemas/AppRoleFeaturePermissions&#x60; (aligned with &#x60;services/appRoleFeatureMap.js&#x60;).  |  |

### Return type

[**ApplyRoleFeaturePreset200Response**](ApplyRoleFeaturePreset200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

