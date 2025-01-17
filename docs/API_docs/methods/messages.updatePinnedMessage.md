---
title: "messages.updatePinnedMessage"
description: "Pin a message"
grand_parent: "Telegram RPC API"
parent: "Methods"
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
redirect_from: /API_docs/methods/messages_updatePinnedMessage.html
---
# Method: messages.updatePinnedMessage
[Back to methods index](index.html)



Pin a message

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|silent|[Bool](/API_docs/types/Bool.html) | Pin the message silently, without triggering a notification | Optional|
|unpin|[Bool](/API_docs/types/Bool.html) | Whether the message should unpinned or pinned | Optional|
|pm\_oneside|[Bool](/API_docs/types/Bool.html) | Whether the message should only be pinned on the local side of a one-to-one chat | Optional|
|peer|[Username, chat ID, Update, Message or InputPeer](/API_docs/types/InputPeer.html) | The peer where to pin the message | Optional|
|id|[int](/API_docs/types/int.html) | The message to pin or unpin | Yes|


### Return type: [Updates](/API_docs/types/Updates.html)

### Can bots use this method: **YES**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$Updates = $MadelineProto->messages->updatePinnedMessage(['silent' => Bool, 'unpin' => Bool, 'pm_oneside' => Bool, 'peer' => InputPeer, 'id' => int, ]);
```

### Errors

| Code | Type     | Description   |
|------|----------|---------------|
|400|BOT_ONESIDE_NOT_AVAIL|Bots can't pin messages in PM just for themselves|
|400|CHANNEL_PRIVATE|You haven't joined this channel/supergroup|
|400|CHAT_ADMIN_REQUIRED|You must be an admin in this chat to do this|
|400|CHAT_NOT_MODIFIED|The pinned message wasn't modified|
|400|MESSAGE_ID_INVALID|The provided message id is invalid|
|400|PEER_ID_INVALID|The provided peer id is invalid|
|400|PIN_RESTRICTED|You can't pin messages|
|400|USER_BANNED_IN_CHANNEL|You're banned from sending messages in supergroups/channels|
|406|AUTH_KEY_DUPLICATED|An auth key with the same ID was already generated|
|403|CHAT_WRITE_FORBIDDEN|You can't write in this chat|


