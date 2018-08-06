## Reducer

reducer 是一个函数，接受 state 和 action，返回老的或新的 state 。即：`(state, action) => state`

### 增删改

以 todos 为例。

```javascript
app.model({
  namespace: 'todos',
  state: [],
  reducers: {
    add(state, { payload: todo }) {
      return state.concat(todo);
    },
    remove(state, { payload: id }) {
      return state.filter(todo => todo.id !== id);
    },
    update(state, { payload: updatedTodo }) {
      return state.map(todo => {
        if (todo.id === updatedTodo.id) {
          return { ...todo, ...updatedTodo };
        } else {
          return todo;
        }
      });
    },
  },
};
```

### 嵌套数据的增删改

建议最多一层嵌套，以保持 state 的扁平化，深层嵌套会让 reducer 很难写和难以维护。

```javascript
app.model({
  namespace: 'app',
  state: {
    todos: [],
    loading: false,
  },
  reducers: {
    add(state, { payload: todo }) {
      const todos = state.todos.concat(todo);
      return { ...state, todos };
    },
  },
});
```

下面是深层嵌套的例子，应尽量避免。

```javascript
app.model({
  namespace: 'app',
  state: {
    a: {
      b: {
        todos: [],
        loading: false,
      },
    },
  },
  reducers: {
    add(state, { payload: todo }) {
      const todos = state.a.b.todos.concat(todo);
      const b = { ...state.a.b, todos };
      const a = { ...state.a, b };
      return { ...state, a };
    },
  },
});
```

## Effect

示例：

```javascript
app.model({
  namespace: 'todos',
  effects: {
    *addRemote({ payload: todo }, { put, call }) {
      yield call(addTodo, todo);
      yield put({ type: 'add', payload: todo });
    },
  },
});
```

### Effects

#### put

用于触发 action 。

```javascript
yield put({ type: 'todos/add', payload: 'Learn Dva' });
```

#### call

用于调用异步逻辑，支持 promise 。

```javascript
const result = yield call(fetch, '/todos');
```

#### select

用于从 state 里获取数据。

```javascript
const todos = yield select(state => state.todos);
```

### 错误处理

#### 全局错误处理

dva 里，effects 和 subscriptions 的抛错全部会走 `onError` hook，所以可以在 `onError` 里统一处理错误。

```javascript
const app = dva({
  onError(e, dispatch) {
    console.log(e.message);
  },
});
```

然后 effects 里的抛错和 reject 的 promise 就都会被捕获到了。

#### 本地错误处理

如果需要对某些 effects 的错误进行特殊处理，需要在 effect 内部加 `try catch` 。

```javascript
app.model({
  effects: {
    *addRemote() {
      try {
        // Your Code Here
      } catch(e) {
        console.log(e.message);
      }
    },
  },
});
```

### 异步请求

异步请求基于 whatwg-fetch，API 详见： `https://github.com/github/fetch`

#### GET 和 POST

```javascript
import request from '../util/request';

// GET
request('/api/todos');

// POST
request('/api/todos', {
  method: 'POST',
  body: JSON.stringify({ a: 1 }),
});
```

#### 统一错误处理

假如约定后台返回以下格式时，做统一的错误处理。

```javascript
{
  status: 'error',
  message: '',
}
```

编辑 `utils/request.js`，加入以下中间件：

```javascript
function parseErrorMessage({ data }) {
  const { status, message } = data;
  if (status === 'error') {
    throw new Error(message);
  }
  return { data };
}
```

然后，这类错误就会走到 `onError` hook 里。

## Subscription

`subscriptions` 是订阅，用于订阅一个数据源，然后根据需要 dispatch 相应的 action。数据源可以是当前的时间、服务器的 websocket 连接、keyboard 输入、geolocation 变化、history 路由变化等等。格式为 `({ dispatch, history }) => unsubscribe` 。

### 异步数据初始化

比如：当用户进入 `/users` 页面时，触发 action `users/fetch` 加载用户数据。

```javascript
app.model({
  subscriptions: {
    setup({ dispatch, history }) {
      history.listen(({ pathname }) => {
        if (pathname === '/users') {
          dispatch({
            type: 'users/fetch',
          });
        }
      });
    },
  },
});
```

#### `path-to-regexp` Package

如果 url 规则比较复杂，比如 `/users/:userId/search`，那么匹配和 userId 的获取都会比较麻烦。这是推荐用 [path-to-regexp](https://github.com/pillarjs/path-to-regexp) 简化这部分逻辑。

```javascript
import pathToRegexp from 'path-to-regexp';

// in subscription
const match = pathToRegexp('/users/:userId/search').exec(pathname);
if (match) {
  const userId = match[1];
  // dispatch action with userId
}
```

## Router

### Config with JSX Element (router.js)

```javascript
<Route path="/" component={App}>
  <Route path="accounts" component={Accounts}/>
  <Route path="statements" component={Statements}/>
</Route>
```

详见：[react-router](https://github.com/reactjs/react-router/blob/master/docs/guides/RouteConfiguration.md)