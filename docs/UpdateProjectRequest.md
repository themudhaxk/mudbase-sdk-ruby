# Mudbase::UpdateProjectRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **logo_url** | **String** | Public URL for the project logo/brand image. Prefer uploading via **POST /api/projects/{id}/logo** or **POST /api/projects/{orgId}/projects/{id}/logo** (stored under logo/project/ in platform storage). Used in project-related emails.  | [optional] |
| **settings** | [**ProjectSettings**](ProjectSettings.md) |  | [optional] |
| **auth** | [**AuthConfig**](AuthConfig.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateProjectRequest.new(
  name: Mudbase Platform,
  description: Main platform for Mudbase services,
  logo_url: null,
  settings: null,
  auth: null
)
```

