# DeviceEventEmitter 事件管理

## DeviceEventEmitter使用方法

注册一个监听事件：
this.subscription = DeviceEventEmitter.addListener('userNameDidChange',(userName) =>{
    alert('通知');
})

清除一个监听事件：
this.subscription.remove();

这样就会遇到一个问题，当注册的事件太多的时候就会造成代码的冗余和事件的管理困难，所以我将监听事件的创建，查询和删除封装在一个类当中，便于监听事件的管理

## 功能

1、链式添加监听事件
2、链式删除监听事件
3、得到所有注册的监听事件

##使用方法

### 引入模块儿

import EventListener from './index';

1、链式添加监听事件：
const event1 = {
    eventListenerFirst:() => {},
}

const event2 = {
    eventListenerSecond:() => {},
}

EventListener.addEventListen(event1).addEventListen(event2);

2、链式删除监听事件
EventListener.clearEventListen(eventListenerFirst).clearEventListen(eventListenerSecond);
或者 不穿入任何参数而将所有的监听时间删除掉
EventListener.clearEventListen();

3、得到所有注册的监听事件
const eventListener = EventListener.ventListener;