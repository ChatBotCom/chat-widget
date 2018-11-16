# Chat Widget API

- [Chat Widget API](#chat-widget-api)
  * [Hooks](#hooks)
    + [onBeforeLoad](#onbeforeload)
    + [onLoad](#onload)
    + [onCreate](#oncreate)
    + [onDestroy](#ondestroy)
    + [onChatWindowOpen](#onchatwindowopen)
    + [onChatWindowClose](#onchatwindowclose)
    + [onMessage](#onmessage)
  * [Methods](#methods)
    + [create](#create)
    + [destroy](#destroy)
    + [resetSession](#resetsession)
    + [openChat](#openchat)
    + [closeChat](#closechat)
    + [setCustomParameters](#setcustomparameters)
      - [Payload](#payload)
      - [Entry Object](#entry-object)
    + [sendMessage](#sendmessage)
        * [Payload](#payload-1)
    + [sendTrigger](#sendtrigger)
      - [Payload](#payload-2)

## Hooks

### onBeforeLoad

Callback function invoked when widget code is loaded but chat window is not rendered yet.
You can return `false` to stop the widget initialization.

```javascript
var BE_API = window.BE_API || {};

BE_API.onBeforeLoad = function () {
    // return false
};
```

### onLoad

Callback function invoked when widget code is loaded and chat window is rendered.

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    // ...
};
```

### onCreate

Callback function invoked after `create()` API method call.

```javascript
var BE_API = window.BE_API || {};

BE_API.onCreate = function () {
    // ...
};
```

### onDestroy

Callback function invoked after `destroy()` API method call.

```javascript
var BE_API = window.BE_API || {};

BE_API.onDestroy = function () {
    // ...
};
```

### onChatWindowOpen

Callback function invoked when the chat window is opened.

```javascript
var BE_API = window.BE_API || {};

BE_API.onChatWindowOpen = function () {
    // ...
};
```

### onChatWindowClose

Callback function invoked when the chat window is closed.

```javascript
var BE_API = window.BE_API || {};

BE_API.onChatWindowClose = function () {
    // ...
};
```

### onMessage

Callback function invoked after query result.

```javascript
var BE_API = window.BE_API || {};

BE_API.onMessage = function (result) {
    console.log(result)
};
```



## Methods

### create

Create chat widget if does not exist

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    BE_API.create();
};
```

### destroy

Destroy chat widget if exist

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    BE_API.destroy();
};
```

### resetSession

Reset current session and recreate widget.

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    BE_API.resetSession();
};
```

### openChat

Open the chat window, should be used only inside BE_API.onLoad callback

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    BE_API.openChat();
};
```

### closeChat

Close the chat window, should be used only inside BE_API.onLoad callback

```javascript
var BE_API = window.BE_API || {};

BE_API.onLoad = function () {
    BE_API.closeChat();
};
```

### setCustomParameters

Set your custom parameters that will be sent to the query.
Each method call will overwrite existing parameters.
Read more about parameters here: https://www.botengine.ai/docs/talk-with-bot#parameters

#### Payload


| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `Object` | Object( [Entry Object](#entry-object)(1, 99) ) `required` | Object with entries                    |



#### Entry Object

| parameter  | type              | description                                                  |
| ---------- | ----------------- | ------------------------------------------------------------ |
| `key` | String(1, 128) | Parameter name                         |
| `value` | String(1, 1024) | Parameter value |



```javascript
var BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.setCustomParameters({
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
var BE_API = window.BE_API || {};

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
var BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.sendTrigger('custom_trigger')
}
```
