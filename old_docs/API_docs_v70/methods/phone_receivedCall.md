---
title: phone.receivedCall
description: phone.receivedCall parameters, return type and example
---
## Method: phone.receivedCall  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|peer|[InputPhoneCall](../types/InputPhoneCall.md) | Yes|


### Return type: [Bool](../types/Bool.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CALL_ALREADY_DECLINED|The call was already declined|
|CALL_PEER_INVALID|The provided call peer object is invalid|


### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
$MadelineProto->session = 'mySession.madeline';
if (isset($number)) { // Login as a user
    $MadelineProto->phone_login($number);
    $code = readline('Enter the code you received: '); // Or do this in two separate steps in an HTTP API
    $MadelineProto->complete_phone_login($code);
}

$Bool = $MadelineProto->phone->receivedCall(['peer' => InputPhoneCall, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/phone.receivedCall`

Parameters:

peer - Json encoded InputPhoneCall




Or, if you're into Lua:

```
Bool = phone.receivedCall({peer=InputPhoneCall, })
```

