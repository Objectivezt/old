# TypeScript-React-Starter

## 下载 create-react-app

> 这是一个创建react应用的脚手架

```bash
npm install -g create-react-app
```

## 创建一个 react项目

```bash
create-react-app react-ts --scripts-version=react-scripts-ts
```

### 生成目录结构

```tree
react-ts/
├─ .gitignore
├─ images.d.ts
├─ node_modules/
├─ public/
├─ src/
│  └─ ...
├─ package.json
├─ tsconfig.json
├─ tsconfig.prod.json
├─ tsconfig.test.json
└─ tslint.json
```

### 修改配置tslint文件

```json
 {
-  "extends": ["tslint:recommended", "tslint-react", "tslint-config-prettier"],
+  "extends": [],
+  "defaultSeverity": "warning",
   "linterOptions": {
     "exclude": [
       "config/**/*.js",
       "node_modules/**/*.ts",
       "coverage/lcov-report/*.js"
     ]
   }
 }
```

### 执行命令

> 启动

```bash
npm run start
```

>运行测试

```bash
npm run test
```

>执行打包命令

```bash
npm run build
```

## 创建组件

> 创建一个带Props带State带组件

```tsx
import * as React from "react";

export interface Props {
  name: string;
  enthusiasmLevel?: number;
}

interface State {
  currentEnthusiasm: number;
}

class Hello extends React.Component<Props, State> {
  constructor(props: Props) {
    super(props);
    this.state = { currentEnthusiasm: props.enthusiasmLevel || 1 };
  }

  onIncrement = () => this.updateEnthusiasm(this.state.currentEnthusiasm + 1);
  onDecrement = () => this.updateEnthusiasm(this.state.currentEnthusiasm - 1);

  render() {
    const { name } = this.props;

    if (this.state.currentEnthusiasm <= 0) {
      throw new Error('You could be a little more enthusiastic. :D');
    }

    return (
      <div className="hello">
        <div className="greeting">
          Hello {name + getExclamationMarks(this.state.currentEnthusiasm)}
        </div>
        <button onClick={this.onDecrement}>-</button>
        <button onClick={this.onIncrement}>+</button>
      </div>
    );
  }

  updateEnthusiasm(currentEnthusiasm: number) {
    this.setState({ currentEnthusiasm });
  }
}

export default Hello;

function getExclamationMarks(numChars: number) {
  return Array(numChars + 1).join('!');
}
```

> 导入 css

```css
.hello {
  text-align: center;
  margin: 20px;
  font-size: 48px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.hello button {
  margin-left: 25px;
  margin-right: 25px;
  font-size: 40px;
  min-width: 50px;
}
```

```tsx
import './Hello.css';
```