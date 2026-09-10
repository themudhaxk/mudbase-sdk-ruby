# Mudbase::FilesApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**api_files_download_file_id_get**](FilesApi.md#api_files_download_file_id_get) | **GET** /api/files/download/{fileId} | Get a download URL for a file |
| [**api_files_logo_redirect_get**](FilesApi.md#api_files_logo_redirect_get) | **GET** /api/files/logo-redirect | Redirect to an org/project logo&#39;s content |
| [**api_files_public_file_id_get**](FilesApi.md#api_files_public_file_id_get) | **GET** /api/files/public/{fileId} | Redirect to a public file&#39;s content |
| [**confirm_direct_upload**](FilesApi.md#confirm_direct_upload) | **POST** /api/files/upload/confirm | Confirm direct upload (scan + finalize metadata) |
| [**delete_file**](FilesApi.md#delete_file) | **DELETE** /api/bucket/projects/{projectId}/buckets/{bucketId}/files/{fileId} | Delete file |
| [**download_bucket_file**](FilesApi.md#download_bucket_file) | **GET** /api/bucket/files/{fileId}/download | Download file from bucket |
| [**download_file**](FilesApi.md#download_file) | **GET** /api/files/{fileId}/download | Generate a presigned URL for downloading a file |
| [**generate_presigned_upload**](FilesApi.md#generate_presigned_upload) | **POST** /api/files/upload/presigned | Generate a presigned PUT URL for direct browser upload |
| [**generate_signed_url**](FilesApi.md#generate_signed_url) | **POST** /api/bucket/projects/{projectId}/buckets/{bucketId}/files/{fileId}/signed-url | Generate signed URL for file |
| [**get_file**](FilesApi.md#get_file) | **GET** /api/bucket/projects/{projectId}/buckets/{bucketId}/files/{fileId} | Get file metadata |
| [**list_files**](FilesApi.md#list_files) | **GET** /api/bucket/projects/{projectId}/buckets/{bucketId}/files | List files in bucket |
| [**upload_files**](FilesApi.md#upload_files) | **POST** /api/bucket/projects/{projectId}/buckets/{bucketId}/files | Upload files to bucket |


## api_files_download_file_id_get

> <ApiFilesDownloadFileIdGet200Response> api_files_download_file_id_get(file_id, opts)

Get a download URL for a file

Returns a URL to download the file. For private files a short-lived signed URL is generated; the lifetime can be tuned per request via the optional expiresIn query parameter (seconds, clamped to a safe server-configured range). For public (public-read) files the permanent world-readable URL is returned with isPublic true and a warning, since signing a public object provides no protection. Accepts a JWT (Bearer) or a project API key.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::FilesApi.new
file_id = 'file_id_example' # String | 
opts = {
  expires_in: 56 # Integer | Signed-URL lifetime in seconds for private files. Clamped to the server's min/max range; ignored for public files. Defaults to the server's configured expiry.
}

begin
  # Get a download URL for a file
  result = api_instance.api_files_download_file_id_get(file_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_download_file_id_get: #{e}"
end
```

#### Using the api_files_download_file_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ApiFilesDownloadFileIdGet200Response>, Integer, Hash)> api_files_download_file_id_get_with_http_info(file_id, opts)

```ruby
begin
  # Get a download URL for a file
  data, status_code, headers = api_instance.api_files_download_file_id_get_with_http_info(file_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ApiFilesDownloadFileIdGet200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_download_file_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_id** | **String** |  |  |
| **expires_in** | **Integer** | Signed-URL lifetime in seconds for private files. Clamped to the server&#39;s min/max range; ignored for public files. Defaults to the server&#39;s configured expiry. | [optional] |

### Return type

[**ApiFilesDownloadFileIdGet200Response**](ApiFilesDownloadFileIdGet200Response.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## api_files_logo_redirect_get

> api_files_logo_redirect_get(key)

Redirect to an org/project logo's content

Unauthenticated. Logos are always meant to be public branding assets, but the object storage backend has no per-object ACL, so this route (not the bucket) is what actually serves them - the `key` query param is validated against the exact shape logoStorageService.uploadLogo() produces before signing, so this can never be used to fetch an arbitrary storage key. 302-redirects to a short-lived signed GET url.

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::FilesApi.new
key = 'key_example' # String | 

begin
  # Redirect to an org/project logo's content
  api_instance.api_files_logo_redirect_get(key)
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_logo_redirect_get: #{e}"
end
```

#### Using the api_files_logo_redirect_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_files_logo_redirect_get_with_http_info(key)

```ruby
begin
  # Redirect to an org/project logo's content
  data, status_code, headers = api_instance.api_files_logo_redirect_get_with_http_info(key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_logo_redirect_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## api_files_public_file_id_get

> api_files_public_file_id_get(file_id)

Redirect to a public file's content

Unauthenticated. Only serves files with isPublic=true whose upload has been confirmed and whose virus scan came back clean - the object storage backend has no per-object ACL, so this route (not the storage bucket) is what actually decides whether a \"public\" file's bytes are reachable. 302-redirects to a fresh, short-lived (60s) signed GET url so the actual bytes are still served straight off the storage edge.

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::FilesApi.new
file_id = 'file_id_example' # String | 

begin
  # Redirect to a public file's content
  api_instance.api_files_public_file_id_get(file_id)
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_public_file_id_get: #{e}"
end
```

#### Using the api_files_public_file_id_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> api_files_public_file_id_get_with_http_info(file_id)

```ruby
begin
  # Redirect to a public file's content
  data, status_code, headers = api_instance.api_files_public_file_id_get_with_http_info(file_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->api_files_public_file_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## confirm_direct_upload

> <ConfirmUploadResponse> confirm_direct_upload(confirm_direct_upload_request)

Confirm direct upload (scan + finalize metadata)

After a client uploads directly to object storage using the presigned PUT URL, call this endpoint to have the server scan the object, create the File record, and optionally quarantine if infected.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::FilesApi.new
confirm_direct_upload_request = Mudbase::ConfirmDirectUploadRequest.new({key: 'key_example', project_id: 'project_id_example'}) # ConfirmDirectUploadRequest | 

begin
  # Confirm direct upload (scan + finalize metadata)
  result = api_instance.confirm_direct_upload(confirm_direct_upload_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->confirm_direct_upload: #{e}"
end
```

#### Using the confirm_direct_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConfirmUploadResponse>, Integer, Hash)> confirm_direct_upload_with_http_info(confirm_direct_upload_request)

```ruby
begin
  # Confirm direct upload (scan + finalize metadata)
  data, status_code, headers = api_instance.confirm_direct_upload_with_http_info(confirm_direct_upload_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConfirmUploadResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->confirm_direct_upload_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **confirm_direct_upload_request** | [**ConfirmDirectUploadRequest**](ConfirmDirectUploadRequest.md) |  |  |

### Return type

[**ConfirmUploadResponse**](ConfirmUploadResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_file

> <MessageResponse> delete_file(project_id, bucket_id, file_id)

Delete file

Delete a file from a bucket permanently. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::FilesApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
file_id = 'file_id_example' # String | 

begin
  # Delete file
  result = api_instance.delete_file(project_id, bucket_id, file_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->delete_file: #{e}"
end
```

#### Using the delete_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_file_with_http_info(project_id, bucket_id, file_id)

```ruby
begin
  # Delete file
  data, status_code, headers = api_instance.delete_file_with_http_info(project_id, bucket_id, file_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->delete_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **file_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## download_bucket_file

> File download_bucket_file(file_id, opts)

Download file from bucket

Download a file from a bucket. For public files, no authentication is required. For private files, a download token (obtained via signed URL endpoint) is required in the query parameter. Accepts: Token-based authentication via query parameter (for private files), or no authentication (for public files). 

### Examples

```ruby
require 'time'
require 'mudbase'

api_instance = Mudbase::FilesApi.new
file_id = '685af8b85d73a104065b6a77' # String | 
opts = {
  token: 'token_example' # String | 
}

begin
  # Download file from bucket
  result = api_instance.download_bucket_file(file_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->download_bucket_file: #{e}"
end
```

#### Using the download_bucket_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> download_bucket_file_with_http_info(file_id, opts)

```ruby
begin
  # Download file from bucket
  data, status_code, headers = api_instance.download_bucket_file_with_http_info(file_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->download_bucket_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_id** | **String** |  |  |
| **token** | **String** |  | [optional] |

### Return type

**File**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/octet-stream, application/json


## download_file

> <SignedUrlResponse> download_file(file_id, opts)

Generate a presigned URL for downloading a file

Returns a time-limited provider-signed URL for direct download. Server enforces RBAC before issuing the URL.

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::FilesApi.new
file_id = 'file_id_example' # String | 
opts = {
  token: 'token_example' # String | 
}

begin
  # Generate a presigned URL for downloading a file
  result = api_instance.download_file(file_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->download_file: #{e}"
end
```

#### Using the download_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SignedUrlResponse>, Integer, Hash)> download_file_with_http_info(file_id, opts)

```ruby
begin
  # Generate a presigned URL for downloading a file
  data, status_code, headers = api_instance.download_file_with_http_info(file_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SignedUrlResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->download_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_id** | **String** |  |  |
| **token** | **String** |  | [optional] |

### Return type

[**SignedUrlResponse**](SignedUrlResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## generate_presigned_upload

> <PresignedPostResponse> generate_presigned_upload(generate_presigned_upload_request)

Generate a presigned PUT URL for direct browser upload

Issue a presigned PUT URL for clients to upload directly to object storage. The server stores the issued key with expiry and RBAC is enforced. PUT (not POST) is used because the object storage backend does not implement a POST-based upload API. The client must PUT the file body to `url` with the exact `headers` returned (a Content-Type mismatch fails with SignatureDoesNotMatch). `maxFileUploadBytes` is enforced server-side by `/api/files/upload/confirm` after the upload, not by the presigned URL itself. 

### Examples

```ruby
require 'time'
require 'mudbase'
# setup authorization
Mudbase.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-Key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-API-Key'] = 'Bearer'

  # Configure Bearer authorization (JWT): ProjectBearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Mudbase::FilesApi.new
generate_presigned_upload_request = Mudbase::GeneratePresignedUploadRequest.new({project_id: 'project_id_example', original_name: 'original_name_example'}) # GeneratePresignedUploadRequest | 

begin
  # Generate a presigned PUT URL for direct browser upload
  result = api_instance.generate_presigned_upload(generate_presigned_upload_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->generate_presigned_upload: #{e}"
end
```

#### Using the generate_presigned_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PresignedPostResponse>, Integer, Hash)> generate_presigned_upload_with_http_info(generate_presigned_upload_request)

```ruby
begin
  # Generate a presigned PUT URL for direct browser upload
  data, status_code, headers = api_instance.generate_presigned_upload_with_http_info(generate_presigned_upload_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PresignedPostResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->generate_presigned_upload_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **generate_presigned_upload_request** | [**GeneratePresignedUploadRequest**](GeneratePresignedUploadRequest.md) |  |  |

### Return type

[**PresignedPostResponse**](PresignedPostResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## generate_signed_url

> <SignedUrlResponse> generate_signed_url(project_id, bucket_id, file_id, opts)

Generate signed URL for file

Generate a time-limited signed URL for downloading a private file. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::FilesApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
file_id = 'file_id_example' # String | 
opts = {
  generate_signed_url_request: Mudbase::GenerateSignedUrlRequest.new # GenerateSignedUrlRequest | 
}

begin
  # Generate signed URL for file
  result = api_instance.generate_signed_url(project_id, bucket_id, file_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->generate_signed_url: #{e}"
end
```

#### Using the generate_signed_url_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SignedUrlResponse>, Integer, Hash)> generate_signed_url_with_http_info(project_id, bucket_id, file_id, opts)

```ruby
begin
  # Generate signed URL for file
  data, status_code, headers = api_instance.generate_signed_url_with_http_info(project_id, bucket_id, file_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SignedUrlResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->generate_signed_url_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **file_id** | **String** |  |  |
| **generate_signed_url_request** | [**GenerateSignedUrlRequest**](GenerateSignedUrlRequest.md) |  | [optional] |

### Return type

[**SignedUrlResponse**](SignedUrlResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_file

> <FileResponse> get_file(project_id, bucket_id, file_id)

Get file metadata

Get metadata for a specific file in a bucket. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::FilesApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
file_id = 'file_id_example' # String | 

begin
  # Get file metadata
  result = api_instance.get_file(project_id, bucket_id, file_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->get_file: #{e}"
end
```

#### Using the get_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FileResponse>, Integer, Hash)> get_file_with_http_info(project_id, bucket_id, file_id)

```ruby
begin
  # Get file metadata
  data, status_code, headers = api_instance.get_file_with_http_info(project_id, bucket_id, file_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FileResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->get_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **file_id** | **String** |  |  |

### Return type

[**FileResponse**](FileResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_files

> <FileListResponse> list_files(project_id, bucket_id, opts)

List files in bucket

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

api_instance = Mudbase::FilesApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  search: 'search_example', # String | 
  type: 'type_example' # String | 
}

begin
  # List files in bucket
  result = api_instance.list_files(project_id, bucket_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->list_files: #{e}"
end
```

#### Using the list_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FileListResponse>, Integer, Hash)> list_files_with_http_info(project_id, bucket_id, opts)

```ruby
begin
  # List files in bucket
  data, status_code, headers = api_instance.list_files_with_http_info(project_id, bucket_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FileListResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->list_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |
| **search** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |

### Return type

[**FileListResponse**](FileListResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## upload_files

> <FileUploadResponse> upload_files(project_id, bucket_id, files)

Upload files to bucket

Upload one or more files to a storage bucket using multipart/form-data. Per-file size is limited by the org plan (`maxFileUploadBytes`) and bucket `maxFileSize`, whichever is stricter. Exceeding the limit returns **413**. Accepts: OrgBearerAuth (for admin users), ProjectBearerAuth (JWT for authenticated users), or ApiKeyAuth (X-API-Key for programmatic access). Both ProjectBearerAuth and ApiKeyAuth are fully implemented. 

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

api_instance = Mudbase::FilesApi.new
project_id = 'project_id_example' # String | 
bucket_id = 'bucket_id_example' # String | 
files = [File.new('/path/to/some/file')] # Array<File> | 

begin
  # Upload files to bucket
  result = api_instance.upload_files(project_id, bucket_id, files)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->upload_files: #{e}"
end
```

#### Using the upload_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FileUploadResponse>, Integer, Hash)> upload_files_with_http_info(project_id, bucket_id, files)

```ruby
begin
  # Upload files to bucket
  data, status_code, headers = api_instance.upload_files_with_http_info(project_id, bucket_id, files)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FileUploadResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling FilesApi->upload_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **bucket_id** | **String** |  |  |
| **files** | **Array&lt;File&gt;** |  |  |

### Return type

[**FileUploadResponse**](FileUploadResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

