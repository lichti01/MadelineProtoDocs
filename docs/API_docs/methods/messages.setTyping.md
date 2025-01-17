---
title: "messages.setTyping"
description: "Sends a current user typing event (see [SendMessageAction](../types/SendMessageAction.html) for all event types) to a conversation partner or group."
grand_parent: "Telegram RPC API"
parent: "Methods"
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
redirect_from: /API_docs/methods/messages_setTyping.html
---
# Method: messages.setTyping
[Back to methods index](index.html)



Sends a current user typing event (see [SendMessageAction](../types/SendMessageAction.html) for all event types) to a conversation partner or group.

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|peer|[Username, chat ID, Update, Message or InputPeer](/API_docs/types/InputPeer.html) | Target user or group | Optional|
|top\_msg\_id|[int](/API_docs/types/int.html) | [Thread ID](https://core.telegram.org/api/threads) | Optional|
|action|[SendMessageAction](/API_docs/types/SendMessageAction.html) | Type of action<br>Parameter added in [Layer 17](https://core.telegram.org/api/layers#layer-17). | Yes|


### Return type: [Bool](/API_docs/types/Bool.html)

### Can bots use this method: **YES**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$Bool = $MadelineProto->messages->setTyping(['peer' => InputPeer, 'top_msg_id' => int, 'action' => SendMessageAction, ]);
```

### Errors

| Code | Type     | Description   |
|------|----------|---------------|
|400|CHANNEL_INVALID|The provided channel is invalid|
|400|CHANNEL_PRIVATE|You haven't joined this channel/supergroup|
|400|CHAT_ADMIN_REQUIRED|You must be an admin in this chat to do this|
|400|CHAT_ID_INVALID|The provided chat id is invalid|
|400|INPUT_FETCH_FAIL|Failed deserializing TL payload|
|400|INPUT_USER_DEACTIVATED|The specified user was deleted|
|400|MSG_ID_INVALID|Invalid message ID provided|
|400|PEER_ID_INVALID|The provided peer id is invalid|
|400|USER_BANNED_IN_CHANNEL|You're banned from sending messages in supergroups/channels|
|400|USER_IS_BLOCKED|You were blocked by this user|
|400|USER_IS_BOT|Bots can't send messages to other bots|
|406|AUTH_KEY_DUPLICATED|An auth key with the same ID was already generated|
|403|CHAT_WRITE_FORBIDDEN|You can't write in this chat|
|403|USER_IS_BLOCKED|You were blocked by this user|
|-503|Timeout|Timeout while fetching data|


