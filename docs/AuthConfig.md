# Mudbase::AuthConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **providers** | [**Array&lt;AuthProvider&gt;**](AuthProvider.md) |  | [optional] |
| **notify_on_new_sign_in** | **Boolean** | When true, a \&quot;new sign-in detected\&quot; email is sent to the user on each project-based sign-in (local or OAuth). Counts against the org&#39;s messaging/email plan quota. Default false. Organization-based sign-in always sends this email (no quota deduction).  | [optional][default to false] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AuthConfig.new(
  providers: null,
  notify_on_new_sign_in: null
)
```

