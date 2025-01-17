---
title: "upload.getFile"
description: "You cannot use this method directly, use the upload, downloadToStream, downloadToFile, downloadToDir methods instead; see https://docs.madelineproto.xyz for more info"
grand_parent: "Telegram RPC API"
parent: "Methods"
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
redirect_from: /API_docs/methods/upload_getFile.html
---
# Method: upload.getFile
[Back to methods index](index.html)



You cannot use this method directly, use the upload, downloadToStream, downloadToFile, downloadToDir methods instead; see https://docs.madelineproto.xyz for more info

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|precise|[Bool](/API_docs/types/Bool.html) | Disable some checks on limit and offset values, useful for example to stream videos by keyframes | Optional|
|cdn\_supported|[Bool](/API_docs/types/Bool.html) | Whether the current client supports [CDN downloads](https://core.telegram.org/cdn) | Optional|
|location|[InputFileLocation](/API_docs/types/InputFileLocation.html) | File location | Yes|
|offset|[int](/API_docs/types/int.html) | Number of bytes to be skipped | Yes|
|limit|[int](/API_docs/types/int.html) | Number of bytes to be returned | Yes|


### Return type: [upload.File](/API_docs/types/upload.File.html)

### Can bots use this method: **YES**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$upload_File = $MadelineProto->upload->getFile(['precise' => Bool, 'cdn_supported' => Bool, 'location' => InputFileLocation, 'offset' => int, 'limit' => int, ]);
```

### Errors

| Code | Type     | Description   |
|------|----------|---------------|
|400|CHANNEL_INVALID|The provided channel is invalid|
|400|CHANNEL_PRIVATE|You haven't joined this channel/supergroup|
|400|FILE_ID_INVALID|The provided file id is invalid|
|400|FILE_REFERENCE_EXPIRED|File reference expired, it must be refetched as described in https://core.telegram.org/api/file_reference|
|400|INPUT_FETCH_FAIL|Failed deserializing TL payload|
|400|LIMIT_INVALID|The provided limit is invalid|
|400|LOCATION_INVALID|The provided location is invalid|
|400|MSG_ID_INVALID|Invalid message ID provided|
|400|OFFSET_INVALID|The provided offset is invalid|
|400|PEER_ID_INVALID|The provided peer id is invalid|
|-3002|All workers are busy. Active_queries = X|All workers are busy. Active_queries = X|
|406|AUTH_KEY_DUPLICATED|An auth key with the same ID was already generated|
|406|FILEREF_UPGRADE_NEEDED|The client has to be updated in order to support [file references](https://core.telegram.org/api/file_reference)|
|401|AUTH_KEY_PERM_EMPTY|The temporary auth key must be binded to the permanent auth key to use these methods.|
|-500|No workers running|Internal error|
|-503|Timeout|Timeout while fetching data|


