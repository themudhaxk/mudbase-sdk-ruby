# Mudbase::BackupsApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_backup**](BackupsApi.md#create_backup) | **POST** /api/projects/{projectId}/backups | Create project backup |
| [**delete_backup**](BackupsApi.md#delete_backup) | **DELETE** /api/projects/{projectId}/backups/{backupId} | Delete backup |
| [**list_backups**](BackupsApi.md#list_backups) | **GET** /api/projects/{projectId}/backups | List project backups |
| [**restore_backup**](BackupsApi.md#restore_backup) | **POST** /api/projects/{projectId}/backups/{backupId}/restore | Restore from backup |


## create_backup

> <CreateBackup201Response> create_backup(project_id, opts)

Create project backup

Create a backup of project data, optionally including files and wallets. Supports both JWT Bearer token and API key authentication.

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

api_instance = Mudbase::BackupsApi.new
project_id = '65f1a2b3c4d5e6f7a8b9c0d1' # String | 
opts = {
  create_backup_request: Mudbase::CreateBackupRequest.new # CreateBackupRequest | 
}

begin
  # Create project backup
  result = api_instance.create_backup(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->create_backup: #{e}"
end
```

#### Using the create_backup_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateBackup201Response>, Integer, Hash)> create_backup_with_http_info(project_id, opts)

```ruby
begin
  # Create project backup
  data, status_code, headers = api_instance.create_backup_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateBackup201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->create_backup_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_backup_request** | [**CreateBackupRequest**](CreateBackupRequest.md) |  | [optional] |

### Return type

[**CreateBackup201Response**](CreateBackup201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_backup

> <DeleteBackup200Response> delete_backup(project_id, backup_id)

Delete backup

Delete a project backup. Supports both JWT Bearer token and API key authentication.

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

api_instance = Mudbase::BackupsApi.new
project_id = 'project_id_example' # String | 
backup_id = 'backup_id_example' # String | 

begin
  # Delete backup
  result = api_instance.delete_backup(project_id, backup_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->delete_backup: #{e}"
end
```

#### Using the delete_backup_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteBackup200Response>, Integer, Hash)> delete_backup_with_http_info(project_id, backup_id)

```ruby
begin
  # Delete backup
  data, status_code, headers = api_instance.delete_backup_with_http_info(project_id, backup_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteBackup200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->delete_backup_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **backup_id** | **String** |  |  |

### Return type

[**DeleteBackup200Response**](DeleteBackup200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_backups

> <ListBackups200Response> list_backups(project_id)

List project backups

Get all backups for a project. Supports both JWT Bearer token and API key authentication.

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

api_instance = Mudbase::BackupsApi.new
project_id = 'project_id_example' # String | 

begin
  # List project backups
  result = api_instance.list_backups(project_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->list_backups: #{e}"
end
```

#### Using the list_backups_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListBackups200Response>, Integer, Hash)> list_backups_with_http_info(project_id)

```ruby
begin
  # List project backups
  data, status_code, headers = api_instance.list_backups_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListBackups200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->list_backups_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |

### Return type

[**ListBackups200Response**](ListBackups200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## restore_backup

> <RestoreBackup200Response> restore_backup(project_id, backup_id, restore_backup_request)

Restore from backup

Restore project data from a backup. Supports replace or merge modes. Supports both JWT Bearer token and API key authentication.

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

api_instance = Mudbase::BackupsApi.new
project_id = 'project_id_example' # String | 
backup_id = 'backup_id_example' # String | 
restore_backup_request = Mudbase::RestoreBackupRequest.new({confirmation: 'RESTORE_DATA'}) # RestoreBackupRequest | 

begin
  # Restore from backup
  result = api_instance.restore_backup(project_id, backup_id, restore_backup_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->restore_backup: #{e}"
end
```

#### Using the restore_backup_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RestoreBackup200Response>, Integer, Hash)> restore_backup_with_http_info(project_id, backup_id, restore_backup_request)

```ruby
begin
  # Restore from backup
  data, status_code, headers = api_instance.restore_backup_with_http_info(project_id, backup_id, restore_backup_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RestoreBackup200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling BackupsApi->restore_backup_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **backup_id** | **String** |  |  |
| **restore_backup_request** | [**RestoreBackupRequest**](RestoreBackupRequest.md) |  |  |

### Return type

[**RestoreBackup200Response**](RestoreBackup200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ApiKeyAuth](../README.md#ApiKeyAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

