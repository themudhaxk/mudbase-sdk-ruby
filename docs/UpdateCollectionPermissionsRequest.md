# Mudbase::UpdateCollectionPermissionsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actions** | **Array&lt;String&gt;** |  | [optional] |
| **conditions** | **Object** |  | [optional] |
| **data_scope** | **String** | &#x60;all&#x60; &#x3D; no automatic row-owner filter. &#x60;own&#x60; &#x3D; only documents where the owner field matches the authenticated app user. | [optional] |
| **owner_field** | **String** | Optional override for the document field when dataScope is &#x60;own&#x60; (default &#x60;settings.dataOwnerField&#x60;, usually &#x60;createdBy&#x60;). | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateCollectionPermissionsRequest.new(
  actions: [&quot;create&quot;,&quot;read&quot;,&quot;update&quot;,&quot;delete&quot;],
  conditions: {&quot;status&quot;:&quot;active&quot;},
  data_scope: null,
  owner_field: null
)
```

