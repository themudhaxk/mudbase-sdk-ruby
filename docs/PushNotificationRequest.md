# Mudbase::PushNotificationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tokens** | **Array&lt;String&gt;** | Registered device push tokens to deliver to (device-token channel). | [optional] |
| **endpoints** | **Array&lt;String&gt;** | Registered Web Push subscription endpoints to deliver to (native Web Push channel).  | [optional] |
| **user_ids** | **Array&lt;String&gt;** | Deliver to every Web Push subscription registered under these user ids (native Web Push channel).  | [optional] |
| **web_push_broadcast** | **Boolean** | When true, deliver to every enabled Web Push subscription registered to the project (native Web Push channel). Ignored when the project has not enabled native Web Push.  | [optional] |
| **title** | **String** |  |  |
| **body** | **String** |  |  |
| **data** | **Object** |  | [optional] |
| **image_url** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PushNotificationRequest.new(
  tokens: null,
  endpoints: null,
  user_ids: null,
  web_push_broadcast: null,
  title: null,
  body: null,
  data: null,
  image_url: null
)
```

