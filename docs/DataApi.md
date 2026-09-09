# Mudbase::DataApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_data**](DataApi.md#create_data) | **POST** /api/data/projects/{projectId}/collections/{collectionId}/data | Create data in collection |
| [**delete_data**](DataApi.md#delete_data) | **DELETE** /api/data/projects/{projectId}/collections/{collectionId}/data/{documentId} | Delete document |
| [**get_data**](DataApi.md#get_data) | **GET** /api/data/projects/{projectId}/collections/{collectionId}/data/{documentId} | Get single document |
| [**list_data**](DataApi.md#list_data) | **GET** /api/data/projects/{projectId}/collections/{collectionId}/data | List data in collection |
| [**update_data**](DataApi.md#update_data) | **PATCH** /api/data/projects/{projectId}/collections/{collectionId}/data/{documentId} | Update document |


## create_data

> <DataResponse> create_data(project_id, collection_id, body)

Create data in collection

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

api_instance = Mudbase::DataApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
body = { ... } # Object | 

begin
  # Create data in collection
  result = api_instance.create_data(project_id, collection_id, body)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->create_data: #{e}"
end
```

#### Using the create_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DataResponse>, Integer, Hash)> create_data_with_http_info(project_id, collection_id, body)

```ruby
begin
  # Create data in collection
  data, status_code, headers = api_instance.create_data_with_http_info(project_id, collection_id, body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DataResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->create_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **body** | **Object** |  |  |

### Return type

[**DataResponse**](DataResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_data

> <MessageResponse> delete_data(project_id, collection_id, document_id)

Delete document

Delete a document from a collection. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::DataApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
document_id = 'document_id_example' # String | 

begin
  # Delete document
  result = api_instance.delete_data(project_id, collection_id, document_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->delete_data: #{e}"
end
```

#### Using the delete_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_data_with_http_info(project_id, collection_id, document_id)

```ruby
begin
  # Delete document
  data, status_code, headers = api_instance.delete_data_with_http_info(project_id, collection_id, document_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->delete_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **document_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_data

> <DataResponse> get_data(project_id, collection_id, document_id)

Get single document

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

api_instance = Mudbase::DataApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
document_id = 'document_id_example' # String | 

begin
  # Get single document
  result = api_instance.get_data(project_id, collection_id, document_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->get_data: #{e}"
end
```

#### Using the get_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DataResponse>, Integer, Hash)> get_data_with_http_info(project_id, collection_id, document_id)

```ruby
begin
  # Get single document
  data, status_code, headers = api_instance.get_data_with_http_info(project_id, collection_id, document_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DataResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->get_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **document_id** | **String** |  |  |

### Return type

[**DataResponse**](DataResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_data

> <DataListResponse> list_data(project_id, collection_id, opts)

List data in collection

List all documents in a collection. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::DataApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  sort: 'sort_example', # String | 
  filter: 'filter_example' # String | 
}

begin
  # List data in collection
  result = api_instance.list_data(project_id, collection_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->list_data: #{e}"
end
```

#### Using the list_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DataListResponse>, Integer, Hash)> list_data_with_http_info(project_id, collection_id, opts)

```ruby
begin
  # List data in collection
  data, status_code, headers = api_instance.list_data_with_http_info(project_id, collection_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DataListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->list_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **sort** | **String** |  | [optional][default to &#39;-createdAt&#39;] |
| **filter** | **String** |  | [optional] |

### Return type

[**DataListResponse**](DataListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_data

> <DataResponse> update_data(project_id, collection_id, document_id, body)

Update document

Update a document in a collection. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::DataApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
document_id = 'document_id_example' # String | 
body = { ... } # Object | 

begin
  # Update document
  result = api_instance.update_data(project_id, collection_id, document_id, body)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->update_data: #{e}"
end
```

#### Using the update_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DataResponse>, Integer, Hash)> update_data_with_http_info(project_id, collection_id, document_id, body)

```ruby
begin
  # Update document
  data, status_code, headers = api_instance.update_data_with_http_info(project_id, collection_id, document_id, body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DataResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling DataApi->update_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **document_id** | **String** |  |  |
| **body** | **Object** |  |  |

### Return type

[**DataResponse**](DataResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

