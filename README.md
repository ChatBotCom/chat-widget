# Chat Widget API

- [Chat Widget API](#chat-widget-api)
  * [Hooks](#hooks)
    + [onBeforeLoad](#onbeforeload)
    + [onLoad](#onload)
    + [onCreate](#oncreate)
    + [onDestroy](#ondestroy)
    + [onChatWindowOpen](#onchatwindowopen)
    + [onChatWindowClose](#onchatwindowclose)
    + [onChatWindowHide](#onChatWindowHide)
    + [onMessage](#onmessage)
    + [onStartConversation](#onstartconversation)
  * [Methods](#methods)
    + [create](#create)
    + [destroy](#destroy)
    + [isInitialized](#isInitialized)
    + [resetSession](#resetsession)
    + `deprecated` [openChat](#openchat)
    + [openChatWindow](#openChatWindow)
    + `deprecated` [closeChat](#closechat)
    + [closeChatWindow](#closeChatWindow)
    + [hideChatWindow](#hideChatWindow)
    + [isChatWindowOpened](#isChatWindowOpened)
    + [isChatWindowClosed](#isChatWindowClosed)
    + [isChatWindowHidden](#isChatWindowHidden)
    + [sendMessage](#sendmessage)
    + [sendTrigger](#sendtrigger)
    + `deprecated` [setUserParameters](#setUserParameters)
    + [setUserAttributes](#setUserAttributes)
    + `deprecated` [setCustomParameters](#setcustomparameters)
    + [setSessionAttributes](#setSessionAttributes)

## Hooks

### onBeforeLoad

Callback function invoked when widget code is loaded but chat window is not rendered yet.
You can return `false` to stop the widget initialization.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onBeforeLoad = function () {
    // return false
};
```

### onLoad

Callback function invoked when widget code is loaded and chat window is rendered.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    // ...
};
```

### onCreate

Callback function invoked after `create()` API method call.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onCreate = function () {
    // ...
};
```

### onDestroy

Callback function invoked after `destroy()` API method call.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onDestroy = function () {
    // ...
};
```

### onChatWindowOpen

Callback function invoked when the chat window is opened.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onChatWindowOpen = function () {
    // ...
};
```

### onChatWindowClose

Callback function invoked when the chat window is closed.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onChatWindowClose = function () {
    // ...
};
```

### onChatWindowHide

Callback function invoked when the chat window is hidden.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onChatWindowHide = function () {
    // ...
};
```

### onMessage

Callback function invoked after query result.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onMessage = function (result) {
    console.log(result)
};
```

### onStartConversation

Callback function invoked after the conversation starts.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onStartConversation = function () {
    // ...
};
```


## Methods

### create

Create chat widget if does not exist

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.create();
};
```

### destroy

Destroy chat widget if exist

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.destroy();
};
```

### isInitialized
Returns `true` if the chat is initialized.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.isInitialized();
};
```

### resetSession

Reset current session and recreate widget.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.resetSession();
};
```

### openChat

Deprecated, use: [openChatWindow](#openChatWindow)

### openChatWindow

Open the chat window, should be used only inside window.BE_API.onLoad callback

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.openChatWindow();
};
```

### closeChat

Deprecated, use: [closeChatWindow](#closeChatWindow)

### closeChatWindow

Close the chat window, should be used only inside window.BE_API.onLoad callback

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.closeChatWindow();
};
```

### hideChatWindow

Hide the chat window, should be used only inside window.BE_API.onLoad callback

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.hideChatWindow();
};
```

### isChatWindowOpened

Should be used only inside window.BE_API.onLoad callback.
Returns `true` if the chat window is open.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.isChatWindowOpened();
};
```

### isChatWindowClosed

Should be used only inside window.BE_API.onLoad callback.
Returns `true` if the chat window is closed.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.isChatWindowClosed();
};
```

### isChatWindowHidden

Should be used only inside window.BE_API.onLoad callback.
Returns `true` if the chat window is hidden.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.isChatWindowHidden();
};
```

###  setUserParameters

Deprecated, use: [setUserAttributes](#setUserAttributes)

###  setUserAttributes

Set user attributes. Read more about user attributes here:

https://www.chatbot.com/docs/users#update-user

#### Payload


| parameter | type                                                      | description         |
| --------- | --------------------------------------------------------- | ------------------- |
| `Object`  | Object( [Entry Object](#entry-object)(1, 99) ) `required` | Object with entries |



#### Entry Object

| parameter | type            | description     |
| --------- | --------------- | --------------- |
| `key`     | String(1, 128)  | Attribute name  |
| `value`   | String(1, 1024) | Attribute value |



```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.setUserAttributes({
        email: 'support@botengine.ai',
        name: 'Botengine Support'
    })
}
```

### setCustomParameters

Deprecated, use: [setSessionAttributes](#setSessionAttributes)

### setSessionAttributes

Set your custom attributes that will be sent to the query.
Each method call will overwrite existing parameters.
Read more about attributes here: https://www.botengine.ai/docs/talk-with-bot#parameters

#### Payload


| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `Object` | Object( [Entry Object](#entry-object)(1, 99) ) `required` | Object with entries                    |



#### Entry Object

| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `key` | String(1, 128) | Attribute name                         |
| `value` | String(1, 1024) | Attribute value |



```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.setSessionAttributes({
        email: 'support@botengine.ai',
        name: 'Botengine Support'
    })
}
```



### sendMessage

Send a message as visitor.


##### Payload


| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `payload.message` | String(1, 256) `required` | Message                                |
| `payload.postback` | String(1, 256) | Postback |


```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.sendMessage({
        message: 'message',
        postback: 'postback'
    })
}
```

### sendTrigger

Trigger the specific interaction.

#### Payload

| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `payload`  | String(1, 50) `required` | Trigger name                           |

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.sendTrigger('custom_trigger')
}
```
