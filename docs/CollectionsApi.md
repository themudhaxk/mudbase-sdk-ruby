# Mudbase::CollectionsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_collection**](CollectionsApi.md#create_collection) | **POST** /api/schemas/projects/{projectId}/collections | Create new collection |
| [**delete_collection**](CollectionsApi.md#delete_collection) | **DELETE** /api/schemas/projects/{projectId}/collections/{collectionId} | Delete collection |
| [**get_collection**](CollectionsApi.md#get_collection) | **GET** /api/schemas/projects/{projectId}/collections/{collectionId} | Get single collection |
| [**list_collections**](CollectionsApi.md#list_collections) | **GET** /api/schemas/projects/{projectId}/collections | List collections in project |
| [**update_collection**](CollectionsApi.md#update_collection) | **PATCH** /api/schemas/projects/{projectId}/collections/{collectionId} | Update collection |


## create_collection

> <CreateCollection201Response> create_collection(project_id, create_collection_request)

Create new collection

Create a new collection in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::CollectionsApi.new
project_id = 'project_id_example' # String | 
create_collection_request = Mudbase::CreateCollectionRequest.new({name: 'name_example', fields: [Mudbase::Field.new({name: 'name_example', type: 'string'})]}) # CreateCollectionRequest | 

begin
  # Create new collection
  result = api_instance.create_collection(project_id, create_collection_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->create_collection: #{e}"
end
```

#### Using the create_collection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCollection201Response>, Integer, Hash)> create_collection_with_http_info(project_id, create_collection_request)

```ruby
begin
  # Create new collection
  data, status_code, headers = api_instance.create_collection_with_http_info(project_id, create_collection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCollection201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->create_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_collection_request** | [**CreateCollectionRequest**](CreateCollectionRequest.md) |  |  |

### Return type

[**CreateCollection201Response**](CreateCollection201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_collection

> <MessageResponse> delete_collection(project_id, collection_id)

Delete collection

Delete a collection permanently. This is a destructive operation. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::CollectionsApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 

begin
  # Delete collection
  result = api_instance.delete_collection(project_id, collection_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->delete_collection: #{e}"
end
```

#### Using the delete_collection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_collection_with_http_info(project_id, collection_id)

```ruby
begin
  # Delete collection
  data, status_code, headers = api_instance.delete_collection_with_http_info(project_id, collection_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->delete_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_collection

> <Collection> get_collection(project_id, collection_id)

Get single collection

Get collection details by ID. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::CollectionsApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 

begin
  # Get single collection
  result = api_instance.get_collection(project_id, collection_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->get_collection: #{e}"
end
```

#### Using the get_collection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Collection>, Integer, Hash)> get_collection_with_http_info(project_id, collection_id)

```ruby
begin
  # Get single collection
  data, status_code, headers = api_instance.get_collection_with_http_info(project_id, collection_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Collection>
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->get_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |

### Return type

[**Collection**](Collection.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_collections

> <ListCollections200Response> list_collections(project_id)

List collections in project

List all collections in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::CollectionsApi.new
project_id = 'project_id_example' # String | 

begin
  # List collections in project
  result = api_instance.list_collections(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->list_collections: #{e}"
end
```

#### Using the list_collections_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCollections200Response>, Integer, Hash)> list_collections_with_http_info(project_id)

```ruby
begin
  # List collections in project
  data, status_code, headers = api_instance.list_collections_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCollections200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->list_collections_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**ListCollections200Response**](ListCollections200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_collection

> <CreateCollection201Response> update_collection(project_id, collection_id, update_collection_request)

Update collection

Update collection configuration (name, fields, permissions). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::CollectionsApi.new
project_id = 'project_id_example' # String | 
collection_id = 'collection_id_example' # String | 
update_collection_request = Mudbase::UpdateCollectionRequest.new # UpdateCollectionRequest | 

begin
  # Update collection
  result = api_instance.update_collection(project_id, collection_id, update_collection_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->update_collection: #{e}"
end
```

#### Using the update_collection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCollection201Response>, Integer, Hash)> update_collection_with_http_info(project_id, collection_id, update_collection_request)

```ruby
begin
  # Update collection
  data, status_code, headers = api_instance.update_collection_with_http_info(project_id, collection_id, update_collection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCollection201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling CollectionsApi->update_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **collection_id** | **String** |  |  |
| **update_collection_request** | [**UpdateCollectionRequest**](UpdateCollectionRequest.md) |  |  |

### Return type

[**CreateCollection201Response**](CreateCollection201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

