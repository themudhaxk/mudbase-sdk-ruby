# Mudbase::RolesApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**assign_role**](RolesApi.md#assign_role) | **POST** /api/orgs/{orgId}/users/{userId}/role | ~~Assign custom role to user~~ (deprecated) |
| [**check_permissions**](RolesApi.md#check_permissions) | **GET** /api/orgs/{orgId}/users/{userId}/permissions | ~~Check user permissions~~ (deprecated) |
| [**create_role**](RolesApi.md#create_role) | **POST** /api/orgs/{orgId}/roles | ~~Create custom role~~ (deprecated) |
| [**delete_role**](RolesApi.md#delete_role) | **DELETE** /api/orgs/{orgId}/roles/{roleId} | ~~Delete role~~ (deprecated) |
| [**get_role**](RolesApi.md#get_role) | **GET** /api/orgs/{orgId}/roles/{roleId} | ~~Get role details~~ (deprecated) |
| [**get_users_by_role**](RolesApi.md#get_users_by_role) | **GET** /api/orgs/{orgId}/roles/{roleSlug}/users | ~~Get users with specific role~~ (deprecated) |
| [**list_roles**](RolesApi.md#list_roles) | **GET** /api/orgs/{orgId}/roles | ~~List all roles~~ (deprecated) |
| [**remove_role**](RolesApi.md#remove_role) | **DELETE** /api/orgs/{orgId}/users/{userId}/role | ~~Remove custom role from user~~ (deprecated) |
| [**update_role**](RolesApi.md#update_role) | **PUT** /api/orgs/{orgId}/roles/{roleId} | ~~Update role~~ (deprecated) |


## assign_role

> <AssignRole200Response> assign_role(org_id, user_id, assign_role_request)

~~Assign custom role to user~~ (deprecated)

Assign a custom role to a user in the organization. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 
assign_role_request = Mudbase::AssignRoleRequest.new({role_slug: 'support_agent'}) # AssignRoleRequest | 

begin
  # ~~Assign custom role to user~~ (deprecated)
  result = api_instance.assign_role(org_id, user_id, assign_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->assign_role: #{e}"
end
```

#### Using the assign_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AssignRole200Response>, Integer, Hash)> assign_role_with_http_info(org_id, user_id, assign_role_request)

```ruby
begin
  # ~~Assign custom role to user~~ (deprecated)
  data, status_code, headers = api_instance.assign_role_with_http_info(org_id, user_id, assign_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AssignRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->assign_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **assign_role_request** | [**AssignRoleRequest**](AssignRoleRequest.md) |  |  |

### Return type

[**AssignRole200Response**](AssignRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## check_permissions

> <CheckPermissions200Response> check_permissions(org_id, user_id)

~~Check user permissions~~ (deprecated)

Get all permissions for a user (system + custom role combined)

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 

begin
  # ~~Check user permissions~~ (deprecated)
  result = api_instance.check_permissions(org_id, user_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->check_permissions: #{e}"
end
```

#### Using the check_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CheckPermissions200Response>, Integer, Hash)> check_permissions_with_http_info(org_id, user_id)

```ruby
begin
  # ~~Check user permissions~~ (deprecated)
  data, status_code, headers = api_instance.check_permissions_with_http_info(org_id, user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CheckPermissions200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->check_permissions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |

### Return type

[**CheckPermissions200Response**](CheckPermissions200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_role

> <CreateRole201Response> create_role(org_id, create_role_request)

~~Create custom role~~ (deprecated)

Create a new custom role with specific permissions for your organization. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
create_role_request = Mudbase::CreateRoleRequest.new({name: 'Support Agent'}) # CreateRoleRequest | 

begin
  # ~~Create custom role~~ (deprecated)
  result = api_instance.create_role(org_id, create_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->create_role: #{e}"
end
```

#### Using the create_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateRole201Response>, Integer, Hash)> create_role_with_http_info(org_id, create_role_request)

```ruby
begin
  # ~~Create custom role~~ (deprecated)
  data, status_code, headers = api_instance.create_role_with_http_info(org_id, create_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateRole201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->create_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **create_role_request** | [**CreateRoleRequest**](CreateRoleRequest.md) |  |  |

### Return type

[**CreateRole201Response**](CreateRole201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_role

> <DeleteRole200Response> delete_role(org_id, role_id)

~~Delete role~~ (deprecated)

Delete a custom role. Cannot delete system roles or roles with active users. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
role_id = 'role123' # String | 

begin
  # ~~Delete role~~ (deprecated)
  result = api_instance.delete_role(org_id, role_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->delete_role: #{e}"
end
```

#### Using the delete_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteRole200Response>, Integer, Hash)> delete_role_with_http_info(org_id, role_id)

```ruby
begin
  # ~~Delete role~~ (deprecated)
  data, status_code, headers = api_instance.delete_role_with_http_info(org_id, role_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->delete_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **role_id** | **String** |  |  |

### Return type

[**DeleteRole200Response**](DeleteRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_role

> <GetRole200Response> get_role(org_id, role_id)

~~Get role details~~ (deprecated)

Get details of a specific custom role. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
role_id = 'role123' # String | 

begin
  # ~~Get role details~~ (deprecated)
  result = api_instance.get_role(org_id, role_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->get_role: #{e}"
end
```

#### Using the get_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetRole200Response>, Integer, Hash)> get_role_with_http_info(org_id, role_id)

```ruby
begin
  # ~~Get role details~~ (deprecated)
  data, status_code, headers = api_instance.get_role_with_http_info(org_id, role_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->get_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **role_id** | **String** |  |  |

### Return type

[**GetRole200Response**](GetRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_users_by_role

> <GetUsersByRole200Response> get_users_by_role(org_id, role_slug)

~~Get users with specific role~~ (deprecated)

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
role_slug = 'support_agent' # String | 

begin
  # ~~Get users with specific role~~ (deprecated)
  result = api_instance.get_users_by_role(org_id, role_slug)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->get_users_by_role: #{e}"
end
```

#### Using the get_users_by_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUsersByRole200Response>, Integer, Hash)> get_users_by_role_with_http_info(org_id, role_slug)

```ruby
begin
  # ~~Get users with specific role~~ (deprecated)
  data, status_code, headers = api_instance.get_users_by_role_with_http_info(org_id, role_slug)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUsersByRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->get_users_by_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **role_slug** | **String** |  |  |

### Return type

[**GetUsersByRole200Response**](GetUsersByRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_roles

> <ListRoles200Response> list_roles(org_id)

~~List all roles~~ (deprecated)

Get all custom roles for the organization. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # ~~List all roles~~ (deprecated)
  result = api_instance.list_roles(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->list_roles: #{e}"
end
```

#### Using the list_roles_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListRoles200Response>, Integer, Hash)> list_roles_with_http_info(org_id)

```ruby
begin
  # ~~List all roles~~ (deprecated)
  data, status_code, headers = api_instance.list_roles_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListRoles200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->list_roles_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**ListRoles200Response**](ListRoles200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_role

> <AssignRole200Response> remove_role(org_id, user_id)

~~Remove custom role from user~~ (deprecated)

Remove a custom role from a user in the organization. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 

begin
  # ~~Remove custom role from user~~ (deprecated)
  result = api_instance.remove_role(org_id, user_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->remove_role: #{e}"
end
```

#### Using the remove_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AssignRole200Response>, Integer, Hash)> remove_role_with_http_info(org_id, user_id)

```ruby
begin
  # ~~Remove custom role from user~~ (deprecated)
  data, status_code, headers = api_instance.remove_role_with_http_info(org_id, user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AssignRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->remove_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |

### Return type

[**AssignRole200Response**](AssignRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_role

> <UpdateRole200Response> update_role(org_id, role_id, update_role_request)

~~Update role~~ (deprecated)

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

api_instance = Mudbase::RolesApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
role_id = 'role123' # String | 
update_role_request = Mudbase::UpdateRoleRequest.new # UpdateRoleRequest | 

begin
  # ~~Update role~~ (deprecated)
  result = api_instance.update_role(org_id, role_id, update_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->update_role: #{e}"
end
```

#### Using the update_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateRole200Response>, Integer, Hash)> update_role_with_http_info(org_id, role_id, update_role_request)

```ruby
begin
  # ~~Update role~~ (deprecated)
  data, status_code, headers = api_instance.update_role_with_http_info(org_id, role_id, update_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RolesApi->update_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **role_id** | **String** |  |  |
| **update_role_request** | [**UpdateRoleRequest**](UpdateRoleRequest.md) |  |  |

### Return type

[**UpdateRole200Response**](UpdateRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

