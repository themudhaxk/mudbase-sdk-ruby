# Mudbase::ProjectSettings

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **allow_anonymous_auth** | **Boolean** | Allow anonymous (unauthenticated) users | [optional][default to true] |
| **require_email_verification** | **Boolean** | When true, users who sign up with email do not receive a token until they verify their email; login is blocked until verified. | [optional][default to true] |
| **require_phone_verification** | **Boolean** | When true, users who sign in with phone (e.g. OTP) must have verified their phone before receiving a token. | [optional][default to false] |
| **default_user_account_status** | **String** | Default account status for new signups. **active** &#x3D; user can use the app immediately. **pending** &#x3D; user must be approved by an org owner/admin (PATCH org user status to active) before they can perform protected operations.  | [optional][default to &#39;active&#39;] |
| **enable_realtime** | **Boolean** |  | [optional][default to true] |
| **enable_storage** | **Boolean** |  | [optional][default to true] |
| **enable_functions** | **Boolean** |  | [optional][default to false] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProjectSettings.new(
  allow_anonymous_auth: null,
  require_email_verification: null,
  require_phone_verification: null,
  default_user_account_status: null,
  enable_realtime: null,
  enable_storage: null,
  enable_functions: null
)
```

