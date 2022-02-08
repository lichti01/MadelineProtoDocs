---
title: "account.setContentSettings"
description: "Set sensitive content settings (for viewing or hiding NSFW content)"
grand_parent: "Telegram RPC API"
parent: "Methods"
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
redirect_from: /API_docs/methods/account_setContentSettings.html
---
# Method: account.setContentSettings
[Back to methods index](index.html)



Set sensitive content settings (for viewing or hiding NSFW content)

### Parameters:

| Name     |    Type       | Description | Required |
|----------|---------------|-------------|----------|
http://127.0.0.1:9503/api/account.setContentSettings/?data[sensitive_enabled]=true

### Return type: [Bool](/API_docs/types/Bool.html)

### Can bots use this method: **NO**


### MadelineProto Example ([now async for huge speed and parallelism!](https://docs.madelineproto.xyz/docs/ASYNC.html)):


```php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

$MadelineProto = new \danog\MadelineProto\API('session.madeline');
$MadelineProto->start();

$Bool = $MadelineProto->account->setContentSettings(['sensitive_enabled' => Bool, ]);
```

### Errors

| Code | Type     | Description   |
|------|----------|---------------|
|403|SENSITIVE_CHANGE_FORBIDDEN|You can't change your sensitive content settings.|


