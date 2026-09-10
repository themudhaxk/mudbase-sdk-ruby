# Mudbase::MCPApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**mcp_config_get**](MCPApi.md#mcp_config_get) | **GET** /mcp/config | MCP connection status for the current org |


## mcp_config_get

> <McpConfigGet200Response> mcp_config_get

MCP connection status for the current org

Whether the org's plan includes MCP access and, when enabled, the endpoint URL an MCP client should connect to (the org's dedicated API host if it has dedicated infrastructure, otherwise the shared platform host). Auth here is the normal dashboard session - this powers the console's MCP settings page, distinct from the API-key-authenticated POST / endpoint an actual MCP client calls.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::MCPApi.new

begin
  # MCP connection status for the current org
  result = api_instance.mcp_config_get
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling MCPApi->mcp_config_get: #{e}"
end
```

#### Using the mcp_config_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<McpConfigGet200Response>, Integer, Hash)> mcp_config_get_with_http_info

```ruby
begin
  # MCP connection status for the current org
  data, status_code, headers = api_instance.mcp_config_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <McpConfigGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling MCPApi->mcp_config_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**McpConfigGet200Response**](McpConfigGet200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

