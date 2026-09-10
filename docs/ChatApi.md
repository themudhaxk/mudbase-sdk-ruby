# Mudbase::ChatApi

All URIs are relative to *https://cloud.mudbase.dev*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_participant**](ChatApi.md#add_participant) | **POST** /api/chat/projects/{projectId}/chats/{chatId}/participants | Add participant to chat |
| [**add_reaction**](ChatApi.md#add_reaction) | **POST** /api/chat/projects/{projectId}/chats/{chatId}/messages/{messageId}/reactions | Add reaction to message |
| [**create_chat**](ChatApi.md#create_chat) | **POST** /api/chat/projects/{projectId}/chats | Create new chat |
| [**delete_message**](ChatApi.md#delete_message) | **DELETE** /api/chat/projects/{projectId}/chats/{chatId}/messages/{messageId} | Delete message |
| [**edit_message**](ChatApi.md#edit_message) | **PATCH** /api/chat/projects/{projectId}/chats/{chatId}/messages/{messageId} | Edit message |
| [**get_chat_details**](ChatApi.md#get_chat_details) | **GET** /api/chat/projects/{projectId}/chats/{chatId} | Get chat details |
| [**get_chat_e2ee_participant_keys**](ChatApi.md#get_chat_e2ee_participant_keys) | **GET** /api/chat/projects/{projectId}/chats/{chatId}/e2ee/participant-keys | List participant E2EE public keys |
| [**get_chat_messages**](ChatApi.md#get_chat_messages) | **GET** /api/chat/projects/{projectId}/chats/{chatId}/messages | Get chat messages |
| [**get_user_chats**](ChatApi.md#get_user_chats) | **GET** /api/chat/projects/{projectId}/chats | Get user chats |
| [**mark_messages_as_read**](ChatApi.md#mark_messages_as_read) | **POST** /api/chat/projects/{projectId}/chats/{chatId}/messages/read | Mark messages as read |
| [**put_chat_e2ee_key**](ChatApi.md#put_chat_e2ee_key) | **PUT** /api/chat/projects/{projectId}/me/chat-e2ee-key | Register chat E2EE identity public key |
| [**remove_participant**](ChatApi.md#remove_participant) | **DELETE** /api/chat/projects/{projectId}/chats/{chatId}/participants | Remove participant from chat |
| [**remove_reaction**](ChatApi.md#remove_reaction) | **DELETE** /api/chat/projects/{projectId}/chats/{chatId}/messages/{messageId}/reactions | Remove reaction from message |
| [**send_message**](ChatApi.md#send_message) | **POST** /api/chat/projects/{projectId}/chats/{chatId}/messages | Send message |


## add_participant

> <AddParticipant200Response> add_participant(project_id, chat_id, add_participant_request)

Add participant to chat

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
add_participant_request = Mudbase::AddParticipantRequest.new({user_id: 'user_id_example'}) # AddParticipantRequest | 

begin
  # Add participant to chat
  result = api_instance.add_participant(project_id, chat_id, add_participant_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->add_participant: #{e}"
end
```

#### Using the add_participant_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AddParticipant200Response>, Integer, Hash)> add_participant_with_http_info(project_id, chat_id, add_participant_request)

```ruby
begin
  # Add participant to chat
  data, status_code, headers = api_instance.add_participant_with_http_info(project_id, chat_id, add_participant_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AddParticipant200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->add_participant_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **add_participant_request** | [**AddParticipantRequest**](AddParticipantRequest.md) |  |  |

### Return type

[**AddParticipant200Response**](AddParticipant200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## add_reaction

> <AddReaction200Response> add_reaction(project_id, chat_id, message_id, add_reaction_request)

Add reaction to message

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
message_id = 'message_id_example' # String | 
add_reaction_request = Mudbase::AddReactionRequest.new({emoji: 'emoji_example'}) # AddReactionRequest | 

begin
  # Add reaction to message
  result = api_instance.add_reaction(project_id, chat_id, message_id, add_reaction_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->add_reaction: #{e}"
end
```

#### Using the add_reaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AddReaction200Response>, Integer, Hash)> add_reaction_with_http_info(project_id, chat_id, message_id, add_reaction_request)

```ruby
begin
  # Add reaction to message
  data, status_code, headers = api_instance.add_reaction_with_http_info(project_id, chat_id, message_id, add_reaction_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AddReaction200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->add_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **add_reaction_request** | [**AddReactionRequest**](AddReactionRequest.md) |  |  |

### Return type

[**AddReaction200Response**](AddReaction200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_chat

> <CreateChat201Response> create_chat(project_id, create_chat_request)

Create new chat

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
create_chat_request = Mudbase::CreateChatRequest.new({name: 'name_example', type: 'direct', participants: ['participants_example']}) # CreateChatRequest | 

begin
  # Create new chat
  result = api_instance.create_chat(project_id, create_chat_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->create_chat: #{e}"
end
```

#### Using the create_chat_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateChat201Response>, Integer, Hash)> create_chat_with_http_info(project_id, create_chat_request)

```ruby
begin
  # Create new chat
  data, status_code, headers = api_instance.create_chat_with_http_info(project_id, create_chat_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateChat201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->create_chat_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **create_chat_request** | [**CreateChatRequest**](CreateChatRequest.md) |  |  |

### Return type

[**CreateChat201Response**](CreateChat201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_message

> <MessageResponse> delete_message(project_id, chat_id, message_id)

Delete message

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
message_id = 'message_id_example' # String | 

begin
  # Delete message
  result = api_instance.delete_message(project_id, chat_id, message_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->delete_message: #{e}"
end
```

#### Using the delete_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> delete_message_with_http_info(project_id, chat_id, message_id)

```ruby
begin
  # Delete message
  data, status_code, headers = api_instance.delete_message_with_http_info(project_id, chat_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->delete_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## edit_message

> <EditMessage200Response> edit_message(project_id, chat_id, message_id, edit_message_request)

Edit message

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
message_id = 'message_id_example' # String | 
edit_message_request = Mudbase::EditMessageRequest.new # EditMessageRequest | 

begin
  # Edit message
  result = api_instance.edit_message(project_id, chat_id, message_id, edit_message_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->edit_message: #{e}"
end
```

#### Using the edit_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EditMessage200Response>, Integer, Hash)> edit_message_with_http_info(project_id, chat_id, message_id, edit_message_request)

```ruby
begin
  # Edit message
  data, status_code, headers = api_instance.edit_message_with_http_info(project_id, chat_id, message_id, edit_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EditMessage200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->edit_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **edit_message_request** | [**EditMessageRequest**](EditMessageRequest.md) |  |  |

### Return type

[**EditMessage200Response**](EditMessage200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_chat_details

> <GetChatDetails200Response> get_chat_details(project_id, chat_id)

Get chat details

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 

begin
  # Get chat details
  result = api_instance.get_chat_details(project_id, chat_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_details: #{e}"
end
```

#### Using the get_chat_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetChatDetails200Response>, Integer, Hash)> get_chat_details_with_http_info(project_id, chat_id)

```ruby
begin
  # Get chat details
  data, status_code, headers = api_instance.get_chat_details_with_http_info(project_id, chat_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetChatDetails200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |

### Return type

[**GetChatDetails200Response**](GetChatDetails200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_chat_e2ee_participant_keys

> <GetChatE2eeParticipantKeys200Response> get_chat_e2ee_participant_keys(project_id, chat_id)

List participant E2EE public keys

Returns registered identity public keys for users in this chat (for client-side key distribution).

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 

begin
  # List participant E2EE public keys
  result = api_instance.get_chat_e2ee_participant_keys(project_id, chat_id)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_e2ee_participant_keys: #{e}"
end
```

#### Using the get_chat_e2ee_participant_keys_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetChatE2eeParticipantKeys200Response>, Integer, Hash)> get_chat_e2ee_participant_keys_with_http_info(project_id, chat_id)

```ruby
begin
  # List participant E2EE public keys
  data, status_code, headers = api_instance.get_chat_e2ee_participant_keys_with_http_info(project_id, chat_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetChatE2eeParticipantKeys200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_e2ee_participant_keys_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |

### Return type

[**GetChatE2eeParticipantKeys200Response**](GetChatE2eeParticipantKeys200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_chat_messages

> <GetChatMessages200Response> get_chat_messages(project_id, chat_id, opts)

Get chat messages

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56, # Integer | 
  before: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  after: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # Get chat messages
  result = api_instance.get_chat_messages(project_id, chat_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_messages: #{e}"
end
```

#### Using the get_chat_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetChatMessages200Response>, Integer, Hash)> get_chat_messages_with_http_info(project_id, chat_id, opts)

```ruby
begin
  # Get chat messages
  data, status_code, headers = api_instance.get_chat_messages_with_http_info(project_id, chat_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetChatMessages200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_chat_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **before** | **Time** |  | [optional] |
| **after** | **Time** |  | [optional] |

### Return type

[**GetChatMessages200Response**](GetChatMessages200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_user_chats

> <GetUserChats200Response> get_user_chats(project_id, opts)

Get user chats

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
opts = {
  page: 56, # Integer | 
  limit: 56 # Integer | 
}

begin
  # Get user chats
  result = api_instance.get_user_chats(project_id, opts)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_user_chats: #{e}"
end
```

#### Using the get_user_chats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUserChats200Response>, Integer, Hash)> get_user_chats_with_http_info(project_id, opts)

```ruby
begin
  # Get user chats
  data, status_code, headers = api_instance.get_user_chats_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUserChats200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->get_user_chats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **limit** | **Integer** |  | [optional][default to 20] |

### Return type

[**GetUserChats200Response**](GetUserChats200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_messages_as_read

> <MarkMessagesAsRead200Response> mark_messages_as_read(project_id, chat_id, mark_messages_as_read_request)

Mark messages as read

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
mark_messages_as_read_request = Mudbase::MarkMessagesAsReadRequest.new({message_ids: ['message_ids_example']}) # MarkMessagesAsReadRequest | 

begin
  # Mark messages as read
  result = api_instance.mark_messages_as_read(project_id, chat_id, mark_messages_as_read_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->mark_messages_as_read: #{e}"
end
```

#### Using the mark_messages_as_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MarkMessagesAsRead200Response>, Integer, Hash)> mark_messages_as_read_with_http_info(project_id, chat_id, mark_messages_as_read_request)

```ruby
begin
  # Mark messages as read
  data, status_code, headers = api_instance.mark_messages_as_read_with_http_info(project_id, chat_id, mark_messages_as_read_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MarkMessagesAsRead200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->mark_messages_as_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **mark_messages_as_read_request** | [**MarkMessagesAsReadRequest**](MarkMessagesAsReadRequest.md) |  |  |

### Return type

[**MarkMessagesAsRead200Response**](MarkMessagesAsRead200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## put_chat_e2ee_key

> <PutChatE2eeKey200Response> put_chat_e2ee_key(project_id, put_chat_e2ee_key_request)

Register chat E2EE identity public key

Stores your long-term public key for end-to-end encrypted chat (key agreement). Private keys never leave the client. Required for other participants to encrypt to you. 

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
put_chat_e2ee_key_request = Mudbase::PutChatE2eeKeyRequest.new({identity_public_key: 'identity_public_key_example'}) # PutChatE2eeKeyRequest | 

begin
  # Register chat E2EE identity public key
  result = api_instance.put_chat_e2ee_key(project_id, put_chat_e2ee_key_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->put_chat_e2ee_key: #{e}"
end
```

#### Using the put_chat_e2ee_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PutChatE2eeKey200Response>, Integer, Hash)> put_chat_e2ee_key_with_http_info(project_id, put_chat_e2ee_key_request)

```ruby
begin
  # Register chat E2EE identity public key
  data, status_code, headers = api_instance.put_chat_e2ee_key_with_http_info(project_id, put_chat_e2ee_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PutChatE2eeKey200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->put_chat_e2ee_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **put_chat_e2ee_key_request** | [**PutChatE2eeKeyRequest**](PutChatE2eeKeyRequest.md) |  |  |

### Return type

[**PutChatE2eeKey200Response**](PutChatE2eeKey200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_participant

> <MessageResponse> remove_participant(project_id, chat_id, remove_participant_request)

Remove participant from chat

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
remove_participant_request = Mudbase::RemoveParticipantRequest.new({user_id: 'user_id_example'}) # RemoveParticipantRequest | 

begin
  # Remove participant from chat
  result = api_instance.remove_participant(project_id, chat_id, remove_participant_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->remove_participant: #{e}"
end
```

#### Using the remove_participant_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageResponse>, Integer, Hash)> remove_participant_with_http_info(project_id, chat_id, remove_participant_request)

```ruby
begin
  # Remove participant from chat
  data, status_code, headers = api_instance.remove_participant_with_http_info(project_id, chat_id, remove_participant_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageResponse>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->remove_participant_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **remove_participant_request** | [**RemoveParticipantRequest**](RemoveParticipantRequest.md) |  |  |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_reaction

> <RemoveReaction200Response> remove_reaction(project_id, chat_id, message_id, add_reaction_request)

Remove reaction from message

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
message_id = 'message_id_example' # String | 
add_reaction_request = Mudbase::AddReactionRequest.new({emoji: 'emoji_example'}) # AddReactionRequest | 

begin
  # Remove reaction from message
  result = api_instance.remove_reaction(project_id, chat_id, message_id, add_reaction_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->remove_reaction: #{e}"
end
```

#### Using the remove_reaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveReaction200Response>, Integer, Hash)> remove_reaction_with_http_info(project_id, chat_id, message_id, add_reaction_request)

```ruby
begin
  # Remove reaction from message
  data, status_code, headers = api_instance.remove_reaction_with_http_info(project_id, chat_id, message_id, add_reaction_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveReaction200Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->remove_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **add_reaction_request** | [**AddReactionRequest**](AddReactionRequest.md) |  |  |

### Return type

[**RemoveReaction200Response**](RemoveReaction200Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_message

> <SendMessage201Response> send_message(project_id, chat_id, send_message_request)

Send message

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

api_instance = Mudbase::ChatApi.new
project_id = 'project_id_example' # String | 
chat_id = 'chat_id_example' # String | 
send_message_request = Mudbase::SendMessageRequest.new({type: 'text'}) # SendMessageRequest | 

begin
  # Send message
  result = api_instance.send_message(project_id, chat_id, send_message_request)
  p result
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->send_message: #{e}"
end
```

#### Using the send_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendMessage201Response>, Integer, Hash)> send_message_with_http_info(project_id, chat_id, send_message_request)

```ruby
begin
  # Send message
  data, status_code, headers = api_instance.send_message_with_http_info(project_id, chat_id, send_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendMessage201Response>
rescue Mudbase::ApiError => e
  puts "Error when calling ChatApi->send_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  |  |
| **chat_id** | **String** |  |  |
| **send_message_request** | [**SendMessageRequest**](SendMessageRequest.md) |  |  |

### Return type

[**SendMessage201Response**](SendMessage201Response.md)

### Authorization

[OrgBearerAuth](../README.md#OrgBearerAuth), [ProjectBearerAuth](../README.md#ProjectBearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

