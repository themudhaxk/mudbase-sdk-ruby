# Mudbase::BucketsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_bucket**](BucketsApi.md#create_bucket) | **POST** /api/bucket/projects/{projectId}/buckets | Create a new bucket |
| [**delete_bucket**](BucketsApi.md#delete_bucket) | **DELETE** /api/bucket/projects/{projectId}/buckets/{bucketId} | Delete bucket |
| [**get_bucket**](BucketsApi.md#get_bucket) | **GET** /api/bucket/projects/{projectId}/buckets/{bucketId} | Get bucket details |
| [**list_buckets**](BucketsApi.md#list_buckets) | **GET** /api/bucket/projects/{projectId}/buckets | List buckets in a project |
| [**update_bucket**](BucketsApi.md#update_bucket) | **PATCH** /api/bucket/projects/{projectId}/buckets/{bucketId} | Update bucket |


## create_bucket

> <BucketResponse> create_bucket(project_id, create_bucket_request)

Create a new bucket

Create a new storage bucket in a project. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BucketsApi.new
project_id = 'project_id_example' # String | 
create_bucket_request = Mudbase::CreateBucketRequest.new({name: 'name_example'}) # CreateBucketRequest | 

begin
  # Create a new bucket
  result = api_instance.create_bucket(project_id, create_bucket_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->create_bucket: #{e}"
end
```

#### Using the create_bucket_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BucketResponse>, Integer, Hash)> create_bucket_with_http_info(project_id, create_bucket_request)

```ruby
begin
  # Create a new bucket
  data, status_code, headers = api_instance.create_bucket_with_http_info(project_id, create_bucket_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BucketResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->create_bucket_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_bucket_request** | [**CreateBucketRequest**](CreateBucketRequest.md) |  |  |

### Return type

[**BucketResponse**](BucketResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_bucket

> <MessageResponse> delete_bucket(project_id, bucket_id)

Delete bucket

Delete a storage bucket permanently. This is a destructive operation that will also delete all files in the bucket. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::BucketsApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 

begin
  # Delete bucket
  result = api_instance.delete_bucket(project_id, bucket_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->delete_bucket: #{e}"
end
```

#### Using the delete_bucket_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_bucket_with_http_info(project_id, bucket_id)

```ruby
begin
  # Delete bucket
  data, status_code, headers = api_instance.delete_bucket_with_http_info(project_id, bucket_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->delete_bucket_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_bucket

> <BucketResponse> get_bucket(project_id, bucket_id)

Get bucket details

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure Bearer authorization (JWT): OrgBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'

  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::BucketsApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 

begin
  # Get bucket details
  result = api_instance.get_bucket(project_id, bucket_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->get_bucket: #{e}"
end
```

#### Using the get_bucket_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BucketResponse>, Integer, Hash)> get_bucket_with_http_info(project_id, bucket_id)

```ruby
begin
  # Get bucket details
  data, status_code, headers = api_instance.get_bucket_with_http_info(project_id, bucket_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BucketResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->get_bucket_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |

### Return type

[**BucketResponse**](BucketResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_buckets

> <BucketListResponse> list_buckets(project_id, opts)

List buckets in a project

List all storage buckets in a project with pagination and search. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::BucketsApi.new
project_id = 'project_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  search: 'search_example' # String | 
}

begin
  # List buckets in a project
  result = api_instance.list_buckets(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->list_buckets: #{e}"
end
```

#### Using the list_buckets_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BucketListResponse>, Integer, Hash)> list_buckets_with_http_info(project_id, opts)

```ruby
begin
  # List buckets in a project
  data, status_code, headers = api_instance.list_buckets_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BucketListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->list_buckets_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **search** | **String** |  | [optional] |

### Return type

[**BucketListResponse**](BucketListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_bucket

> <BucketResponse> update_bucket(project_id, bucket_id, update_bucket_request)

Update bucket

Update bucket configuration (name, public/private status, settings). Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::BucketsApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
update_bucket_request = Mudbase::UpdateBucketRequest.new # UpdateBucketRequest | 

begin
  # Update bucket
  result = api_instance.update_bucket(project_id, bucket_id, update_bucket_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->update_bucket: #{e}"
end
```

#### Using the update_bucket_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BucketResponse>, Integer, Hash)> update_bucket_with_http_info(project_id, bucket_id, update_bucket_request)

```ruby
begin
  # Update bucket
  data, status_code, headers = api_instance.update_bucket_with_http_info(project_id, bucket_id, update_bucket_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BucketResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling BucketsApi->update_bucket_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **update_bucket_request** | [**UpdateBucketRequest**](UpdateBucketRequest.md) |  |  |

### Return type

[**BucketResponse**](BucketResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

