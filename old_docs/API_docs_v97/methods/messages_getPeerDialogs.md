---
title: messages.getPeerDialogs
description: Get dialog info of peers
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
---
# Method: messages.getPeerDialogs  
[Back to methods index](index.md)


Get dialog info of peers

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|peers|Array of [Username, chat ID, Update, Message or InputDialogPeer](../types/InputDialogPeer.md) | The peers | Yes|


### Return type: [messages\_PeerDialogs](../types/messages_PeerDialogs.md)

### Can bots use this method: **NO**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
define('MADELINE_BRANCH', '');
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$messages_PeerDialogs = $MadelineProto->messages->getPeerDialogs(['peers' => [InputDialogPeer, InputDialogPeer], ]);
```

Or, if you're into Lua:

```lua
messages_PeerDialogs = messages.getPeerDialogs({peers={InputDialogPeer}, })
```

### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CHANNEL_PRIVATE|You haven't joined this channel/supergroup|
|PEER_ID_INVALID|The provided peer id is invalid|

