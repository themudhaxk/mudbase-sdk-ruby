# Mudbase::UsersApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**api_me_bootstrap_get**](UsersApi.md#api_me_bootstrap_get) | **GET** /api/me/bootstrap | Dashboard bootstrap (session + orgs + default org + projects) |
| [**change_password**](UsersApi.md#change_password) | **PATCH** /api/users/password | Change password |
| [**disable2_fa**](UsersApi.md#disable2_fa) | **POST** /api/users/2fa/disable | Disable 2FA |
| [**erase_user_data**](UsersApi.md#erase_user_data) | **POST** /api/users/me/erase | Delete user data (GDPR Article 17) |
| [**export_user_data**](UsersApi.md#export_user_data) | **GET** /api/users/me/export | Export user data (GDPR Article 15) |
| [**get_current_user**](UsersApi.md#get_current_user) | **GET** /api/users/me | Get current user profile |
| [**link_o_auth_provider**](UsersApi.md#link_o_auth_provider) | **GET** /api/users/me/oauth-providers/link/{provider} | Link OAuth provider to account |
| [**list_o_auth_providers**](UsersApi.md#list_o_auth_providers) | **GET** /api/users/me/oauth-providers | List linked OAuth providers |
| [**resend_verification_email**](UsersApi.md#resend_verification_email) | **POST** /api/users/resend-verification | Resend verification email |
| [**setup2_fa**](UsersApi.md#setup2_fa) | **POST** /api/users/2fa/setup | Setup 2FA |
| [**unlink_o_auth_provider**](UsersApi.md#unlink_o_auth_provider) | **DELETE** /api/users/me/oauth-providers/{provider} | Unlink OAuth provider |
| [**update_user_profile**](UsersApi.md#update_user_profile) | **PATCH** /api/users/update | Update user profile |
| [**verify2_fa**](UsersApi.md#verify2_fa) | **POST** /api/users/2fa/verify | Verify and enable 2FA |
| [**verify_email**](UsersApi.md#verify_email) | **POST** /api/users/verify-email | Verify email address (organization and project) |


## api_me_bootstrap_get

> <ApiMeBootstrapGet200Response> api_me_bootstrap_get

Dashboard bootstrap (session + orgs + default org + projects)

Consolidated dashboard warmup in a single round-trip. Returns the session user, the user's organizations, the resolved default organization, and that org's projects. Shapes match GET /api/auth/session, GET /api/orgs and GET /api/projects.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::UsersApi.new

begin
  # Dashboard bootstrap (session + orgs + default org + projects)
  result = api_instance.api_me_bootstrap_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->api_me_bootstrap_get: #{e}"
end
```

#### Using the api_me_bootstrap_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiMeBootstrapGet200Response>, Integer, Hash)> api_me_bootstrap_get_with_http_info

```ruby
begin
  # Dashboard bootstrap (session + orgs + default org + projects)
  data, status_code, headers = api_instance.api_me_bootstrap_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiMeBootstrapGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->api_me_bootstrap_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ApiMeBootstrapGet200Response**](ApiMeBootstrapGet200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## change_password

> <MessageResponse> change_password(change_password_request)

Change password

Change the current user's password. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
change_password_request = Mudbase::ChangePasswordRequest.new({current_password: 'current_password_example', new_password: 'new_password_example'}) # ChangePasswordRequest | 

begin
  # Change password
  result = api_instance.change_password(change_password_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->change_password: #{e}"
end
```

#### Using the change_password_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> change_password_with_http_info(change_password_request)

```ruby
begin
  # Change password
  data, status_code, headers = api_instance.change_password_with_http_info(change_password_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->change_password_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **change_password_request** | [**ChangePasswordRequest**](ChangePasswordRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## disable2_fa

> <MessageResponse> disable2_fa(disable2_fa_request)

Disable 2FA

Disable two-factor authentication for the current user. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
disable2_fa_request = Mudbase::Disable2FARequest.new({password: 'SecurePass123!', token: '123456'}) # Disable2FARequest | 

begin
  # Disable 2FA
  result = api_instance.disable2_fa(disable2_fa_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->disable2_fa: #{e}"
end
```

#### Using the disable2_fa_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> disable2_fa_with_http_info(disable2_fa_request)

```ruby
begin
  # Disable 2FA
  data, status_code, headers = api_instance.disable2_fa_with_http_info(disable2_fa_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->disable2_fa_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **disable2_fa_request** | [**Disable2FARequest**](Disable2FARequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## erase_user_data

> <EraseUserData200Response> erase_user_data(erase_user_data_request)

Delete user data (GDPR Article 17)

Request account erasure (right to be forgotten). Anonymizes PII, revokes all sessions and API keys, and disables the account immediately (not a grace period - the effect is immediate and irreversible). Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint.  Requires re-proving your current password (skipped only for OAuth-only accounts with no password set) and, if 2FA is enabled, a fresh TOTP code - the same step-up re-authentication already required by the less-destructive `PATCH /api/users/password` and `POST /api/users/2fa/disable`. 

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

api_instance = Mudbase::UsersApi.new
erase_user_data_request = Mudbase::EraseUserDataRequest.new({confirm: 'DELETE'}) # EraseUserDataRequest | 

begin
  # Delete user data (GDPR Article 17)
  result = api_instance.erase_user_data(erase_user_data_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->erase_user_data: #{e}"
end
```

#### Using the erase_user_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EraseUserData200Response>, Integer, Hash)> erase_user_data_with_http_info(erase_user_data_request)

```ruby
begin
  # Delete user data (GDPR Article 17)
  data, status_code, headers = api_instance.erase_user_data_with_http_info(erase_user_data_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EraseUserData200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->erase_user_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **erase_user_data_request** | [**EraseUserDataRequest**](EraseUserDataRequest.md) |  |  |

### Return type

[**EraseUserData200Response**](EraseUserData200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_user_data

> <ExportUserData200Response> export_user_data

Export user data (GDPR Article 15)

Export all user data in JSON format for GDPR data portability compliance. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new

begin
  # Export user data (GDPR Article 15)
  result = api_instance.export_user_data
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->export_user_data: #{e}"
end
```

#### Using the export_user_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportUserData200Response>, Integer, Hash)> export_user_data_with_http_info

```ruby
begin
  # Export user data (GDPR Article 15)
  data, status_code, headers = api_instance.export_user_data_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportUserData200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->export_user_data_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ExportUserData200Response**](ExportUserData200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_current_user

> <GetCurrentUser200Response> get_current_user

Get current user profile

Get the current authenticated user's profile. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). 

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

api_instance = Mudbase::UsersApi.new

begin
  # Get current user profile
  result = api_instance.get_current_user
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->get_current_user: #{e}"
end
```

#### Using the get_current_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetCurrentUser200Response>, Integer, Hash)> get_current_user_with_http_info

```ruby
begin
  # Get current user profile
  data, status_code, headers = api_instance.get_current_user_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetCurrentUser200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->get_current_user_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetCurrentUser200Response**](GetCurrentUser200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## link_o_auth_provider

> link_o_auth_provider(provider, opts)

Link OAuth provider to account

Initiate OAuth flow to link a new provider to the current account. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
provider = 'google' # String | 
opts = {
  project_id: '65f1a2b3c4d5e6f7a8b9c0d1' # String | 
}

begin
  # Link OAuth provider to account
  api_instance.link_o_auth_provider(provider, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->link_o_auth_provider: #{e}"
end
```

#### Using the link_o_auth_provider_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> link_o_auth_provider_with_http_info(provider, opts)

```ruby
begin
  # Link OAuth provider to account
  data, status_code, headers = api_instance.link_o_auth_provider_with_http_info(provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->link_o_auth_provider_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |
| **project_id** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_o_auth_providers

> <ListOAuthProviders200Response> list_o_auth_providers

List linked OAuth providers

Get all OAuth providers linked to the current user's account. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new

begin
  # List linked OAuth providers
  result = api_instance.list_o_auth_providers
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->list_o_auth_providers: #{e}"
end
```

#### Using the list_o_auth_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListOAuthProviders200Response>, Integer, Hash)> list_o_auth_providers_with_http_info

```ruby
begin
  # List linked OAuth providers
  data, status_code, headers = api_instance.list_o_auth_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListOAuthProviders200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->list_o_auth_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListOAuthProviders200Response**](ListOAuthProviders200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## resend_verification_email

> <MessageResponse> resend_verification_email

Resend verification email

Sends a new verification email to the authenticated user. Rate limited (e.g. 3 requests per 15 minutes per user). For project-scoped users the link includes project context. 

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

api_instance = Mudbase::UsersApi.new

begin
  # Resend verification email
  result = api_instance.resend_verification_email
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->resend_verification_email: #{e}"
end
```

#### Using the resend_verification_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> resend_verification_email_with_http_info

```ruby
begin
  # Resend verification email
  data, status_code, headers = api_instance.resend_verification_email_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->resend_verification_email_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## setup2_fa

> <TwoFASetupResponse> setup2_fa

Setup 2FA

Setup two-factor authentication for the current user. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new

begin
  # Setup 2FA
  result = api_instance.setup2_fa
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->setup2_fa: #{e}"
end
```

#### Using the setup2_fa_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TwoFASetupResponse>, Integer, Hash)> setup2_fa_with_http_info

```ruby
begin
  # Setup 2FA
  data, status_code, headers = api_instance.setup2_fa_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TwoFASetupResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->setup2_fa_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**TwoFASetupResponse**](TwoFASetupResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## unlink_o_auth_provider

> <UnlinkOAuthProvider200Response> unlink_o_auth_provider(provider)

Unlink OAuth provider

Remove an OAuth provider from the current account. Cannot unlink if it's the only authentication method. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
provider = 'google' # String | 

begin
  # Unlink OAuth provider
  result = api_instance.unlink_o_auth_provider(provider)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->unlink_o_auth_provider: #{e}"
end
```

#### Using the unlink_o_auth_provider_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UnlinkOAuthProvider200Response>, Integer, Hash)> unlink_o_auth_provider_with_http_info(provider)

```ruby
begin
  # Unlink OAuth provider
  data, status_code, headers = api_instance.unlink_o_auth_provider_with_http_info(provider)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UnlinkOAuthProvider200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->unlink_o_auth_provider_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |

### Return type

[**UnlinkOAuthProvider200Response**](UnlinkOAuthProvider200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_user_profile

> <UpdateUserProfile200Response> update_user_profile(update_user_request)

Update user profile

Update the current user's profile. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
update_user_request = Mudbase::UpdateUserRequest.new # UpdateUserRequest | 

begin
  # Update user profile
  result = api_instance.update_user_profile(update_user_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->update_user_profile: #{e}"
end
```

#### Using the update_user_profile_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateUserProfile200Response>, Integer, Hash)> update_user_profile_with_http_info(update_user_request)

```ruby
begin
  # Update user profile
  data, status_code, headers = api_instance.update_user_profile_with_http_info(update_user_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateUserProfile200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->update_user_profile_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **update_user_request** | [**UpdateUserRequest**](UpdateUserRequest.md) |  |  |

### Return type

[**UpdateUserProfile200Response**](UpdateUserProfile200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify2_fa

> <MessageResponse> verify2_fa(verify2_fa_request)

Verify and enable 2FA

Verify and enable two-factor authentication for the current user. Accepts JWT Bearer token (OrgBearerAuth or ProjectBearerAuth - both are the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::UsersApi.new
verify2_fa_request = Mudbase::Verify2FARequest.new({token: '123456'}) # Verify2FARequest | 

begin
  # Verify and enable 2FA
  result = api_instance.verify2_fa(verify2_fa_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->verify2_fa: #{e}"
end
```

#### Using the verify2_fa_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> verify2_fa_with_http_info(verify2_fa_request)

```ruby
begin
  # Verify and enable 2FA
  data, status_code, headers = api_instance.verify2_fa_with_http_info(verify2_fa_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->verify2_fa_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **verify2_fa_request** | [**Verify2FARequest**](Verify2FARequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_email

> <MessageResponse> verify_email(verify_email_auth_request)

Verify email address (organization and project)

Verifies the user's email using the token from the link sent at signup. Works for both organization (platform) and project-based signups; the token is from the verification link (e.g. verify-email?token=... for org, or verify-email?token=...&project=... for project). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::UsersApi.new
verify_email_auth_request = Mudbase::VerifyEmailAuthRequest.new({token: 'token_example'}) # VerifyEmailAuthRequest | 

begin
  # Verify email address (organization and project)
  result = api_instance.verify_email(verify_email_auth_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->verify_email: #{e}"
end
```

#### Using the verify_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> verify_email_with_http_info(verify_email_auth_request)

```ruby
begin
  # Verify email address (organization and project)
  data, status_code, headers = api_instance.verify_email_with_http_info(verify_email_auth_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling UsersApi->verify_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **verify_email_auth_request** | [**VerifyEmailAuthRequest**](VerifyEmailAuthRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

