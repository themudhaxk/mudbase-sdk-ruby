# Mudbase Ruby SDK

Official **Ruby** client for [Mudbase](https://mudbase.dev) - the backend platform for modern apps.

Mudbase is a backend platform: authentication, a schema-driven database, file storage, serverless functions, webhooks, and real-time and transactional messaging behind one API. The Ruby SDK is a native Ruby client for that API, so you can manage users and organizations, define collections and query data, store and serve files, invoke functions, and configure webhooks without hand-rolling HTTP requests.

## Installation

```bash
gem install mudbase
```

## Quickstart

```ruby
require "mudbase"

Mudbase.configure do |config|
  config.host = "cloud.mudbase.dev"
  config.api_key["ApiKeyAuth"] = "YOUR_API_KEY"
end

collections = Mudbase::CollectionsApi.new
result = collections.list_collections("YOUR_PROJECT_ID")
puts result.collections
```

## What you can do

- **Authentication** - sign-up, sign-in, sessions, and API key management
- **Database** - schema-defined collections with typed CRUD and filtered queries
- **Storage** - buckets and file uploads and downloads
- **Realtime** - WebSocket events and live data subscriptions
- **Functions** - deploy and invoke serverless functions
- **Messaging** - transactional email, SMS, and push notifications
- **Webhooks** - configurable delivery with retry and logs
- **Roles & permissions** - project-level access control

## Links

- **Documentation:** https://docs.mudbase.dev
- **API reference:** https://docs.mudbase.dev/api
- **Dashboard:** https://console.mudbase.dev
- **Status:** https://status.mudbase.dev
- **Product:** https://mudbase.dev

## Support

Questions or issues: open one at https://github.com/themudhaxk/mudbase-sdk-ruby, or reach us at support@mudbase.dev.
