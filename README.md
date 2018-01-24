# react-toast


还未发布到npm
## 用法

```js
// ES6
import Notifications, {notify} from '...../react-notify-toast';


```js
render() {
	return (
		<div className='main'>
			<Notifications />
			...
		</div>
	)
}

```

弹窗方法

```js

notify.show('Toasty!');

```

## 通知队列

通知队列可以使用createShowQueue函数.

````js
constructor() {
    super();
    this.show = notify.createShowQueue();
}
````

````js
this.show('Toasty!');
````

## 参数

显示参数
`notify.show(message, type, timeout, color)`


`message` :通知消息


`type` 通知类型:

- `success` 成功消息
- `warning` 警告消息
- `error` 错误消息
- `custom` 自定义消息

没有设置类型,就是用默认消息!


`timeout` 显示时间,默认5000ms,-1表示一直显示

`color` 样式,即背景和文本颜色

```js
let myColor = { background: '#0E1717', text: "#FFFFFF" };
notify.show("this is sample text", "custom", 5000, myColor);
```

createShowQueue方法有两个可选参数:

* `initialRecallDelay` 如果第一次尝试显示通知失败（因为未排队的通知已被显示），则要等待多长时间（以ms为单位））。 默认值：500ms

* `recallDelayIncrement` 是在每次失败的尝试后添加到RecallDelay的时间（以ms为单位）。 这是为了在没有超时的情况下显示非排队通知的情况下减轻许多快速重复的呼叫。 默认500ms
