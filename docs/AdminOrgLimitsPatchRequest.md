# Mudbase::AdminOrgLimitsPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **projects** | **Integer** |  | [optional] |
| **storage** | **Integer** |  | [optional] |
| **bandwidth** | **Integer** |  | [optional] |
| **api_calls** | **Integer** |  | [optional] |
| **buckets** | **Integer** |  | [optional] |
| **collections** | **Integer** |  | [optional] |
| **realtime_connections** | **Integer** |  | [optional] |
| **realtime_messages** | **Integer** |  | [optional] |
| **chat_messages_per_month** | **Integer** |  | [optional] |
| **api_keys_per_project** | **Integer** |  | [optional] |
| **webhooks_per_project** | **Integer** |  | [optional] |
| **functions_per_project** | **Integer** |  | [optional] |
| **function_invocations_per_month** | **Integer** |  | [optional] |
| **messaging_messages_per_month** | **Integer** |  | [optional] |
| **sms_per_month** | **Integer** |  | [optional] |
| **chat_channels_per_project** | **Integer** |  | [optional] |
| **backups_per_project** | **Integer** |  | [optional] |
| **restores_per_month** | **Integer** |  | [optional] |
| **integrations_per_project** | **Integer** |  | [optional] |
| **roles_per_org** | **Integer** |  | [optional] |
| **alerts_per_project** | **Integer** |  | [optional] |
| **blockchain_chains** | **Integer** |  | [optional] |
| **team_users** | **Integer** |  | [optional] |
| **bug_analysis** | [**AdminOrgLimitsPatchRequestBugAnalysis**](AdminOrgLimitsPatchRequestBugAnalysis.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AdminOrgLimitsPatchRequest.new(
  projects: null,
  storage: null,
  bandwidth: null,
  api_calls: null,
  buckets: null,
  collections: null,
  realtime_connections: null,
  realtime_messages: null,
  chat_messages_per_month: null,
  api_keys_per_project: null,
  webhooks_per_project: null,
  functions_per_project: null,
  function_invocations_per_month: null,
  messaging_messages_per_month: null,
  sms_per_month: null,
  chat_channels_per_project: null,
  backups_per_project: null,
  restores_per_month: null,
  integrations_per_project: null,
  roles_per_org: null,
  alerts_per_project: null,
  blockchain_chains: null,
  team_users: null,
  bug_analysis: null
)
```

