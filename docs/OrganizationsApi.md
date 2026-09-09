# Mudbase::OrganizationsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_org_custom_domain**](OrganizationsApi.md#add_org_custom_domain) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains | Add a custom domain |
| [**create_organization**](OrganizationsApi.md#create_organization) | **POST** /api/orgs | ~~Create new organization~~ (disabled) |
| [**delete_org_custom_domain**](OrganizationsApi.md#delete_org_custom_domain) | **DELETE** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname} | Remove a custom domain |
| [**delete_organization**](OrganizationsApi.md#delete_organization) | **DELETE** /api/orgs/{orgId} | Delete organization |
| [**delete_sub_organization**](OrganizationsApi.md#delete_sub_organization) | **DELETE** /api/orgs/{orgId}/suborgs/{suborgId} | ~~Delete sub-organization~~ (deprecated) |
| [**get_org_custom_domain_dns_instructions**](OrganizationsApi.md#get_org_custom_domain_dns_instructions) | **GET** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/dns-instructions | Get DNS TXT record instructions for one hostname |
| [**get_organization**](OrganizationsApi.md#get_organization) | **GET** /api/orgs/{orgId} | Get organization details by ID |
| [**get_organization_members**](OrganizationsApi.md#get_organization_members) | **GET** /api/orgs/{orgId}/members | Get organization members |
| [**get_organization_usage**](OrganizationsApi.md#get_organization_usage) | **GET** /api/orgs/{orgId}/usage | Get organization usage and billing |
| [**get_organization_users**](OrganizationsApi.md#get_organization_users) | **GET** /api/orgs/{orgId}/users | List organization users with metadata |
| [**get_project_users**](OrganizationsApi.md#get_project_users) | **GET** /api/orgs/{orgId}/projects/{projectId}/users | List project users with metadata |
| [**get_sub_organizations**](OrganizationsApi.md#get_sub_organizations) | **GET** /api/orgs/{orgId}/suborgs | ~~Get sub-organizations~~ (deprecated) |
| [**get_user_overview**](OrganizationsApi.md#get_user_overview) | **GET** /api/orgs/{orgId}/users/{userId}/overview | Get user overview and data footprint |
| [**internal_custom_domain_addon**](OrganizationsApi.md#internal_custom_domain_addon) | **POST** /internal/org/custom-domain-addon | Enable/disable Growth/Scale custom domain add-on (internal) |
| [**internal_custom_domain_sweep_status**](OrganizationsApi.md#internal_custom_domain_sweep_status) | **GET** /internal/custom-domain/sweep-status | Custom domain background sweep status (internal) |
| [**internal_domain_dns_recheck_batch**](OrganizationsApi.md#internal_domain_dns_recheck_batch) | **POST** /internal/domain-dns/recheck-batch | Batch DNS re-verification for drift (internal) |
| [**internal_provision_enterprise**](OrganizationsApi.md#internal_provision_enterprise) | **POST** /internal/provision-enterprise | Provision enterprise dedicated API/DB (internal) |
| [**invite_sub_organization_member**](OrganizationsApi.md#invite_sub_organization_member) | **POST** /api/orgs/{orgId}/suborgs/{suborgId}/invite | ~~Invite member to sub-organization~~ (deprecated) |
| [**invite_team_member**](OrganizationsApi.md#invite_team_member) | **POST** /api/orgs/{orgId}/invite | Invite team member to organization |
| [**list_org_custom_domains**](OrganizationsApi.md#list_org_custom_domains) | **GET** /api/orgs/{orgId}/projects/{projectId}/domains | List custom domains and DNS verification hints |
| [**list_organizations**](OrganizationsApi.md#list_organizations) | **GET** /api/orgs | Get all organizations for user |
| [**org_custom_domain_platform_ready**](OrganizationsApi.md#org_custom_domain_platform_ready) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/platform-ready | Notify platform ops that hosting or edge work is ready (email) |
| [**org_custom_domain_submit_cname**](OrganizationsApi.md#org_custom_domain_submit_cname) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/submit-cname | Custom domain step 2 (optional): org confirms routing CNAME was added |
| [**org_custom_domain_submit_platform_dns_verification_deprecated**](OrganizationsApi.md#org_custom_domain_submit_platform_dns_verification_deprecated) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/submit-platform-dns-verification | Deprecated — use POST .../verify-platform-dns |
| [**org_custom_domain_verify_platform_dns**](OrganizationsApi.md#org_custom_domain_verify_platform_dns) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/verify-platform-dns | Custom domain step 3: verify platform DNS (manual TXT or managed certificate readiness) |
| [**patch_org_custom_domain**](OrganizationsApi.md#patch_org_custom_domain) | **PATCH** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname} | Update domain status or regenerate verification token |
| [**remove_sub_organization_member**](OrganizationsApi.md#remove_sub_organization_member) | **DELETE** /api/orgs/{orgId}/suborgs/{suborgId}/members/{userId} | ~~Remove member from sub-organization~~ (deprecated) |
| [**remove_team_member**](OrganizationsApi.md#remove_team_member) | **DELETE** /api/orgs/{orgId}/members/{userId} | Remove team member from organization |
| [**set_org_primary_domain**](OrganizationsApi.md#set_org_primary_domain) | **PATCH** /api/orgs/{orgId}/projects/{projectId}/domains/primary | Set primary custom domain |
| [**update_member_role**](OrganizationsApi.md#update_member_role) | **PATCH** /api/orgs/{orgId}/members/{userId}/role | Update member role |
| [**update_organization**](OrganizationsApi.md#update_organization) | **PATCH** /api/orgs/{orgId} | Update organization |
| [**update_organization_plan**](OrganizationsApi.md#update_organization_plan) | **PATCH** /api/orgs/plan/{orgId} | Update organization plan |
| [**update_sub_organization**](OrganizationsApi.md#update_sub_organization) | **PATCH** /api/orgs/{orgId}/suborgs/{suborgId} | ~~Update sub-organization~~ (deprecated) |
| [**update_sub_organization_member_role**](OrganizationsApi.md#update_sub_organization_member_role) | **PATCH** /api/orgs/{orgId}/suborgs/{suborgId}/members/{userId}/role | ~~Update sub-organization member role~~ (deprecated) |
| [**update_user_account_status**](OrganizationsApi.md#update_user_account_status) | **PATCH** /api/orgs/{orgId}/users/{userId}/status | Update user account status (activate or suspend) |
| [**verify_org_custom_domain_dns**](OrganizationsApi.md#verify_org_custom_domain_dns) | **POST** /api/orgs/{orgId}/projects/{projectId}/domains/{hostname}/verify-dns | Verify domain ownership via DNS TXT |


## add_org_custom_domain

> <OrgAddDomainResponse> add_org_custom_domain(org_id, project_id, add_org_domain_request)

Add a custom domain

Creates a pending domain row; the response **`domain`** uses the compact **`OrgDomainEntryOrgConsole`** shape (**`dnsRecords`** includes the Mudbase ownership TXT). **`dnsRecords`** may include the Mudbase TXT and routing CNAME only until the Mudbase TXT succeeds and the managed certificate is provisioned. **`flyCertificateStatus`** is typically omitted until certificate provisioning runs after the first successful **`verify-dns`**. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
add_org_domain_request = Mudbase::AddOrgDomainRequest.new({hostname: 'hostname_example'}) # AddOrgDomainRequest | 

begin
  # Add a custom domain
  result = api_instance.add_org_custom_domain(org_id, project_id, add_org_domain_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->add_org_custom_domain: #{e}"
end
```

#### Using the add_org_custom_domain_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgAddDomainResponse>, Integer, Hash)> add_org_custom_domain_with_http_info(org_id, project_id, add_org_domain_request)

```ruby
begin
  # Add a custom domain
  data, status_code, headers = api_instance.add_org_custom_domain_with_http_info(org_id, project_id, add_org_domain_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgAddDomainResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->add_org_custom_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **add_org_domain_request** | [**AddOrgDomainRequest**](AddOrgDomainRequest.md) |  |  |

### Return type

[**OrgAddDomainResponse**](OrgAddDomainResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization

> create_organization(create_organization_request)

~~Create new organization~~ (disabled)

~~Create a new organization.~~ This endpoint is disabled and kept only for backward compatibility in documentation. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
create_organization_request = Mudbase::CreateOrganizationRequest.new({name: 'Mudbase Inc'}) # CreateOrganizationRequest | 

begin
  # ~~Create new organization~~ (disabled)
  api_instance.create_organization(create_organization_request)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization: #{e}"
end
```

#### Using the create_organization_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_organization_with_http_info(create_organization_request)

```ruby
begin
  # ~~Create new organization~~ (disabled)
  data, status_code, headers = api_instance.create_organization_with_http_info(create_organization_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_organization_request** | [**CreateOrganizationRequest**](CreateOrganizationRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_org_custom_domain

> delete_org_custom_domain(org_id, project_id, hostname)

Remove a custom domain

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Remove a custom domain
  api_instance.delete_org_custom_domain(org_id, project_id, hostname)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_org_custom_domain: #{e}"
end
```

#### Using the delete_org_custom_domain_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_org_custom_domain_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Remove a custom domain
  data, status_code, headers = api_instance.delete_org_custom_domain_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_org_custom_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## delete_organization

> <DeleteOrganization200Response> delete_organization(org_id)

Delete organization

Delete an organization permanently. This is a destructive operation. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # Delete organization
  result = api_instance.delete_organization(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization: #{e}"
end
```

#### Using the delete_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteOrganization200Response>, Integer, Hash)> delete_organization_with_http_info(org_id)

```ruby
begin
  # Delete organization
  data, status_code, headers = api_instance.delete_organization_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteOrganization200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**DeleteOrganization200Response**](DeleteOrganization200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_sub_organization

> <DeleteSubOrganization200Response> delete_sub_organization(org_id, suborg_id)

~~Delete sub-organization~~ (deprecated)

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
suborg_id = '685acbe0e129932fbb7a0fc4' # String | 

begin
  # ~~Delete sub-organization~~ (deprecated)
  result = api_instance.delete_sub_organization(org_id, suborg_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_sub_organization: #{e}"
end
```

#### Using the delete_sub_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteSubOrganization200Response>, Integer, Hash)> delete_sub_organization_with_http_info(org_id, suborg_id)

```ruby
begin
  # ~~Delete sub-organization~~ (deprecated)
  data, status_code, headers = api_instance.delete_sub_organization_with_http_info(org_id, suborg_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteSubOrganization200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->delete_sub_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **suborg_id** | **String** |  |  |

### Return type

[**DeleteSubOrganization200Response**](DeleteSubOrganization200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_org_custom_domain_dns_instructions

> <OrgDnsInstructionsResponse> get_org_custom_domain_dns_instructions(org_id, project_id, hostname)

Get DNS TXT record instructions for one hostname

Returns the same shape as list/add for one hostname (URL-encode `hostname` in the path), including **`dnsRecords`** and **`flyCertificateStatus`** when applicable. See **`listOrgCustomDomains`** for how managed certificate provisioning affects those fields. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Get DNS TXT record instructions for one hostname
  result = api_instance.get_org_custom_domain_dns_instructions(org_id, project_id, hostname)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_org_custom_domain_dns_instructions: #{e}"
end
```

#### Using the get_org_custom_domain_dns_instructions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgDnsInstructionsResponse>, Integer, Hash)> get_org_custom_domain_dns_instructions_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Get DNS TXT record instructions for one hostname
  data, status_code, headers = api_instance.get_org_custom_domain_dns_instructions_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgDnsInstructionsResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_org_custom_domain_dns_instructions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

[**OrgDnsInstructionsResponse**](OrgDnsInstructionsResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization

> <Organization> get_organization(org_id)

Get organization details by ID

Get organization details by ID. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # Get organization details by ID
  result = api_instance.get_organization(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization: #{e}"
end
```

#### Using the get_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Organization>, Integer, Hash)> get_organization_with_http_info(org_id)

```ruby
begin
  # Get organization details by ID
  data, status_code, headers = api_instance.get_organization_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Organization>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**Organization**](Organization.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization_members

> <GetOrganizationMembers200Response> get_organization_members(org_id)

Get organization members

Get all members of an organization. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # Get organization members
  result = api_instance.get_organization_members(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_members: #{e}"
end
```

#### Using the get_organization_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOrganizationMembers200Response>, Integer, Hash)> get_organization_members_with_http_info(org_id)

```ruby
begin
  # Get organization members
  data, status_code, headers = api_instance.get_organization_members_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOrganizationMembers200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**GetOrganizationMembers200Response**](GetOrganizationMembers200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization_usage

> <GetOrganizationUsage200Response> get_organization_usage(org_id)

Get organization usage and billing

Get usage statistics and billing information for an organization. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # Get organization usage and billing
  result = api_instance.get_organization_usage(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_usage: #{e}"
end
```

#### Using the get_organization_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOrganizationUsage200Response>, Integer, Hash)> get_organization_usage_with_http_info(org_id)

```ruby
begin
  # Get organization usage and billing
  data, status_code, headers = api_instance.get_organization_usage_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOrganizationUsage200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**GetOrganizationUsage200Response**](GetOrganizationUsage200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization_users

> <GetOrganizationUsers200Response> get_organization_users(org_id, opts)

List organization users with metadata

Get all users in the organization with metadata (email, full name, role, accountStatus, phone, lastLogin, etc.). Optional query `status` filters by accountStatus (pending, active, suspended). Requires organization access and owner or admin role. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
opts = {
  status: 'pending' # String | Filter by account status (pending, active, suspended)
}

begin
  # List organization users with metadata
  result = api_instance.get_organization_users(org_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_users: #{e}"
end
```

#### Using the get_organization_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOrganizationUsers200Response>, Integer, Hash)> get_organization_users_with_http_info(org_id, opts)

```ruby
begin
  # List organization users with metadata
  data, status_code, headers = api_instance.get_organization_users_with_http_info(org_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOrganizationUsers200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_users_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **status** | **String** | Filter by account status (pending, active, suspended) | [optional] |

### Return type

[**GetOrganizationUsers200Response**](GetOrganizationUsers200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_users

> <GetProjectUsers200Response> get_project_users(org_id, project_id, opts)

List project users with metadata

Get all users in a project with metadata (email, full name, role, accountStatus, etc.). Optional query `status` filters by accountStatus. Project must belong to the organization. Requires owner or admin role. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
project_id = '685ad30be129932fbb7a1047' # String | 
opts = {
  status: 'pending' # String | Filter by account status (pending, active, suspended)
}

begin
  # List project users with metadata
  result = api_instance.get_project_users(org_id, project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_project_users: #{e}"
end
```

#### Using the get_project_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetProjectUsers200Response>, Integer, Hash)> get_project_users_with_http_info(org_id, project_id, opts)

```ruby
begin
  # List project users with metadata
  data, status_code, headers = api_instance.get_project_users_with_http_info(org_id, project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetProjectUsers200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_project_users_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **status** | **String** | Filter by account status (pending, active, suspended) | [optional] |

### Return type

[**GetProjectUsers200Response**](GetProjectUsers200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_sub_organizations

> <GetSubOrganizations200Response> get_sub_organizations(org_id)

~~Get sub-organizations~~ (deprecated)

Get all sub-organizations under a parent organization. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 

begin
  # ~~Get sub-organizations~~ (deprecated)
  result = api_instance.get_sub_organizations(org_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_sub_organizations: #{e}"
end
```

#### Using the get_sub_organizations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSubOrganizations200Response>, Integer, Hash)> get_sub_organizations_with_http_info(org_id)

```ruby
begin
  # ~~Get sub-organizations~~ (deprecated)
  data, status_code, headers = api_instance.get_sub_organizations_with_http_info(org_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSubOrganizations200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_sub_organizations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |

### Return type

[**GetSubOrganizations200Response**](GetSubOrganizations200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_user_overview

> <GetUserOverview200Response> get_user_overview(org_id, user_id)

Get user overview and data footprint

Get a user's profile plus footprint (files count/size, sessions, API keys, collections in project). Use for dashboard to see everything tied to the user. Requires owner or admin role. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
user_id = 'user_id_example' # String | 

begin
  # Get user overview and data footprint
  result = api_instance.get_user_overview(org_id, user_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_user_overview: #{e}"
end
```

#### Using the get_user_overview_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUserOverview200Response>, Integer, Hash)> get_user_overview_with_http_info(org_id, user_id)

```ruby
begin
  # Get user overview and data footprint
  data, status_code, headers = api_instance.get_user_overview_with_http_info(org_id, user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUserOverview200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->get_user_overview_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |

### Return type

[**GetUserOverview200Response**](GetUserOverview200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## internal_custom_domain_addon

> internal_custom_domain_addon(internal_custom_domain_addon_request)

Enable/disable Growth/Scale custom domain add-on (internal)

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: InternalApiKey
  config.api_key['X-Internal-Api-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-Internal-Api-Key'] = 'Bearer'
end

api_instance = Mudbase::OrganizationsApi.new
internal_custom_domain_addon_request = Mudbase::InternalCustomDomainAddonRequest.new({org_id: 'org_id_example', enabled: false}) # InternalCustomDomainAddonRequest | 

begin
  # Enable/disable Growth/Scale custom domain add-on (internal)
  api_instance.internal_custom_domain_addon(internal_custom_domain_addon_request)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_custom_domain_addon: #{e}"
end
```

#### Using the internal_custom_domain_addon_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> internal_custom_domain_addon_with_http_info(internal_custom_domain_addon_request)

```ruby
begin
  # Enable/disable Growth/Scale custom domain add-on (internal)
  data, status_code, headers = api_instance.internal_custom_domain_addon_with_http_info(internal_custom_domain_addon_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_custom_domain_addon_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **internal_custom_domain_addon_request** | [**InternalCustomDomainAddonRequest**](InternalCustomDomainAddonRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[InternalApiKey](../README.md#InternalApiKey)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## internal_custom_domain_sweep_status

> internal_custom_domain_sweep_status

Custom domain background sweep status (internal)

Returns the last automated custom-domain sweep (TXT recheck + certificate provisioning retry), job env flags, and deploy troubleshooting hints when the proxy reports the app is not listening on 0.0.0.0:PORT. Requires header `X-Internal-Api-Key` (same as other /internal routes).

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: InternalApiKey
  config.api_key['X-Internal-Api-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-Internal-Api-Key'] = 'Bearer'
end

api_instance = Mudbase::OrganizationsApi.new

begin
  # Custom domain background sweep status (internal)
  api_instance.internal_custom_domain_sweep_status
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_custom_domain_sweep_status: #{e}"
end
```

#### Using the internal_custom_domain_sweep_status_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> internal_custom_domain_sweep_status_with_http_info

```ruby
begin
  # Custom domain background sweep status (internal)
  data, status_code, headers = api_instance.internal_custom_domain_sweep_status_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_custom_domain_sweep_status_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[InternalApiKey](../README.md#InternalApiKey)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## internal_domain_dns_recheck_batch

> internal_domain_dns_recheck_batch(opts)

Batch DNS re-verification for drift (internal)

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: InternalApiKey
  config.api_key['X-Internal-Api-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-Internal-Api-Key'] = 'Bearer'
end

api_instance = Mudbase::OrganizationsApi.new
opts = {
  internal_domain_dns_recheck_batch_request: Mudbase::InternalDomainDnsRecheckBatchRequest.new # InternalDomainDnsRecheckBatchRequest | 
}

begin
  # Batch DNS re-verification for drift (internal)
  api_instance.internal_domain_dns_recheck_batch(opts)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_domain_dns_recheck_batch: #{e}"
end
```

#### Using the internal_domain_dns_recheck_batch_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> internal_domain_dns_recheck_batch_with_http_info(opts)

```ruby
begin
  # Batch DNS re-verification for drift (internal)
  data, status_code, headers = api_instance.internal_domain_dns_recheck_batch_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_domain_dns_recheck_batch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **internal_domain_dns_recheck_batch_request** | [**InternalDomainDnsRecheckBatchRequest**](InternalDomainDnsRecheckBatchRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[InternalApiKey](../README.md#InternalApiKey)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## internal_provision_enterprise

> internal_provision_enterprise(provision_enterprise_request)

Provision enterprise dedicated API/DB (internal)

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: InternalApiKey
  config.api_key['X-Internal-Api-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-Internal-Api-Key'] = 'Bearer'
end

api_instance = Mudbase::OrganizationsApi.new
provision_enterprise_request = Mudbase::ProvisionEnterpriseRequest.new({org_id: 'org_id_example', provision_request_id: 'provision_request_id_example', api_base_url: 'api_base_url_example', db_ref: 'db_ref_example', server_id: 'server_id_example'}) # ProvisionEnterpriseRequest | 

begin
  # Provision enterprise dedicated API/DB (internal)
  api_instance.internal_provision_enterprise(provision_enterprise_request)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_provision_enterprise: #{e}"
end
```

#### Using the internal_provision_enterprise_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> internal_provision_enterprise_with_http_info(provision_enterprise_request)

```ruby
begin
  # Provision enterprise dedicated API/DB (internal)
  data, status_code, headers = api_instance.internal_provision_enterprise_with_http_info(provision_enterprise_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->internal_provision_enterprise_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provision_enterprise_request** | [**ProvisionEnterpriseRequest**](ProvisionEnterpriseRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[InternalApiKey](../README.md#InternalApiKey)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## invite_sub_organization_member

> <InviteSubOrganizationMember200Response> invite_sub_organization_member(org_id, suborg_id, invite_member_request)

~~Invite member to sub-organization~~ (deprecated)

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
suborg_id = '685acbe0e129932fbb7a0fc4' # String | 
invite_member_request = Mudbase::InviteMemberRequest.new({email: 'email_example', role: 'admin'}) # InviteMemberRequest | 

begin
  # ~~Invite member to sub-organization~~ (deprecated)
  result = api_instance.invite_sub_organization_member(org_id, suborg_id, invite_member_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->invite_sub_organization_member: #{e}"
end
```

#### Using the invite_sub_organization_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InviteSubOrganizationMember200Response>, Integer, Hash)> invite_sub_organization_member_with_http_info(org_id, suborg_id, invite_member_request)

```ruby
begin
  # ~~Invite member to sub-organization~~ (deprecated)
  data, status_code, headers = api_instance.invite_sub_organization_member_with_http_info(org_id, suborg_id, invite_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InviteSubOrganizationMember200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->invite_sub_organization_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **suborg_id** | **String** |  |  |
| **invite_member_request** | [**InviteMemberRequest**](InviteMemberRequest.md) |  |  |

### Return type

[**InviteSubOrganizationMember200Response**](InviteSubOrganizationMember200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## invite_team_member

> <InviteTeamMember200Response> invite_team_member(org_id, invite_member_request)

Invite team member to organization

Send an invitation to a user to join the organization. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
invite_member_request = Mudbase::InviteMemberRequest.new({email: 'email_example', role: 'admin'}) # InviteMemberRequest | 

begin
  # Invite team member to organization
  result = api_instance.invite_team_member(org_id, invite_member_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->invite_team_member: #{e}"
end
```

#### Using the invite_team_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InviteTeamMember200Response>, Integer, Hash)> invite_team_member_with_http_info(org_id, invite_member_request)

```ruby
begin
  # Invite team member to organization
  data, status_code, headers = api_instance.invite_team_member_with_http_info(org_id, invite_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InviteTeamMember200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->invite_team_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **invite_member_request** | [**InviteMemberRequest**](InviteMemberRequest.md) |  |  |

### Return type

[**InviteTeamMember200Response**](InviteTeamMember200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_org_custom_domains

> <OrgDomainsListResponse> list_org_custom_domains(org_id, project_id)

List custom domains and DNS verification hints

Returns allowed hostnames for **this project**, primary hostname (per project), API base URL, and per-domain DNS guidance.  Each row uses **`dnsRecords`** for the Mudbase ownership TXT (purpose **`mudbase_ownership`**) and the routing **CNAME** target that Mudbase provisions for the hostname (else the platform default target). Once the ownership TXT has passed at least once, Mudbase provisions and manages the TLS certificate for the hostname automatically and may add further checklist rows (for example `acme_challenge`) needed to complete certificate issuance. The certificate status field mirrors the managed certificate’s state during issuance (e.g. `pending_validation`, `active`).  Managed edge TLS details are present only on deployments that serve managed edge certificates.  Requires Growth, Scale, or Enterprise plan (custom domains included in plan features). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 

begin
  # List custom domains and DNS verification hints
  result = api_instance.list_org_custom_domains(org_id, project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->list_org_custom_domains: #{e}"
end
```

#### Using the list_org_custom_domains_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgDomainsListResponse>, Integer, Hash)> list_org_custom_domains_with_http_info(org_id, project_id)

```ruby
begin
  # List custom domains and DNS verification hints
  data, status_code, headers = api_instance.list_org_custom_domains_with_http_info(org_id, project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgDomainsListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->list_org_custom_domains_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |

### Return type

[**OrgDomainsListResponse**](OrgDomainsListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organizations

> <ListOrganizations200Response> list_organizations

Get all organizations for user

Get all organizations the authenticated user belongs to. Requires: OrgBearerAuth (organization-level authentication only). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new

begin
  # Get all organizations for user
  result = api_instance.list_organizations
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->list_organizations: #{e}"
end
```

#### Using the list_organizations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListOrganizations200Response>, Integer, Hash)> list_organizations_with_http_info

```ruby
begin
  # Get all organizations for user
  data, status_code, headers = api_instance.list_organizations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListOrganizations200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->list_organizations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListOrganizations200Response**](ListOrganizations200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## org_custom_domain_platform_ready

> org_custom_domain_platform_ready(org_id, project_id, hostname, opts)

Notify platform ops that hosting or edge work is ready (email)

Legacy optional ping: ops are emailed automatically on first successful Mudbase TXT verify. Use this only for an extra nudge. Sends an email to ops while the domain is in platform setup (after Mudbase TXT verification through later pipeline states). Recipients default to `admin@mudhaxkservices.com` and `admin@mudbase.dev` when `CUSTOM_DOMAIN_OPS_NOTIFY_EMAILS` is unset; override with that env (comma/space-separated). Returns **503** `email_provider_not_configured` if the platform email provider is not configured. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 
opts = {
  org_custom_domain_platform_ready_request: Mudbase::OrgCustomDomainPlatformReadyRequest.new # OrgCustomDomainPlatformReadyRequest | 
}

begin
  # Notify platform ops that hosting or edge work is ready (email)
  api_instance.org_custom_domain_platform_ready(org_id, project_id, hostname, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_platform_ready: #{e}"
end
```

#### Using the org_custom_domain_platform_ready_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> org_custom_domain_platform_ready_with_http_info(org_id, project_id, hostname, opts)

```ruby
begin
  # Notify platform ops that hosting or edge work is ready (email)
  data, status_code, headers = api_instance.org_custom_domain_platform_ready_with_http_info(org_id, project_id, hostname, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_platform_ready_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |
| **org_custom_domain_platform_ready_request** | [**OrgCustomDomainPlatformReadyRequest**](OrgCustomDomainPlatformReadyRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## org_custom_domain_submit_cname

> <OrgPatchDomainResponse> org_custom_domain_submit_cname(org_id, project_id, hostname)

Custom domain step 2 (optional): org confirms routing CNAME was added

Usually unnecessary. With automated certificate provisioning, the Mudbase TXT verify may already set `cname_approved`. Legacy pipelines may queue `cname_pending_staff` until staff **`approve-cname`**. Use **`routingCnameTarget`** from **`GET .../projects/{projectId}/domains`** (the managed routing CNAME target when provisioned, else the platform default target). 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Custom domain step 2 (optional): org confirms routing CNAME was added
  result = api_instance.org_custom_domain_submit_cname(org_id, project_id, hostname)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_submit_cname: #{e}"
end
```

#### Using the org_custom_domain_submit_cname_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgPatchDomainResponse>, Integer, Hash)> org_custom_domain_submit_cname_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Custom domain step 2 (optional): org confirms routing CNAME was added
  data, status_code, headers = api_instance.org_custom_domain_submit_cname_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgPatchDomainResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_submit_cname_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

[**OrgPatchDomainResponse**](OrgPatchDomainResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## org_custom_domain_submit_platform_dns_verification_deprecated

> <OrgPatchDomainResponse> org_custom_domain_submit_platform_dns_verification_deprecated(org_id, project_id, hostname)

Deprecated — use POST .../verify-platform-dns

Deprecated alias of **`orgCustomDomainVerifyPlatformDns`** (same behavior: manual TXT and/or automated certificate provisioning per deployment).

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Deprecated — use POST .../verify-platform-dns
  result = api_instance.org_custom_domain_submit_platform_dns_verification_deprecated(org_id, project_id, hostname)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_submit_platform_dns_verification_deprecated: #{e}"
end
```

#### Using the org_custom_domain_submit_platform_dns_verification_deprecated_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgPatchDomainResponse>, Integer, Hash)> org_custom_domain_submit_platform_dns_verification_deprecated_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Deprecated — use POST .../verify-platform-dns
  data, status_code, headers = api_instance.org_custom_domain_submit_platform_dns_verification_deprecated_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgPatchDomainResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_submit_platform_dns_verification_deprecated_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

[**OrgPatchDomainResponse**](OrgPatchDomainResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## org_custom_domain_verify_platform_dns

> <OrgPatchDomainResponse> org_custom_domain_verify_platform_dns(org_id, project_id, hostname)

Custom domain step 3: verify platform DNS (manual TXT or managed certificate readiness)

**Manual path:** After staff **`PATCH .../platform-dns-verification`**, the org adds the published TXT and calls this endpoint. The API resolves public TXT at **`platformDnsVerification.recordName`** and matches **`recordValue`**. On success, `status` → **`platform_dns_pending_review`** until staff **`POST .../activate`**.  **Automated path (default):** When automated certificate provisioning is in effect, the org calls this after the Mudbase TXT and the certificate DNS rows are in place (status typically **`cname_approved`** from automated verify-dns). The API checks the managed certificate with bounded retries. On success, `status` → **`active`** and the org may receive the activation email, with no staff **`approve-cname`** or **`activate`** required.  **Legacy path:** In the legacy staff pipeline, staff **`approve-cname`** may be required first; after the managed certificate is ready, **`status`** becomes **`active`** on auto-activation, else **`platform_dns_pending_review`** until staff **`activate`**.  **`platform_dns_verification_failed`** may include **`details.flyStatus`** / **`details.flyError`** with provisioning error context. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Custom domain step 3: verify platform DNS (manual TXT or managed certificate readiness)
  result = api_instance.org_custom_domain_verify_platform_dns(org_id, project_id, hostname)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_verify_platform_dns: #{e}"
end
```

#### Using the org_custom_domain_verify_platform_dns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgPatchDomainResponse>, Integer, Hash)> org_custom_domain_verify_platform_dns_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Custom domain step 3: verify platform DNS (manual TXT or managed certificate readiness)
  data, status_code, headers = api_instance.org_custom_domain_verify_platform_dns_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgPatchDomainResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->org_custom_domain_verify_platform_dns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

[**OrgPatchDomainResponse**](OrgPatchDomainResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## patch_org_custom_domain

> <OrgPatchDomainResponse> patch_org_custom_domain(org_id, project_id, hostname, opts)

Update domain status or regenerate verification token

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 
opts = {
  patch_org_domain_request: Mudbase::PatchOrgDomainRequest.new # PatchOrgDomainRequest | 
}

begin
  # Update domain status or regenerate verification token
  result = api_instance.patch_org_custom_domain(org_id, project_id, hostname, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->patch_org_custom_domain: #{e}"
end
```

#### Using the patch_org_custom_domain_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgPatchDomainResponse>, Integer, Hash)> patch_org_custom_domain_with_http_info(org_id, project_id, hostname, opts)

```ruby
begin
  # Update domain status or regenerate verification token
  data, status_code, headers = api_instance.patch_org_custom_domain_with_http_info(org_id, project_id, hostname, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgPatchDomainResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->patch_org_custom_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |
| **patch_org_domain_request** | [**PatchOrgDomainRequest**](PatchOrgDomainRequest.md) |  | [optional] |

### Return type

[**OrgPatchDomainResponse**](OrgPatchDomainResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_sub_organization_member

> <RemoveTeamMember200Response> remove_sub_organization_member(org_id, suborg_id, user_id)

~~Remove member from sub-organization~~ (deprecated)

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
suborg_id = '685acbe0e129932fbb7a0fc4' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 

begin
  # ~~Remove member from sub-organization~~ (deprecated)
  result = api_instance.remove_sub_organization_member(org_id, suborg_id, user_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->remove_sub_organization_member: #{e}"
end
```

#### Using the remove_sub_organization_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveTeamMember200Response>, Integer, Hash)> remove_sub_organization_member_with_http_info(org_id, suborg_id, user_id)

```ruby
begin
  # ~~Remove member from sub-organization~~ (deprecated)
  data, status_code, headers = api_instance.remove_sub_organization_member_with_http_info(org_id, suborg_id, user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveTeamMember200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->remove_sub_organization_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **suborg_id** | **String** |  |  |
| **user_id** | **String** |  |  |

### Return type

[**RemoveTeamMember200Response**](RemoveTeamMember200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_team_member

> <RemoveTeamMember200Response> remove_team_member(org_id, user_id)

Remove team member from organization

Remove a user from the organization. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 

begin
  # Remove team member from organization
  result = api_instance.remove_team_member(org_id, user_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->remove_team_member: #{e}"
end
```

#### Using the remove_team_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveTeamMember200Response>, Integer, Hash)> remove_team_member_with_http_info(org_id, user_id)

```ruby
begin
  # Remove team member from organization
  data, status_code, headers = api_instance.remove_team_member_with_http_info(org_id, user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveTeamMember200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->remove_team_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |

### Return type

[**RemoveTeamMember200Response**](RemoveTeamMember200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## set_org_primary_domain

> set_org_primary_domain(org_id, project_id, set_org_primary_domain_request)

Set primary custom domain

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
set_org_primary_domain_request = Mudbase::SetOrgPrimaryDomainRequest.new({hostname: 'hostname_example'}) # SetOrgPrimaryDomainRequest | 

begin
  # Set primary custom domain
  api_instance.set_org_primary_domain(org_id, project_id, set_org_primary_domain_request)
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->set_org_primary_domain: #{e}"
end
```

#### Using the set_org_primary_domain_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> set_org_primary_domain_with_http_info(org_id, project_id, set_org_primary_domain_request)

```ruby
begin
  # Set primary custom domain
  data, status_code, headers = api_instance.set_org_primary_domain_with_http_info(org_id, project_id, set_org_primary_domain_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->set_org_primary_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **set_org_primary_domain_request** | [**SetOrgPrimaryDomainRequest**](SetOrgPrimaryDomainRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not defined


## update_member_role

> <UpdateMemberRole200Response> update_member_role(org_id, user_id, update_member_role_request)

Update member role

Update a member's role in the organization. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 
update_member_role_request = Mudbase::UpdateMemberRoleRequest.new({role: 'owner'}) # UpdateMemberRoleRequest | 

begin
  # Update member role
  result = api_instance.update_member_role(org_id, user_id, update_member_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_member_role: #{e}"
end
```

#### Using the update_member_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateMemberRole200Response>, Integer, Hash)> update_member_role_with_http_info(org_id, user_id, update_member_role_request)

```ruby
begin
  # Update member role
  data, status_code, headers = api_instance.update_member_role_with_http_info(org_id, user_id, update_member_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateMemberRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_member_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **update_member_role_request** | [**UpdateMemberRoleRequest**](UpdateMemberRoleRequest.md) |  |  |

### Return type

[**UpdateMemberRole200Response**](UpdateMemberRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_organization

> <UpdateOrganization200Response> update_organization(org_id, update_organization_request)

Update organization

Update organization details. Requires organization-level authentication (JWT Bearer token). API keys are not supported for this endpoint. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
update_organization_request = Mudbase::UpdateOrganizationRequest.new # UpdateOrganizationRequest | 

begin
  # Update organization
  result = api_instance.update_organization(org_id, update_organization_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization: #{e}"
end
```

#### Using the update_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateOrganization200Response>, Integer, Hash)> update_organization_with_http_info(org_id, update_organization_request)

```ruby
begin
  # Update organization
  data, status_code, headers = api_instance.update_organization_with_http_info(org_id, update_organization_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateOrganization200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **update_organization_request** | [**UpdateOrganizationRequest**](UpdateOrganizationRequest.md) |  |  |

### Return type

[**UpdateOrganization200Response**](UpdateOrganization200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_organization_plan

> <UpdateOrganizationPlan200Response> update_organization_plan(org_id, update_organization_plan_request)

Update organization plan

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
update_organization_plan_request = Mudbase::UpdateOrganizationPlanRequest.new({plan: 'free'}) # UpdateOrganizationPlanRequest | 

begin
  # Update organization plan
  result = api_instance.update_organization_plan(org_id, update_organization_plan_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_plan: #{e}"
end
```

#### Using the update_organization_plan_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateOrganizationPlan200Response>, Integer, Hash)> update_organization_plan_with_http_info(org_id, update_organization_plan_request)

```ruby
begin
  # Update organization plan
  data, status_code, headers = api_instance.update_organization_plan_with_http_info(org_id, update_organization_plan_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateOrganizationPlan200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_plan_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **update_organization_plan_request** | [**UpdateOrganizationPlanRequest**](UpdateOrganizationPlanRequest.md) |  |  |

### Return type

[**UpdateOrganizationPlan200Response**](UpdateOrganizationPlan200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sub_organization

> <UpdateSubOrganization200Response> update_sub_organization(org_id, suborg_id, update_organization_request)

~~Update sub-organization~~ (deprecated)

Update a sub-organization's configuration. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). These are organization-level operations. 

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
suborg_id = '685acbe0e129932fbb7a0fc4' # String | 
update_organization_request = Mudbase::UpdateOrganizationRequest.new # UpdateOrganizationRequest | 

begin
  # ~~Update sub-organization~~ (deprecated)
  result = api_instance.update_sub_organization(org_id, suborg_id, update_organization_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_sub_organization: #{e}"
end
```

#### Using the update_sub_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSubOrganization200Response>, Integer, Hash)> update_sub_organization_with_http_info(org_id, suborg_id, update_organization_request)

```ruby
begin
  # ~~Update sub-organization~~ (deprecated)
  data, status_code, headers = api_instance.update_sub_organization_with_http_info(org_id, suborg_id, update_organization_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSubOrganization200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_sub_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **suborg_id** | **String** |  |  |
| **update_organization_request** | [**UpdateOrganizationRequest**](UpdateOrganizationRequest.md) |  |  |

### Return type

[**UpdateSubOrganization200Response**](UpdateSubOrganization200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sub_organization_member_role

> <UpdateMemberRole200Response> update_sub_organization_member_role(org_id, suborg_id, user_id, update_member_role_request)

~~Update sub-organization member role~~ (deprecated)

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

api_instance = Mudbase::OrganizationsApi.new
org_id = '685acbe0e129932fbb7a0fc3' # String | 
suborg_id = '685acbe0e129932fbb7a0fc4' # String | 
user_id = '685acbe0e129932fbb7a0fc2' # String | 
update_member_role_request = Mudbase::UpdateMemberRoleRequest.new({role: 'owner'}) # UpdateMemberRoleRequest | 

begin
  # ~~Update sub-organization member role~~ (deprecated)
  result = api_instance.update_sub_organization_member_role(org_id, suborg_id, user_id, update_member_role_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_sub_organization_member_role: #{e}"
end
```

#### Using the update_sub_organization_member_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateMemberRole200Response>, Integer, Hash)> update_sub_organization_member_role_with_http_info(org_id, suborg_id, user_id, update_member_role_request)

```ruby
begin
  # ~~Update sub-organization member role~~ (deprecated)
  data, status_code, headers = api_instance.update_sub_organization_member_role_with_http_info(org_id, suborg_id, user_id, update_member_role_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateMemberRole200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_sub_organization_member_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **suborg_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **update_member_role_request** | [**UpdateMemberRoleRequest**](UpdateMemberRoleRequest.md) |  |  |

### Return type

[**UpdateMemberRole200Response**](UpdateMemberRole200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_user_account_status

> <UpdateUserAccountStatus200Response> update_user_account_status(org_id, user_id, update_user_account_status_request)

Update user account status (activate or suspend)

Set a user's account status to active or suspended. Used to approve pending users or suspend/activate accounts. Cannot change status of an organization owner. Requires owner or admin role. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
user_id = 'user_id_example' # String | 
update_user_account_status_request = Mudbase::UpdateUserAccountStatusRequest.new({account_status: 'active'}) # UpdateUserAccountStatusRequest | 

begin
  # Update user account status (activate or suspend)
  result = api_instance.update_user_account_status(org_id, user_id, update_user_account_status_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_user_account_status: #{e}"
end
```

#### Using the update_user_account_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateUserAccountStatus200Response>, Integer, Hash)> update_user_account_status_with_http_info(org_id, user_id, update_user_account_status_request)

```ruby
begin
  # Update user account status (activate or suspend)
  data, status_code, headers = api_instance.update_user_account_status_with_http_info(org_id, user_id, update_user_account_status_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateUserAccountStatus200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->update_user_account_status_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **update_user_account_status_request** | [**UpdateUserAccountStatusRequest**](UpdateUserAccountStatusRequest.md) |  |  |

### Return type

[**UpdateUserAccountStatus200Response**](UpdateUserAccountStatus200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_org_custom_domain_dns

> <OrgVerifyCustomDomainDnsSuccessResponse> verify_org_custom_domain_dns(org_id, project_id, hostname)

Verify domain ownership via DNS TXT

Looks up TXT at `_mudbase-verify.<hostname>` for value `mudbase-domain-verification=<token>`.  On a successful verify, Mudbase begins provisioning and managing the TLS certificate for the hostname automatically. Depending on the deployment, the response may include managed edge TLS details with domain-control validation (DCV) hints for the certificate.  When automated certificate provisioning is in effect, a successful verify records the certificate’s DNS requirements and status may advance to **`cname_approved`** in the same response (no staff **`approve-cname`** step). Otherwise, first success from `pending`/`failed` may move to **`cname_pending_staff`** and queue platform review as before.  The **200** response may include **`dnsRecords`**, certificate status, and **`routingCnameTarget`** for the managed certificate once its requirements are provisioned. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::OrganizationsApi.new
org_id = 'org_id_example' # String | 
project_id = 'project_id_example' # String | 
hostname = 'hostname_example' # String | 

begin
  # Verify domain ownership via DNS TXT
  result = api_instance.verify_org_custom_domain_dns(org_id, project_id, hostname)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->verify_org_custom_domain_dns: #{e}"
end
```

#### Using the verify_org_custom_domain_dns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrgVerifyCustomDomainDnsSuccessResponse>, Integer, Hash)> verify_org_custom_domain_dns_with_http_info(org_id, project_id, hostname)

```ruby
begin
  # Verify domain ownership via DNS TXT
  data, status_code, headers = api_instance.verify_org_custom_domain_dns_with_http_info(org_id, project_id, hostname)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrgVerifyCustomDomainDnsSuccessResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling OrganizationsApi->verify_org_custom_domain_dns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **project_id** | **String** |  |  |
| **hostname** | **String** |  |  |

### Return type

[**OrgVerifyCustomDomainDnsSuccessResponse**](OrgVerifyCustomDomainDnsSuccessResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

