## `eventManager` Class



Module: [cc](../modules/cc.md)
Parent Module: [cc](../modules/cc.md)

This class is deprecated.

This class has been deprecated, please use cc.systemEvent or cc.EventTarget instead. See [Listen to and launch events](../../../manual/en/scripting/events.md) for details.<br>
<br>
cc.eventManager is a singleton object which manages event listener subscriptions and event dispatching.
The EventListener list is managed in such way so that event listeners can be added and removed
while events are being dispatched.


### Index



##### Methods

  - [`pauseTarget`](#pausetarget) Pauses all listeners which are associated the specified target.
  - [`resumeTarget`](#resumetarget) Resumes all listeners which are associated the specified target.
  - [`hasEventListener`](#haseventlistener) Query whether the specified event listener id has been added.
  - [`addListener`](#addlistener) <p>...
  - [`removeListener`](#removelistener) Remove a listener.
  - [`removeListeners`](#removelisteners) Removes all listeners with the same event listener type or removes all listeners of a node.
  - [`removeAllListeners`](#removealllisteners) Removes all listeners
  - [`setPriority`](#setpriority) Sets listener's priority with fixed value.
  - [`setEnabled`](#setenabled) Whether to enable dispatching events
  - [`isEnabled`](#isenabled) Checks whether dispatching events is enabled



### Details




<!-- Method Block -->
#### Methods


##### pauseTarget

Pauses all listeners which are associated the specified target.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:143](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L143) |

###### Parameters
- `node` <a href="../classes/Node.html" class="crosslink">Node</a> 
- `recursive` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### resumeTarget

Resumes all listeners which are associated the specified target.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:167](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L167) |

###### Parameters
- `node` <a href="../classes/Node.html" class="crosslink">Node</a> 
- `recursive` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### hasEventListener

Query whether the specified event listener id has been added.

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:719](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L719) |

###### Parameters
- `listenerID` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The listener id.


##### addListener

<p>
Adds a event listener for a specified event.<br/>
if the parameter "nodeOrPriority" is a node,
it means to add a event listener for a specified event with the priority of scene graph.<br/>
if the parameter "nodeOrPriority" is a Number,
it means to add a event listener for a specified event with the fixed priority.<br/>
</p>

| meta | description |
|------|-------------|
| Returns | <a href="../classes/EventListener.html" class="crosslink">EventListener</a> 
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:730](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L730) |

###### Parameters
- `listener` <a href="../classes/EventListener.html" class="crosslink">EventListener</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The listener of a specified event or a object of some event parameters.
- `nodeOrPriority` <a href="../classes/Node.html" class="crosslink">Node</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The priority of the listener is based on the draw order of this node or fixedPriority The fixed priority of the listener.


##### removeListener

Remove a listener.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:807](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L807) |

###### Parameters
- `listener` <a href="../classes/EventListener.html" class="crosslink">EventListener</a> an event listener or a registered node target

##### Examples

```js

// 1. remove eventManager add Listener;
var mouseListener1 = cc.eventManager.addListener({
    event: cc.EventListener.MOUSE,
    onMouseDown:  function(keyCode, event){ },
    onMouseUp: function(keyCode, event){ },
    onMouseMove: function () { },
    onMouseScroll: function () { }
}, node);

cc.eventManager.removeListener(mouseListener1);

// 2. remove eventListener create Listener;
var mouseListener2 = cc.EventListener.create({
    event: cc.EventListener.MOUSE,
    onMouseDown:  function(keyCode, event){ },
    onMouseUp: function(keyCode, event){ },
    onMouseMove: function () { },
    onMouseScroll: function () { }
});

cc.eventManager.removeListener(mouseListener2);

```

##### removeListeners

Removes all listeners with the same event listener type or removes all listeners of a node.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:901](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L901) |

###### Parameters
- `listenerType` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> &#124; <a href="../classes/Node.html" class="crosslink">Node</a> listenerType or a node
- `recursive` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### removeAllListeners

Removes all listeners

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:985](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L985) |



##### setPriority

Sets listener's priority with fixed value.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:998](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L998) |

###### Parameters
- `listener` <a href="../classes/EventListener.html" class="crosslink">EventListener</a> 
- `fixedPriority` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### setEnabled

Whether to enable dispatching events

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:1028](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L1028) |

###### Parameters
- `enabled` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### isEnabled

Checks whether dispatching events is enabled

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| Defined in | [cocos2d/core/event-manager/CCEventManager.js:1038](https://github.com/cocos-creator/engine/blob/d6ec4c03aa86f40af14d21ef9f059fed5e540c58/cocos2d/core/event-manager/CCEventManager.js#L1038) |




