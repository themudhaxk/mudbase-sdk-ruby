# Mudbase::VerifiedRoleUpgradeApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**verified_role_upgrade**](VerifiedRoleUpgradeApi.md#verified_role_upgrade) | **POST** /api/orgs/{orgId}/users/{userId}/upgrade | Verified role upgrade with payment verification |


## verified_role_upgrade

> <VerifiedRoleUpgrade200Response> verified_role_upgrade(org_id, user_id, verified_role_upgrade_request)

Verified role upgrade with payment verification

Upgrade user role after verifying payment. Prevents replay attacks.

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

api_instance = Mudbase::VerifiedRoleUpgradeApi.new
org_id = 'org_id_example' # String | 
user_id = 'user_id_example' # String | 
verified_role_upgrade_request = Mudbase::VerifiedRoleUpgradeRequest.new({target_role: 'seller'}) # VerifiedRoleUpgradeRequest | 

begin
  # Verified role upgrade with payment verification
  result = api_instance.verified_role_upgrade(org_id, user_id, verified_role_upgrade_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling VerifiedRoleUpgradeApi->verified_role_upgrade: #{e}"
end
```

#### Using the verified_role_upgrade_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VerifiedRoleUpgrade200Response>, Integer, Hash)> verified_role_upgrade_with_http_info(org_id, user_id, verified_role_upgrade_request)

```ruby
begin
  # Verified role upgrade with payment verification
  data, status_code, headers = api_instance.verified_role_upgrade_with_http_info(org_id, user_id, verified_role_upgrade_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VerifiedRoleUpgrade200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling VerifiedRoleUpgradeApi->verified_role_upgrade_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **verified_role_upgrade_request** | [**VerifiedRoleUpgradeRequest**](VerifiedRoleUpgradeRequest.md) |  |  |

### Return type

[**VerifiedRoleUpgrade200Response**](VerifiedRoleUpgrade200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

