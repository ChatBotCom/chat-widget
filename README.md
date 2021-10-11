# Chat Widget API

   * [Chat Widget API](#chat-widget-api)
      * [Hooks](#hooks)
         * [onBeforeLoad](#onbeforeload)
         * [onLoad](#onload)
         * [onDestroy](#ondestroy)
         * [onSessionReset](#onsessionreset)
         * [onChatWindowOpen](#onchatwindowopen)
         * [onChatWindowClose](#onchatwindowclose)
         * [onChatWindowHide](#onchatwindowhide)
         * [onMessage](#onmessage)
         * [onConversationStart](#onconversationstart)
         * [onConversationEnd](#onconversationend)
         * [onMomentOpen](#onmomentopen)
         * [onMomentClose](#onmomentclose)
         * [onMomentLoad](#onmomentload)
      * [Methods](#methods)
         * [create](#create)
         * [destroy](#destroy)
         * [openChatWindow](#openchatwindow)
         * [closeChatWindow](#closechatwindow)
         * [hideChatWindow](#hidechatwindow)
         * [isChatWindowOpened](#ischatwindowopened)
         * [isChatWindowClosed](#ischatwindowclosed)
         * [isChatWindowHidden](#ischatwindowhidden)
         * [isInitialized](#isinitialized)
         * [resetSession](#resetsession)
         * [sendMessage](#sendmessage)
            * [Payload](#payload)
         * [sendTrigger](#sendtrigger)
            * [Payload](#payload-1)
         * [openMoment](#openmoment)
         * [closeMoment](#closemoment)
         * [setSessionAttributes](#setsessionattributes)
            * [Payload](#payload-2)
            * [Entry Object](#entry-object)
         * [setUserAttributes](#setuserattributes)
            * [Payload](#payload-3)
            * [Entry Object](#entry-object-1)
         * [getUserData](#getuserdata)
         * [endChat](#endchat)
         * [hideGreeting](#hidegreeting)
         * [showGreeting](#showgreeting)


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

### onDestroy

Callback function invoked after `destroy()` API method call.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onDestroy = function () {
    // ...
};
```

### onSessionReset

Callback function invoked after `resetSession()` API method call.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onSessionReset = function () {
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

### onConversationStart

Callback function invoked after the conversation starts.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onConversationStart = function () {
    // ...
};
```

### onConversationEnd

Callback function invoked after the conversation ends.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onConversationEnd = function () {
    // ...
};
```

### onMomentOpen

Callback function invoked after the moment window is opened.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onMomentOpen = function () {
    // ...
};
```

### onMomentClose

Callback function invoked after the moment window is closed.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onMomentClose = function () {
    // ...
};
```

### onMomentLoad

Callback function invoked after the moment window is loaded.

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onMomentLoad = function () {
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

### openChatWindow

Open the chat window, should be used only inside window.BE_API.onLoad callback

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = function () {
    window.BE_API.openChatWindow();
};
```

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

### sendMessage

Send a message as visitor.


##### Payload


| parameter          | type                      | description |
| ------------------ | ------------------------- | ----------- |
| `payload.message`  | String(1, 256) `required` | Message     |
| `payload.postback` | String(1, 256)            | Postback    |


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

| parameter | type                     | description  |
| --------- | ------------------------ | ------------ |
| `payload` | String(1, 50) `required` | Trigger name |

```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.sendTrigger('custom_trigger')
}
```

### openMoment
Open moment.


##### Payload


| parameter        | type                              | description |
| ---------------- | --------------------------------- | ----------- |
| `payload.url`    | String(1, 2048) `required`        | Url         |
| `payload.height` | String(`full`, `tall`, `compact`) | Height      |


```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.openMoment({
        url: 'https://exampledomain.com',
        height: 'tall'
    })
}
```

### closeMoment
Closes opened "moment"

### setSessionAttributes

Set your custom attributes that will be sent to the query.
Each method call will overwrite existing parameters.
Read more about attributes here: https://www.chatbot.com/docs/talk-with-bot/#parameters

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
    window.BE_API.setSessionAttributes({
        email: 'support@chatbot.com',
        name: 'ChatBot Support'
    })
}
```

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
        email: 'support@chatbot.com',
        name: 'ChatBot Support'
    })
}
```

### getUserData
Returns the data of the current user.

### endChat
Ends an active conversation.

### hideGreeting
Hides active greeting

### showGreeting
Shows greeting.


##### Payload


| parameter | type                      | description      |
| --------- | ------------------------- | ---------------- |
| `message` | String(1, 256) `required` | Greeting message |


```javascript
window.BE_API = window.BE_API || {};

window.BE_API.onLoad = () => {
    window.BE_API.showGreeting('Greeting message')
}
```

