# Mudbase::ProjectSmsByoPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **default_from** | **String** | Default sender (E.164 for Twilio; Termii/Africa&#39;s Talking may use alphanumeric or approved sender IDs per provider rules). | [optional] |
| **config** | **Hash&lt;String, Object&gt;** | Provider credentials and options (encrypted at rest). Required keys when enabling BYO: **twilio** — &#x60;accountSid&#x60;, &#x60;authToken&#x60;. Optional &#x60;from&#x60;. **termii** — &#x60;apiKey&#x60;. Optional &#x60;from&#x60;. **africastalking** — &#x60;username&#x60;, &#x60;apiKey&#x60;. Optional &#x60;from&#x60;.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProjectSmsByoPatchRequest.new(
  enabled: null,
  provider: null,
  default_from: null,
  config: null
)
```

