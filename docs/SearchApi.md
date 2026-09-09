# Mudbase::SearchApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_search_analytics**](SearchApi.md#get_search_analytics) | **GET** /api/search/projects/{projectId}/search/analytics | Get search analytics |
| [**get_search_suggestions**](SearchApi.md#get_search_suggestions) | **GET** /api/search/projects/{projectId}/search/suggestions | Get search suggestions |
| [**search_data**](SearchApi.md#search_data) | **GET** /api/search/projects/{projectId}/search | Full-text search |


## get_search_analytics

> <GetSearchAnalytics200Response> get_search_analytics(project_id, opts)

Get search analytics

Get search analytics including top queries, search volume, and performance metrics. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::SearchApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
opts = {
  timeframe: '1d' # String | 
}

begin
  # Get search analytics
  result = api_instance.get_search_analytics(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->get_search_analytics: #{e}"
end
```

#### Using the get_search_analytics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSearchAnalytics200Response>, Integer, Hash)> get_search_analytics_with_http_info(project_id, opts)

```ruby
begin
  # Get search analytics
  data, status_code, headers = api_instance.get_search_analytics_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSearchAnalytics200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->get_search_analytics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **timeframe** | **String** |  | [optional][default to &#39;7d&#39;] |

### Return type

[**GetSearchAnalytics200Response**](GetSearchAnalytics200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_suggestions

> <GetSearchSuggestions200Response> get_search_suggestions(project_id, q, opts)

Get search suggestions

Get search query suggestions based on partial input. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::SearchApi.new
project_id = '685ad30be129932fbb7a1047' # String | 
q = 'q_example' # String | 
opts = {
  limit: 56 # Integer | 
}

begin
  # Get search suggestions
  result = api_instance.get_search_suggestions(project_id, q, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->get_search_suggestions: #{e}"
end
```

#### Using the get_search_suggestions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSearchSuggestions200Response>, Integer, Hash)> get_search_suggestions_with_http_info(project_id, q, opts)

```ruby
begin
  # Get search suggestions
  data, status_code, headers = api_instance.get_search_suggestions_with_http_info(project_id, q, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSearchSuggestions200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->get_search_suggestions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **q** | **String** |  |  |
| **limit** | **Integer** |  | [optional][default to 10] |

### Return type

[**GetSearchSuggestions200Response**](GetSearchSuggestions200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## search_data

> <SearchResponse> search_data(project_id, q, opts)

Full-text search

Perform full-text search across collections in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::SearchApi.new
project_id = 'project_id_example' # String | 
q = 'q_example' # String | 
opts = {
  collections: 'collections_example', # String | 
  fields: 'fields_example', # String | 
  limit: 56, # Integer | 
  page: 56 # Integer | 
}

begin
  # Full-text search
  result = api_instance.search_data(project_id, q, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->search_data: #{e}"
end
```

#### Using the search_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchResponse>, Integer, Hash)> search_data_with_http_info(project_id, q, opts)

```ruby
begin
  # Full-text search
  data, status_code, headers = api_instance.search_data_with_http_info(project_id, q, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling SearchApi->search_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **q** | **String** |  |  |
| **collections** | **String** |  | [optional] |
| **fields** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **page** | **Integer** |  | [optional][default to 1] |

### Return type

[**SearchResponse**](SearchResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

