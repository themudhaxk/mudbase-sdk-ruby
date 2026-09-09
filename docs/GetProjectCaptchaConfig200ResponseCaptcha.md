# Mudbase::GetProjectCaptchaConfig200ResponseCaptcha

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** | Whether CAPTCHA is enabled for this project | [optional] |
| **version** | **String** | reCAPTCHA version (v2 or v3) | [optional] |
| **site_key** | **String** | Public site key for frontend integration | [optional] |
| **min_score** | **Float** | Minimum score threshold for reCAPTCHA v3 | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetProjectCaptchaConfig200ResponseCaptcha.new(
  enabled: null,
  version: null,
  site_key: null,
  min_score: null
)
```

