# Mudbase::AuthenticationApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**accept_invite**](AuthenticationApi.md#accept_invite) | **POST** /api/auth/accept-invite | Accept organization invitation |
| [**confirm_local_password_reset_with_otp**](AuthenticationApi.md#confirm_local_password_reset_with_otp) | **POST** /api/auth/local/password-reset/confirm | Confirm password reset with OTP (project-based) |
| [**convert_anonymous_account**](AuthenticationApi.md#convert_anonymous_account) | **POST** /api/auth/anonymous/convert | Convert anonymous account to full account |
| [**create_anonymous_session**](AuthenticationApi.md#create_anonymous_session) | **POST** /api/auth/anonymous | Create anonymous session |
| [**get_available_o_auth_providers**](AuthenticationApi.md#get_available_o_auth_providers) | **GET** /api/auth/oauth/providers/available | Get all available OAuth providers |
| [**get_current_session**](AuthenticationApi.md#get_current_session) | **GET** /api/auth/session | Get current session |
| [**get_local_session**](AuthenticationApi.md#get_local_session) | **GET** /api/auth/local/session | Get current session (project-based) |
| [**get_org_o_auth_providers**](AuthenticationApi.md#get_org_o_auth_providers) | **GET** /api/auth/oauth-org/providers | Get available OAuth providers for organization-based auth |
| [**initiate_o_auth**](AuthenticationApi.md#initiate_o_auth) | **GET** /api/auth/oauth/{provider}/{projectId} | Initiate OAuth authentication |
| [**initiate_org_o_auth**](AuthenticationApi.md#initiate_org_o_auth) | **GET** /api/auth/oauth-org/{provider} | Initiate OAuth authentication for organization |
| [**login_local_user**](AuthenticationApi.md#login_local_user) | **POST** /api/auth/local/login | Login user (project-based) |
| [**login_user**](AuthenticationApi.md#login_user) | **POST** /api/auth/login | Login user |
| [**logout_local_user**](AuthenticationApi.md#logout_local_user) | **POST** /api/auth/local/logout | Logout user (project-based) |
| [**logout_user**](AuthenticationApi.md#logout_user) | **POST** /api/auth/logout | Logout user |
| [**oauth_callback**](AuthenticationApi.md#oauth_callback) | **GET** /api/auth/oauth/callback/{provider} | OAuth callback handler (project-based) |
| [**org_o_auth_callback**](AuthenticationApi.md#org_o_auth_callback) | **GET** /api/auth/oauth-org/callback/{provider} | OAuth callback handler for organization |
| [**refresh_token**](AuthenticationApi.md#refresh_token) | **POST** /api/auth/refresh | Refresh access token (org and project) |
| [**register_local_user**](AuthenticationApi.md#register_local_user) | **POST** /api/auth/local/register | Register new user (project-based) |
| [**register_user**](AuthenticationApi.md#register_user) | **POST** /api/auth/register | Register new user |
| [**request_local_password_reset**](AuthenticationApi.md#request_local_password_reset) | **POST** /api/auth/local/password-reset | Request password reset (project-based, OTP) |
| [**request_password_reset**](AuthenticationApi.md#request_password_reset) | **POST** /api/auth/password-reset | Request password reset (organization / platform) |
| [**resend_verification_auth**](AuthenticationApi.md#resend_verification_auth) | **POST** /api/auth/resend-verification | Resend verification email (no auth) |
| [**reset_local_password**](AuthenticationApi.md#reset_local_password) | **POST** /api/auth/local/password-reset/{token} | Reset password with token (project-based, legacy) |
| [**reset_password**](AuthenticationApi.md#reset_password) | **POST** /api/auth/password-reset/{token} | Reset password with token (organization / platform) |
| [**send_magic_link**](AuthenticationApi.md#send_magic_link) | **POST** /api/auth/magic-link/send | Send magic link |
| [**send_otp**](AuthenticationApi.md#send_otp) | **POST** /api/auth/otp/send | Send OTP code |
| [**validate_password_reset_token**](AuthenticationApi.md#validate_password_reset_token) | **POST** /api/auth/password-reset/validate | Validate password reset token |
| [**verify_email_auth**](AuthenticationApi.md#verify_email_auth) | **POST** /api/auth/verify-email | Verify email address (no auth) |
| [**verify_magic_link**](AuthenticationApi.md#verify_magic_link) | **POST** /api/auth/magic-link/verify | Verify magic link |
| [**verify_otp**](AuthenticationApi.md#verify_otp) | **POST** /api/auth/otp/verify | Verify OTP code |


## accept_invite

> <AcceptInvite201Response> accept_invite(accept_invite_request)

Accept organization invitation

Accept an organization invitation using the token from the invite email link (e.g. `/invite/{token}?orgId=...`). Creates a new user with the invited email and adds them to the organization with the invited role. Returns a JWT and user so the client can log the user in immediately. No authentication required. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
accept_invite_request = Mudbase::AcceptInviteRequest.new({token: 'token_example', password: 'password_example', first_name: 'first_name_example', last_name: 'last_name_example'}) # AcceptInviteRequest | 

begin
  # Accept organization invitation
  result = api_instance.accept_invite(accept_invite_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->accept_invite: #{e}"
end
```

#### Using the accept_invite_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AcceptInvite201Response>, Integer, Hash)> accept_invite_with_http_info(accept_invite_request)

```ruby
begin
  # Accept organization invitation
  data, status_code, headers = api_instance.accept_invite_with_http_info(accept_invite_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AcceptInvite201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->accept_invite_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **accept_invite_request** | [**AcceptInviteRequest**](AcceptInviteRequest.md) |  |  |

### Return type

[**AcceptInvite201Response**](AcceptInvite201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## confirm_local_password_reset_with_otp

> <MessageResponse> confirm_local_password_reset_with_otp(confirm_local_password_reset_with_otp_request)

Confirm password reset with OTP (project-based)

Set new password using the OTP sent to the user's email. Call after POST /api/auth/local/password-reset with projectId. Rate limited (OTP limit). If the user's email was not yet verified, it is marked as verified upon successful reset. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
confirm_local_password_reset_with_otp_request = Mudbase::ConfirmLocalPasswordResetWithOtpRequest.new({email: 'user@example.com', project_id: '65f1a2b3c4d5e6f7a8b9c0d1', otp: '123456', new_password: 'NewSecurePass123!'}) # ConfirmLocalPasswordResetWithOtpRequest | 

begin
  # Confirm password reset with OTP (project-based)
  result = api_instance.confirm_local_password_reset_with_otp(confirm_local_password_reset_with_otp_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->confirm_local_password_reset_with_otp: #{e}"
end
```

#### Using the confirm_local_password_reset_with_otp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> confirm_local_password_reset_with_otp_with_http_info(confirm_local_password_reset_with_otp_request)

```ruby
begin
  # Confirm password reset with OTP (project-based)
  data, status_code, headers = api_instance.confirm_local_password_reset_with_otp_with_http_info(confirm_local_password_reset_with_otp_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->confirm_local_password_reset_with_otp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **confirm_local_password_reset_with_otp_request** | [**ConfirmLocalPasswordResetWithOtpRequest**](ConfirmLocalPasswordResetWithOtpRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## convert_anonymous_account

> <ConvertAnonymousAccount200Response> convert_anonymous_account(convert_anonymous_account_request)

Convert anonymous account to full account

Convert an anonymous user session to a full authenticated account. Preserves user data. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::AuthenticationApi.new
convert_anonymous_account_request = Mudbase::ConvertAnonymousAccountRequest.new({email: 'user@example.com', password: 'SecurePassword123!'}) # ConvertAnonymousAccountRequest | 

begin
  # Convert anonymous account to full account
  result = api_instance.convert_anonymous_account(convert_anonymous_account_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->convert_anonymous_account: #{e}"
end
```

#### Using the convert_anonymous_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConvertAnonymousAccount200Response>, Integer, Hash)> convert_anonymous_account_with_http_info(convert_anonymous_account_request)

```ruby
begin
  # Convert anonymous account to full account
  data, status_code, headers = api_instance.convert_anonymous_account_with_http_info(convert_anonymous_account_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConvertAnonymousAccount200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->convert_anonymous_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **convert_anonymous_account_request** | [**ConvertAnonymousAccountRequest**](ConvertAnonymousAccountRequest.md) |  |  |

### Return type

[**ConvertAnonymousAccount200Response**](ConvertAnonymousAccount200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_anonymous_session

> <CreateAnonymousSession200Response> create_anonymous_session(opts)

Create anonymous session

Create an anonymous user session for guest access. Users can later convert to full accounts.

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
opts = {
  create_anonymous_session_request: Mudbase::CreateAnonymousSessionRequest.new # CreateAnonymousSessionRequest | 
}

begin
  # Create anonymous session
  result = api_instance.create_anonymous_session(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->create_anonymous_session: #{e}"
end
```

#### Using the create_anonymous_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateAnonymousSession200Response>, Integer, Hash)> create_anonymous_session_with_http_info(opts)

```ruby
begin
  # Create anonymous session
  data, status_code, headers = api_instance.create_anonymous_session_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateAnonymousSession200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->create_anonymous_session_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_anonymous_session_request** | [**CreateAnonymousSessionRequest**](CreateAnonymousSessionRequest.md) |  | [optional] |

### Return type

[**CreateAnonymousSession200Response**](CreateAnonymousSession200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_available_o_auth_providers

> <GetAvailableOAuthProviders200Response> get_available_o_auth_providers

Get all available OAuth providers

Returns a list of all supported OAuth providers with their configuration details

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new

begin
  # Get all available OAuth providers
  result = api_instance.get_available_o_auth_providers
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_available_o_auth_providers: #{e}"
end
```

#### Using the get_available_o_auth_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAvailableOAuthProviders200Response>, Integer, Hash)> get_available_o_auth_providers_with_http_info

```ruby
begin
  # Get all available OAuth providers
  data, status_code, headers = api_instance.get_available_o_auth_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAvailableOAuthProviders200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_available_o_auth_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetAvailableOAuthProviders200Response**](GetAvailableOAuthProviders200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_current_session

> <SessionResponse> get_current_session

Get current session

Get the current authenticated user session information. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::AuthenticationApi.new

begin
  # Get current session
  result = api_instance.get_current_session
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_current_session: #{e}"
end
```

#### Using the get_current_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SessionResponse>, Integer, Hash)> get_current_session_with_http_info

```ruby
begin
  # Get current session
  data, status_code, headers = api_instance.get_current_session_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SessionResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_current_session_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SessionResponse**](SessionResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_local_session

> <GetLocalSession200Response> get_local_session(opts)

Get current session (project-based)

Get the current authenticated user session (project-based). Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::AuthenticationApi.new
opts = {
  project_id: 'project_id_example' # String | 
}

begin
  # Get current session (project-based)
  result = api_instance.get_local_session(opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_local_session: #{e}"
end
```

#### Using the get_local_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetLocalSession200Response>, Integer, Hash)> get_local_session_with_http_info(opts)

```ruby
begin
  # Get current session (project-based)
  data, status_code, headers = api_instance.get_local_session_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetLocalSession200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_local_session_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  | [optional] |

### Return type

[**GetLocalSession200Response**](GetLocalSession200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_org_o_auth_providers

> <GetOrgOAuthProviders200Response> get_org_o_auth_providers

Get available OAuth providers for organization-based auth

Returns a list of OAuth providers that are configured and available for organization-based authentication. Providers are configured via environment variables (e.g., GOOGLE_CLIENT_ID, GITHUB_CLIENT_ID). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new

begin
  # Get available OAuth providers for organization-based auth
  result = api_instance.get_org_o_auth_providers
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_org_o_auth_providers: #{e}"
end
```

#### Using the get_org_o_auth_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetOrgOAuthProviders200Response>, Integer, Hash)> get_org_o_auth_providers_with_http_info

```ruby
begin
  # Get available OAuth providers for organization-based auth
  data, status_code, headers = api_instance.get_org_o_auth_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetOrgOAuthProviders200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->get_org_o_auth_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetOrgOAuthProviders200Response**](GetOrgOAuthProviders200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## initiate_o_auth

> initiate_o_auth(provider, project_id, opts)

Initiate OAuth authentication

Initiates OAuth authentication flow for a specified provider and project. The OAuth provider must be configured and enabled for the project first. Returns an HTTP 302 redirect to the OAuth provider's consent screen. Note: Swagger \"Try it out\" may show \"Failed to fetch\" for this endpoint due to browser CORS restrictions on cross-origin redirects. Use top-level browser navigation or curl to test. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
provider = 'google' # String | 
project_id = '65f1a2b3c4d5e6f7a8b9c0d1' # String | 
opts = {
  redirect_url: 'https://client.app/auth/callback' # String | The URL to redirect to after authentication. Must be pre-registered in project settings.
}

begin
  # Initiate OAuth authentication
  api_instance.initiate_o_auth(provider, project_id, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->initiate_o_auth: #{e}"
end
```

#### Using the initiate_o_auth_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> initiate_o_auth_with_http_info(provider, project_id, opts)

```ruby
begin
  # Initiate OAuth authentication
  data, status_code, headers = api_instance.initiate_o_auth_with_http_info(provider, project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->initiate_o_auth_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |
| **project_id** | **String** |  |  |
| **redirect_url** | **String** | The URL to redirect to after authentication. Must be pre-registered in project settings. | [optional] |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## initiate_org_o_auth

> initiate_org_o_auth(provider, opts)

Initiate OAuth authentication for organization

Initiates OAuth authentication flow for organization-level signup/login. The OAuth provider must be configured via environment variables (e.g., GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET). After successful authentication, creates a new organization and user account, or logs in existing user. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
provider = 'google' # String | 
opts = {
  redirect_url: 'https://client.app/auth/callback' # String | The URL to redirect to after authentication
}

begin
  # Initiate OAuth authentication for organization
  api_instance.initiate_org_o_auth(provider, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->initiate_org_o_auth: #{e}"
end
```

#### Using the initiate_org_o_auth_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> initiate_org_o_auth_with_http_info(provider, opts)

```ruby
begin
  # Initiate OAuth authentication for organization
  data, status_code, headers = api_instance.initiate_org_o_auth_with_http_info(provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->initiate_org_o_auth_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |
| **redirect_url** | **String** | The URL to redirect to after authentication | [optional] |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## login_local_user

> <LoginLocalUser200Response> login_local_user(login_local_user_request)

Login user (project-based)

When the project has **requireEmailVerification** enabled and the user has not verified their email, returns 403 with code **EMAIL_VERIFICATION_REQUIRED** (user must verify email first, then login again). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
login_local_user_request = Mudbase::LoginLocalUserRequest.new({email: 'email_example', password: 'password_example'}) # LoginLocalUserRequest | 

begin
  # Login user (project-based)
  result = api_instance.login_local_user(login_local_user_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->login_local_user: #{e}"
end
```

#### Using the login_local_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<LoginLocalUser200Response>, Integer, Hash)> login_local_user_with_http_info(login_local_user_request)

```ruby
begin
  # Login user (project-based)
  data, status_code, headers = api_instance.login_local_user_with_http_info(login_local_user_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <LoginLocalUser200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->login_local_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **login_local_user_request** | [**LoginLocalUserRequest**](LoginLocalUserRequest.md) |  |  |

### Return type

[**LoginLocalUser200Response**](LoginLocalUser200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## login_user

> <AuthResponse> login_user(login_request)

Login user

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
login_request = Mudbase::LoginRequest.new({email: 'john.doe@mudbase.dev', password: 'SecurePass123!'}) # LoginRequest | 

begin
  # Login user
  result = api_instance.login_user(login_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->login_user: #{e}"
end
```

#### Using the login_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AuthResponse>, Integer, Hash)> login_user_with_http_info(login_request)

```ruby
begin
  # Login user
  data, status_code, headers = api_instance.login_user_with_http_info(login_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AuthResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->login_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **login_request** | [**LoginRequest**](LoginRequest.md) |  |  |

### Return type

[**AuthResponse**](AuthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## logout_local_user

> <MessageResponse> logout_local_user

Logout user (project-based)

Logout the current authenticated user session (project-based). Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::AuthenticationApi.new

begin
  # Logout user (project-based)
  result = api_instance.logout_local_user
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->logout_local_user: #{e}"
end
```

#### Using the logout_local_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> logout_local_user_with_http_info

```ruby
begin
  # Logout user (project-based)
  data, status_code, headers = api_instance.logout_local_user_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->logout_local_user_with_http_info: #{e}"
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


## logout_user

> <MessageResponse> logout_user

Logout user

Logout the current authenticated user session. Requires JWT Bearer token authentication. Both OrgBearerAuth and ProjectBearerAuth are supported (they use the same JWT token format). API keys are not supported for this endpoint. 

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

api_instance = Mudbase::AuthenticationApi.new

begin
  # Logout user
  result = api_instance.logout_user
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->logout_user: #{e}"
end
```

#### Using the logout_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> logout_user_with_http_info

```ruby
begin
  # Logout user
  data, status_code, headers = api_instance.logout_user_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->logout_user_with_http_info: #{e}"
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


## oauth_callback

> oauth_callback(provider)

OAuth callback handler (project-based)

Handles OAuth callback for project-based authentication. This route must be matched before /api/auth/oauth/{provider}/{projectId}. Redirects to frontend with query params token, refreshToken, and expiresIn. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
provider = 'provider_example' # String | 

begin
  # OAuth callback handler (project-based)
  api_instance.oauth_callback(provider)
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->oauth_callback: #{e}"
end
```

#### Using the oauth_callback_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> oauth_callback_with_http_info(provider)

```ruby
begin
  # OAuth callback handler (project-based)
  data, status_code, headers = api_instance.oauth_callback_with_http_info(provider)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->oauth_callback_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## org_o_auth_callback

> org_o_auth_callback(provider, opts)

OAuth callback handler for organization

Handles OAuth callback for organization-based authentication. Creates a new organization and user account if the user doesn't exist, or logs in existing user. Redirects to frontend with query params token, refreshToken, and expiresIn. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
provider = 'google' # String | 
opts = {
  code: 'code_example', # String | Authorization code from OAuth provider
  state: 'state_example' # String | State parameter for CSRF protection
}

begin
  # OAuth callback handler for organization
  api_instance.org_o_auth_callback(provider, opts)
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->org_o_auth_callback: #{e}"
end
```

#### Using the org_o_auth_callback_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> org_o_auth_callback_with_http_info(provider, opts)

```ruby
begin
  # OAuth callback handler for organization
  data, status_code, headers = api_instance.org_o_auth_callback_with_http_info(provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->org_o_auth_callback_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |
| **code** | **String** | Authorization code from OAuth provider | [optional] |
| **state** | **String** | State parameter for CSRF protection | [optional] |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## refresh_token

> <RefreshToken200Response> refresh_token(refresh_token_request)

Refresh access token (org and project)

Exchange a valid refresh token for a new JWT access token and refresh token. Works for both **org-based** (platform/dashboard) and **project-based** auth; the same endpoint is used. The previous refresh token is invalidated (rotation). If the same refresh token is used again, the session is revoked (reuse detection). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
refresh_token_request = Mudbase::RefreshTokenRequest.new({refresh_token: 'refresh_token_example'}) # RefreshTokenRequest | 

begin
  # Refresh access token (org and project)
  result = api_instance.refresh_token(refresh_token_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->refresh_token: #{e}"
end
```

#### Using the refresh_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RefreshToken200Response>, Integer, Hash)> refresh_token_with_http_info(refresh_token_request)

```ruby
begin
  # Refresh access token (org and project)
  data, status_code, headers = api_instance.refresh_token_with_http_info(refresh_token_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RefreshToken200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->refresh_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **refresh_token_request** | [**RefreshTokenRequest**](RefreshTokenRequest.md) |  |  |

### Return type

[**RefreshToken200Response**](RefreshToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## register_local_user

> <RegisterLocalUser201Response> register_local_user(register_local_user_request)

Register new user (project-based)

When the project has **requireEmailVerification** enabled (default), the response is 201 with **requireVerification: true** and **no token**; the user must verify their email then sign in via login. When email verification is disabled, a token and refreshToken are returned. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
register_local_user_request = Mudbase::RegisterLocalUserRequest.new({email: 'email_example', password: 'password_example', first_name: 'first_name_example', last_name: 'last_name_example', project_id: 'project_id_example'}) # RegisterLocalUserRequest | 

begin
  # Register new user (project-based)
  result = api_instance.register_local_user(register_local_user_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->register_local_user: #{e}"
end
```

#### Using the register_local_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RegisterLocalUser201Response>, Integer, Hash)> register_local_user_with_http_info(register_local_user_request)

```ruby
begin
  # Register new user (project-based)
  data, status_code, headers = api_instance.register_local_user_with_http_info(register_local_user_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RegisterLocalUser201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->register_local_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **register_local_user_request** | [**RegisterLocalUserRequest**](RegisterLocalUserRequest.md) |  |  |

### Return type

[**RegisterLocalUser201Response**](RegisterLocalUser201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## register_user

> <AuthResponse> register_user(register_request)

Register new user

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
register_request = Mudbase::RegisterRequest.new({email: 'john.doe@mudbase.dev', password: 'SecurePass123!', first_name: 'John', last_name: 'Doe'}) # RegisterRequest | 

begin
  # Register new user
  result = api_instance.register_user(register_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->register_user: #{e}"
end
```

#### Using the register_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AuthResponse>, Integer, Hash)> register_user_with_http_info(register_request)

```ruby
begin
  # Register new user
  data, status_code, headers = api_instance.register_user_with_http_info(register_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AuthResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->register_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **register_request** | [**RegisterRequest**](RegisterRequest.md) |  |  |

### Return type

[**AuthResponse**](AuthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## request_local_password_reset

> <MessageResponse> request_local_password_reset(request_local_password_reset_request)

Request password reset (project-based, OTP)

When projectId is provided, sends a 6-digit OTP to the user's email (project-based reset uses OTP, not link). When projectId is omitted, sends a token link (org/platform local account). Rate limited. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
request_local_password_reset_request = Mudbase::RequestLocalPasswordResetRequest.new({email: 'user@example.com'}) # RequestLocalPasswordResetRequest | 

begin
  # Request password reset (project-based, OTP)
  result = api_instance.request_local_password_reset(request_local_password_reset_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->request_local_password_reset: #{e}"
end
```

#### Using the request_local_password_reset_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> request_local_password_reset_with_http_info(request_local_password_reset_request)

```ruby
begin
  # Request password reset (project-based, OTP)
  data, status_code, headers = api_instance.request_local_password_reset_with_http_info(request_local_password_reset_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->request_local_password_reset_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_local_password_reset_request** | [**RequestLocalPasswordResetRequest**](RequestLocalPasswordResetRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## request_password_reset

> <MessageResponse> request_password_reset(request_password_reset_request)

Request password reset (organization / platform)

Sends a password reset link to the user's email. Use this for organization (platform) accounts. For project-based accounts use POST /api/auth/local/password-reset with projectId (sends OTP instead). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
request_password_reset_request = Mudbase::RequestPasswordResetRequest.new({email: 'john.doe@mudbase.dev'}) # RequestPasswordResetRequest | 

begin
  # Request password reset (organization / platform)
  result = api_instance.request_password_reset(request_password_reset_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->request_password_reset: #{e}"
end
```

#### Using the request_password_reset_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> request_password_reset_with_http_info(request_password_reset_request)

```ruby
begin
  # Request password reset (organization / platform)
  data, status_code, headers = api_instance.request_password_reset_with_http_info(request_password_reset_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->request_password_reset_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_password_reset_request** | [**RequestPasswordResetRequest**](RequestPasswordResetRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## resend_verification_auth

> <MessageResponse> resend_verification_auth(resend_verification_auth_request)

Resend verification email (no auth)

Sends a new verification email to the given email (and optional project). For unauthenticated users who have not verified yet. Rate limited (e.g. 3 per 15 min per IP). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
resend_verification_auth_request = Mudbase::ResendVerificationAuthRequest.new({email: 'email_example'}) # ResendVerificationAuthRequest | 

begin
  # Resend verification email (no auth)
  result = api_instance.resend_verification_auth(resend_verification_auth_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->resend_verification_auth: #{e}"
end
```

#### Using the resend_verification_auth_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> resend_verification_auth_with_http_info(resend_verification_auth_request)

```ruby
begin
  # Resend verification email (no auth)
  data, status_code, headers = api_instance.resend_verification_auth_with_http_info(resend_verification_auth_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->resend_verification_auth_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **resend_verification_auth_request** | [**ResendVerificationAuthRequest**](ResendVerificationAuthRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## reset_local_password

> <MessageResponse> reset_local_password(token, reset_local_password_request)

Reset password with token (project-based, legacy)

Legacy token-based completion. Prefer OTP flow: use POST .../password-reset/confirm with the OTP sent to email for project-based resets. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
token = 'token_example' # String | 
reset_local_password_request = Mudbase::ResetLocalPasswordRequest.new({password: 'NewSecurePass123!'}) # ResetLocalPasswordRequest | 

begin
  # Reset password with token (project-based, legacy)
  result = api_instance.reset_local_password(token, reset_local_password_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->reset_local_password: #{e}"
end
```

#### Using the reset_local_password_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> reset_local_password_with_http_info(token, reset_local_password_request)

```ruby
begin
  # Reset password with token (project-based, legacy)
  data, status_code, headers = api_instance.reset_local_password_with_http_info(token, reset_local_password_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->reset_local_password_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |
| **reset_local_password_request** | [**ResetLocalPasswordRequest**](ResetLocalPasswordRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## reset_password

> <MessageResponse> reset_password(token, reset_password_request)

Reset password with token (organization / platform)

Set new password using the token from the reset link. Validate the token first with POST /api/auth/password-reset/validate before showing the form. If the user's email was not yet verified, it is marked as verified upon successful reset. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
token = 'token_example' # String | 
reset_password_request = Mudbase::ResetPasswordRequest.new({password: 'NewSecurePass123!'}) # ResetPasswordRequest | 

begin
  # Reset password with token (organization / platform)
  result = api_instance.reset_password(token, reset_password_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->reset_password: #{e}"
end
```

#### Using the reset_password_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> reset_password_with_http_info(token, reset_password_request)

```ruby
begin
  # Reset password with token (organization / platform)
  data, status_code, headers = api_instance.reset_password_with_http_info(token, reset_password_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->reset_password_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |
| **reset_password_request** | [**ResetPasswordRequest**](ResetPasswordRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_magic_link

> <MessageResponse> send_magic_link(magic_link_request)

Send magic link

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
magic_link_request = Mudbase::MagicLinkRequest.new({email: 'email_example', project_id: 'project_id_example'}) # MagicLinkRequest | 

begin
  # Send magic link
  result = api_instance.send_magic_link(magic_link_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->send_magic_link: #{e}"
end
```

#### Using the send_magic_link_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> send_magic_link_with_http_info(magic_link_request)

```ruby
begin
  # Send magic link
  data, status_code, headers = api_instance.send_magic_link_with_http_info(magic_link_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->send_magic_link_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **magic_link_request** | [**MagicLinkRequest**](MagicLinkRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_otp

> <MessageResponse> send_otp(otp_send_request)

Send OTP code

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
otp_send_request = Mudbase::OTPSendRequest.new({project_id: 'project_id_example', method: 'sms'}) # OTPSendRequest | 

begin
  # Send OTP code
  result = api_instance.send_otp(otp_send_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->send_otp: #{e}"
end
```

#### Using the send_otp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> send_otp_with_http_info(otp_send_request)

```ruby
begin
  # Send OTP code
  data, status_code, headers = api_instance.send_otp_with_http_info(otp_send_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->send_otp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **otp_send_request** | [**OTPSendRequest**](OTPSendRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## validate_password_reset_token

> <ValidatePasswordResetToken200Response> validate_password_reset_token(validate_password_reset_token_request)

Validate password reset token

Call before showing the \"set new password\" form. Validates that the token from the reset link is still valid and not expired. Organization (platform) reset only. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
validate_password_reset_token_request = Mudbase::ValidatePasswordResetTokenRequest.new({token: 'token_example'}) # ValidatePasswordResetTokenRequest | 

begin
  # Validate password reset token
  result = api_instance.validate_password_reset_token(validate_password_reset_token_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->validate_password_reset_token: #{e}"
end
```

#### Using the validate_password_reset_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ValidatePasswordResetToken200Response>, Integer, Hash)> validate_password_reset_token_with_http_info(validate_password_reset_token_request)

```ruby
begin
  # Validate password reset token
  data, status_code, headers = api_instance.validate_password_reset_token_with_http_info(validate_password_reset_token_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ValidatePasswordResetToken200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->validate_password_reset_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **validate_password_reset_token_request** | [**ValidatePasswordResetTokenRequest**](ValidatePasswordResetTokenRequest.md) |  |  |

### Return type

[**ValidatePasswordResetToken200Response**](ValidatePasswordResetToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_email_auth

> <MessageResponse> verify_email_auth(verify_email_auth_request)

Verify email address (no auth)

Verifies the user's email using the token from the link sent at signup. Use this for both organization and project signups (unauthenticated). Same behavior as POST /api/users/verify-email. 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
verify_email_auth_request = Mudbase::VerifyEmailAuthRequest.new({token: 'token_example'}) # VerifyEmailAuthRequest | 

begin
  # Verify email address (no auth)
  result = api_instance.verify_email_auth(verify_email_auth_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_email_auth: #{e}"
end
```

#### Using the verify_email_auth_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> verify_email_auth_with_http_info(verify_email_auth_request)

```ruby
begin
  # Verify email address (no auth)
  data, status_code, headers = api_instance.verify_email_auth_with_http_info(verify_email_auth_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_email_auth_with_http_info: #{e}"
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


## verify_magic_link

> <AuthResponse> verify_magic_link(verify_magic_link_request)

Verify magic link

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
verify_magic_link_request = Mudbase::VerifyMagicLinkRequest.new({token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InVzZXJAZXhhbXBsZS5jb20iLCJwcm9qZWN0SWQiOiI2ODVhZDMwYmUxMjk5MzJmYmI3YTEwNDciLCJpYXQiOjE3NTA3ODA4OTgsImV4cCI6MTc1MDc4NDQ5OH0.example'}) # VerifyMagicLinkRequest | 

begin
  # Verify magic link
  result = api_instance.verify_magic_link(verify_magic_link_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_magic_link: #{e}"
end
```

#### Using the verify_magic_link_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AuthResponse>, Integer, Hash)> verify_magic_link_with_http_info(verify_magic_link_request)

```ruby
begin
  # Verify magic link
  data, status_code, headers = api_instance.verify_magic_link_with_http_info(verify_magic_link_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AuthResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_magic_link_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **verify_magic_link_request** | [**VerifyMagicLinkRequest**](VerifyMagicLinkRequest.md) |  |  |

### Return type

[**AuthResponse**](AuthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_otp

> <AuthResponse> verify_otp(otp_verify_request)

Verify OTP code

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::AuthenticationApi.new
otp_verify_request = Mudbase::OTPVerifyRequest.new({otp: 'otp_example', project_id: 'project_id_example'}) # OTPVerifyRequest | 

begin
  # Verify OTP code
  result = api_instance.verify_otp(otp_verify_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_otp: #{e}"
end
```

#### Using the verify_otp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AuthResponse>, Integer, Hash)> verify_otp_with_http_info(otp_verify_request)

```ruby
begin
  # Verify OTP code
  data, status_code, headers = api_instance.verify_otp_with_http_info(otp_verify_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AuthResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling AuthenticationApi->verify_otp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **otp_verify_request** | [**OTPVerifyRequest**](OTPVerifyRequest.md) |  |  |

### Return type

[**AuthResponse**](AuthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

