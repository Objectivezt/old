# lifeCycle、Router、Event

## App LifeCycle

1. onLaunch
2. onShow
3. onHide
4. onError

globalData

## MinApp Page LifeCycle

1. onLoad
2. onShow
3. onReady
4. onHide
5. onUnload

data

## Router

> 维护一个栈

1. 初始化 ——————新页面入栈
2. 打开新页面 ——————新页面入栈
3. 页面重定向 ——————当前页面出栈，新页面入栈
4. 页面返回 ———————页面不断出栈，直到目标返回页，新页面入栈
5. Tab 切换 ——————页面全部出栈，只留下新的 Tab 页面
6. 重加载 ——————页面全部出栈，只留下新的页面

## Event

### Event Object

1. type 时间类型
2. timeStamp 触发事件的事件戳
3. target 根源组件
4. currentTarget 事件绑定的当前组件
5. touches 当前对象停留点
6. changed Touches 变化的触摸点
7. details 绑定事件信息

### Event Action

1. 事件捕获阶段
2. 事件处理阶段
3. 事件冒泡阶段

#### 可捕获事件

1. touchstart
2. touchmove
3. touchcancel
4. touchend
5. tap
6. longpress
7. longtap

#### 可冒泡事件

1. 上述可捕获事件都可以冒泡
2. transitionend
3. animationstart
4. animationiteration
5. animationend
6. touchforcechange
7.
