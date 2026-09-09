# Mudbase::RoleElevationApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**approve_role_elevation**](RoleElevationApi.md#approve_role_elevation) | **POST** /api/orgs/{orgId}/role-elevation/{requestId}/approve | Approve/reject role elevation request (admin only) |
| [**get_pending_role_elevation_requests**](RoleElevationApi.md#get_pending_role_elevation_requests) | **GET** /api/orgs/{orgId}/role-elevation/pending | Get pending role elevation requests (admin only) |
| [**get_role_elevation_status**](RoleElevationApi.md#get_role_elevation_status) | **GET** /api/projects/{projectId}/role-elevation/status | Get role elevation status |
| [**request_role_elevation**](RoleElevationApi.md#request_role_elevation) | **POST** /api/projects/{projectId}/role-elevation/request | Request role elevation |
| [**upload_verification_documents**](RoleElevationApi.md#upload_verification_documents) | **POST** /api/projects/{projectId}/role-elevation/documents | Upload verification documents |


## approve_role_elevation

> <ApproveRoleElevation200Response> approve_role_elevation(org_id, request_id, approve_role_elevation_request)

Approve/reject role elevation request (admin only)

Admin approves or rejects a role elevation request

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

api_instance = Mudbase::RoleElevationApi.new
org_id = 'org_id_example' # String | 
request_id = 'request_id_example' # String | 
approve_role_elevation_request = Mudbase::ApproveRoleElevationRequest.new({approved: false}) # ApproveRoleElevationRequest | 

begin
  # Approve/reject role elevation request (admin only)
  result = api_instance.approve_role_elevation(org_id, request_id, approve_role_elevation_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->approve_role_elevation: #{e}"
end
```

#### Using the approve_role_elevation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApproveRoleElevation200Response>, Integer, Hash)> approve_role_elevation_with_http_info(org_id, request_id, approve_role_elevation_request)

```ruby
begin
  # Approve/reject role elevation request (admin only)
  data, status_code, headers = api_instance.approve_role_elevation_with_http_info(org_id, request_id, approve_role_elevation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApproveRoleElevation200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->approve_role_elevation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **request_id** | **String** |  |  |
| **approve_role_elevation_request** | [**ApproveRoleElevationRequest**](ApproveRoleElevationRequest.md) |  |  |

### Return type

[**ApproveRoleElevation200Response**](ApproveRoleElevation200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_pending_role_elevation_requests

> <GetPendingRoleElevationRequests200Response> get_pending_role_elevation_requests(org_id, opts)

Get pending role elevation requests (admin only)

Get all pending role elevation requests requiring admin approval

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

api_instance = Mudbase::RoleElevationApi.new
org_id = 'org_id_example' # String | 
opts = {
  status: 'pending', # String | 
  page: 56, # Integer | 
  limit: 56 # Integer | 
}

begin
  # Get pending role elevation requests (admin only)
  result = api_instance.get_pending_role_elevation_requests(org_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->get_pending_role_elevation_requests: #{e}"
end
```

#### Using the get_pending_role_elevation_requests_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetPendingRoleElevationRequests200Response>, Integer, Hash)> get_pending_role_elevation_requests_with_http_info(org_id, opts)

```ruby
begin
  # Get pending role elevation requests (admin only)
  data, status_code, headers = api_instance.get_pending_role_elevation_requests_with_http_info(org_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetPendingRoleElevationRequests200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->get_pending_role_elevation_requests_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **status** | **String** |  | [optional][default to &#39;pending&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**GetPendingRoleElevationRequests200Response**](GetPendingRoleElevationRequests200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_role_elevation_status

> <GetRoleElevationStatus200Response> get_role_elevation_status(project_id, opts)

Get role elevation status

Get status of pending role elevation requests for current user

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

api_instance = Mudbase::RoleElevationApi.new
project_id = 'project_id_example' # String | 
opts = {
  role_slug: 'role_slug_example' # String | 
}

begin
  # Get role elevation status
  result = api_instance.get_role_elevation_status(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->get_role_elevation_status: #{e}"
end
```

#### Using the get_role_elevation_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetRoleElevationStatus200Response>, Integer, Hash)> get_role_elevation_status_with_http_info(project_id, opts)

```ruby
begin
  # Get role elevation status
  data, status_code, headers = api_instance.get_role_elevation_status_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetRoleElevationStatus200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->get_role_elevation_status_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **role_slug** | **String** |  | [optional] |

### Return type

[**GetRoleElevationStatus200Response**](GetRoleElevationStatus200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## request_role_elevation

> <RequestRoleElevation200Response> request_role_elevation(project_id, request_role_elevation_request)

Request role elevation

User requests to upgrade to a specific role. May require payment, KYC, or admin approval based on role configuration.

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

api_instance = Mudbase::RoleElevationApi.new
project_id = 'project_id_example' # String | 
request_role_elevation_request = Mudbase::RequestRoleElevationRequest.new({role_slug: 'seller'}) # RequestRoleElevationRequest | 

begin
  # Request role elevation
  result = api_instance.request_role_elevation(project_id, request_role_elevation_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->request_role_elevation: #{e}"
end
```

#### Using the request_role_elevation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RequestRoleElevation200Response>, Integer, Hash)> request_role_elevation_with_http_info(project_id, request_role_elevation_request)

```ruby
begin
  # Request role elevation
  data, status_code, headers = api_instance.request_role_elevation_with_http_info(project_id, request_role_elevation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RequestRoleElevation200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->request_role_elevation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **request_role_elevation_request** | [**RequestRoleElevationRequest**](RequestRoleElevationRequest.md) |  |  |

### Return type

[**RequestRoleElevation200Response**](RequestRoleElevation200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## upload_verification_documents

> upload_verification_documents(project_id, upload_verification_documents_request)

Upload verification documents

Upload KYC/verification documents for role elevation

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

api_instance = Mudbase::RoleElevationApi.new
project_id = 'project_id_example' # String | 
upload_verification_documents_request = Mudbase::UploadVerificationDocumentsRequest.new({role_slug: 'role_slug_example', documents: [Mudbase::UploadVerificationDocumentsRequestDocumentsInner.new]}) # UploadVerificationDocumentsRequest | 

begin
  # Upload verification documents
  api_instance.upload_verification_documents(project_id, upload_verification_documents_request)
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->upload_verification_documents: #{e}"
end
```

#### Using the upload_verification_documents_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> upload_verification_documents_with_http_info(project_id, upload_verification_documents_request)

```ruby
begin
  # Upload verification documents
  data, status_code, headers = api_instance.upload_verification_documents_with_http_info(project_id, upload_verification_documents_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling RoleElevationApi->upload_verification_documents_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **upload_verification_documents_request** | [**UploadVerificationDocumentsRequest**](UploadVerificationDocumentsRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined

