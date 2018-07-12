
## React Component

###  React 定义

React Component 有 3 种定义方式，分别是 

1⃣️`React.createClass`,类似JS各种库插件的写法。

2⃣️`class`, 类似Java。

3⃣️`pure function`。官方说是`Stateless Functional Component` ,社区有些使用这一种，保持简洁和无状态。这是函数，不是 Object，没有 `this` 作用域，是 pure function。（个人觉的第二种更优雅些）

比如定义 App Component ： 同上 3⃣️

```javascript
function App(props) {
  function handleClick() {
    props.dispatch({ type: 'app/create' });
  }
  return <div onClick={handleClick}>${props.name}</div>
}
```

等同于（同上 2⃣️）：

```javascript
class App extends React.Component {
  handleClick() {
    this.props.dispatch({ type: 'app/create' });
  }
  render() {
    return <div onClick={this.handleClick.bind(this)}>${this.props.name}</div>
  }
}
```

### JSX

  #### 基础认识

  从本质上讲，
  JSX 只是为 `React.createElement(component, props, ...children)`
  
  官方上、社区上为 函数提供的语法糖

```html
<MyButton color="blue" shadowSize={2}>
  Click Me
</MyButton>
```

通过编译后为:

```javascript
React.createElement(
  MyButton,
  {color: 'blue', shadowSize: 2},
  'Click Me'
)
```

注意点：React定义组件必须首字母大写！！！

官方解释：
    首字母大写的标签指示 JSX 标签是一个 React 组件。这些标签会被编译成 命名变量 的直接引用。所以如果你使用 JSX <Foo /> 表达式，那么 Foo 必须在作用域中。

#### Component 嵌套

类似 HTML，JSX 里可以给组件添加子组件。

```html
<App>
  <Header />
  <MainContent />
  <Footer />
</App>
```

#### className

我们在写标签时候为了外观更加友好，需要写样式，style并提取到`css`文件中，`html`的 标签使用

```css
.headerStyle{
  width:300px,
  color:red,
}
```

```html
<div class="headerStyle"></div>
```

语法糖上  react可以这样写
```javascript
class App extends React.Component {

}
```

使得：
`class` 是保留词，所以添加样式时，需用 `className` 代替 `class` 。

```html
<H className="fancy">React</H>
```

#### JavaScript 表达式

JavaScript 表达式需要用 `{}` 括起来，会执行并返回结果。

比如：

```javascript
<h1>{ this.props.title }</h1>
```

```javascript
<h1>{ obj ? 'a': 'b'  }</h1>
```

#### List map加载

可以把数组映射为 JSX 元素列表。

```javascript
const { todo } = this.props
<Select>
  { todos.map((todo, i) => <Option key={i} value={i}>{todo}</Option>) }
</Select>
```

#### 注释

1⃣️ `//`
2⃣️ `{/* */}`

```javascript
<h1>
  {/* multiline comment */}
  {/*
    multi
    line
    comment
    */}
  {
    // single line
  }
  Hello
</h1>
```

尽量别用 `//` 做单行注释。

当然如果遇到舍不得删除，组件下的属性的话 还是用`//`，用`{/* */}`会有问题。

```javascript
const {coloums,dataSouce,className} = this.state;
<Table
  coloums={coloums}
  dataSouce={dataSouce}
  //className={className}
>
```


#### 常用特性

这是 JSX 从 ECMAScript6 借鉴过来的很有用的特性，

叫做扩展运算符，用于扩充组件 props 。可以少写不少重复代码。

比如：

```javascript
const attrs = {
  href: 'http://pingan.com',
  target: '_blank',
};
<a {...attrs}>Hello</a>
```

等同于

```javascript
const attrs = {
  href: 'http://pingan.com',
  target: '_blank',
};
<a href={attrs.href} target={attrs.target}>Hello</a>
```

### Props

数据处理在 React 中是非常重要的概念之一
属于父亲组件传递传递给子组件的属性
```javascript
class Father extends React.Component {
  render(){
     return （<div>
        <Son title={123}/>
    </div>）
  }
}

class Son extends React.Component {
    render(){
      const {title} = this.props;
      return 
      （<div>
        {title}
      </div>）
    }
}
```

### propTypes

JavaScript 是弱类型语言，所以请尽量声明 propTypes 对 props 进行校验，以减少不必要的问题。

```javascript
function App(props) {
  return <div>{props.name}</div>;
}
App.propTypes = {
  name: React.PropTypes.string.isRequired,
};
```

内置的 prop type 有：

- PropTypes.number
- PropTypes.object
- PropTypes.string
- PropTypes.array
- PropTypes.bool
- PropTypes.func


#### 往下传数据

![](./vonder/img/NAzeMyUoPMqxfRv.png)

#### 往上传数据

![](./vonder/img/fiKKgDGuEJfSvxv.png)


### State

```javascript
class Son extends React.Component {
    constructor(props){
      super(props);
      this.state={
        action:123,
        face:true,
      }
    }

    hanldeClick =() =>{
      this.setState({
        face:false
      })
    }

    render(){
      const {action,face} = this.state;
      return 
      （<div>
        {
          face
          ?<div>{action}</div>
          :null
        }
        <div onClick={his.hanldeClick} >
      </div>）
    }
}
```

### CSS Modules

一张图理解 CSS Modules 的工作原理：

![](./vonder/img/SWBwWTbZKqxwEPq.png)
