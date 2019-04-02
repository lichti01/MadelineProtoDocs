---
title: account.sendChangePhoneCode
description: Change the phone number
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
---
# Method: account.sendChangePhoneCode  
[Back to methods index](index.md)


Change the phone number

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
|phone\_number|[string](../types/string.md) | New phone number | Yes|
|settings|[CodeSettings](../types/CodeSettings.md) | Code settings | Yes|


### Return type: [auth\_SentCode](../types/auth_SentCode.md)

### Can bots use this method: **NO**


### MadelineProto Example:


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
define('MADELINE_BRANCH', '');
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$auth_SentCode = $MadelineProto->account->sendChangePhoneCode(['phone_number' => 'string', 'settings' => CodeSettings, ]);
```

Or, if you're into Lua:

```lua
auth_SentCode = account.sendChangePhoneCode({phone_number='string', settings=CodeSettings, })
```

### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|PHONE_NUMBER_INVALID|The phone number is invalid|

