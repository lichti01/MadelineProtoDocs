---
title: "updateChatParticipantAdmin"
description: "Admin permissions of a user in a legacy group were changed"
nav_exclude: true
image: https://docs.madelineproto.xyz/favicons/android-chrome-256x256.png
---
# Constructor: updateChatParticipantAdmin  
[Back to constructors index](/API_docs/constructors/index.html)



Admin permissions of a user in a [legacy group](https://core.telegram.org/api/channel) were changed

### Attributes:

| Name     |    Type       | Required | Description |
|----------|---------------|----------|-------------|
|chat\_id|[long](/API_docs/types/long.html) | Yes|
|user\_id|[long](/API_docs/types/long.html) | Yes|
|is\_admin|[Bool](/API_docs/types/Bool.html) | Yes|Whether the user was rendered admin|
|version|[int](/API_docs/types/int.html) | Yes|Used in basic groups to reorder updates and make sure that all of them was received.|



### Type: [Update](/API_docs/types/Update.html)


### Example:

```php
$updateChatParticipantAdmin = ['_' => 'updateChatParticipantAdmin', 'chat_id' => long, 'user_id' => long, 'is_admin' => Bool, 'version' => int];
```  
