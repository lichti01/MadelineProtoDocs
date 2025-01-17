---
title: "auth.sendCode"
description: "You cannot use this method directly, use the phoneLogin method instead (see https://docs.madelineproto.xyz for more info)"
grand_parent: "Telegram RPC API"
parent: "Methods"
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
redirect_from: /API_docs/methods/auth_sendCode.html
---
# Method: auth.sendCode
[Back to methods index](index.html)



You cannot use this method directly, use the phoneLogin method instead (see https://docs.madelineproto.xyz for more info)

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|phone\_number|[string](/API_docs/types/string.html) | Phone number in international format | Yes|
|api\_id|[int](/API_docs/types/int.html) | Application identifier (see [App configuration](https://core.telegram.org/myapp)) | Yes|
|api\_hash|[string](/API_docs/types/string.html) | Application secret hash (see [App configuration](https://core.telegram.org/myapp)) | Yes|
|settings|[CodeSettings](/API_docs/types/CodeSettings.html) | Settings for the code type to send | Yes|


### Return type: [auth.SentCode](/API_docs/types/auth.SentCode.html)

### Can bots use this method: **NO**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$auth_SentCode = $MadelineProto->auth->sendCode(['phone_number' => 'string', 'api_id' => int, 'api_hash' => 'string', 'settings' => CodeSettings, ]);
```

### Errors

| Code | Type     | Description   |
|------|----------|---------------|
|400|API_ID_INVALID|API ID invalid|
|400|API_ID_PUBLISHED_FLOOD|This API id was published somewhere, you can't use it now|
|400|INPUT_REQUEST_TOO_LONG|The request is too big|
|400|PHONE_NUMBER_APP_SIGNUP_FORBIDDEN|You can't sign up using this app|
|400|PHONE_NUMBER_BANNED|The provided phone number is banned from telegram|
|400|PHONE_NUMBER_FLOOD|You asked for the code too many times.|
|400|PHONE_NUMBER_INVALID|The phone number is invalid|
|400|PHONE_PASSWORD_PROTECTED|This phone is password protected|
|400|SMS_CODE_CREATE_FAILED|An error occurred while creating the SMS code|
|406|AUTH_KEY_DUPLICATED|An auth key with the same ID was already generated|
|406|PHONE_NUMBER_INVALID|The phone number is invalid|
|406|PHONE_PASSWORD_FLOOD|You have tried logging in too many times|
|401|AUTH_KEY_PERM_EMPTY|The temporary auth key must be binded to the permanent auth key to use these methods.|
|-500|No workers running|Internal error|
|-503|Timeout|Timeout while fetching data|


