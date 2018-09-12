# Jest

最近通过阿里的 Ant design Pro 项目研究了一下React的单元测试。

## Antd pro 中的测试

1. 单元测试
2. e2e测试

项目主要是用到了

`jest` facebook 的开源工具，和后端的断言测试工具类似.

`enzyme` airbnb 的开源工具，和JQuery的DOM操作类似.

`puppeteer` Google 的开源工具，用于做冒烟测试，模拟用户操作，企业级用于起来，可能由于网络下载插件问题，需要本地下载.

## 使用jest+enzyme 集成前端单元测试

### 安装jest

```bash
 npm i jest jest-cli
```

#### 配置

新建一个jest.config.js

```js
module.exports = {
  setupFiles: [
    require.resolve('./tests/shim.js'),
    require.resolve('./tests/setup.js'),
  ],
  transform: {
    '\\.js?$': require.resolve('./tests/transformers/jsTransformer'),
    '\\.ts?$': require.resolve('./tests/transformers/tsTransformer'),
  },
  testMatch: ['**/?(*.)(spec|test|e2e).(j|t)s?(x)'],
  moduleFileExtensions: ['js', 'jsx', 'ts', 'tsx'],
  setupTestFrameworkScriptFile: require.resolve('./tests/jasmine'),
  moduleNameMapper: {
    '\\.(css|less|sass|scss)$': require.resolve('identity-obj-proxy'),
  },
  globals: {
    'ts-jest': {
      useBabelrc: true,
    },
  },
  collectCoverage: true,
  collectCoverageFrom: [
    'containers/**/*.{ts,tsx,js,jsx}',
    'src/**/*.{ts,tsx,js,jsx}',
    '!**/*.d.ts',
  ],
  coveragePathIgnorePatterns: [
    './src/assets/*.*'
  ],
};
```

1. `setupFiles` 启动文件引入.
2. `transform` 文件转换.
3. `collectCoverage` 测试覆盖率
4. `coveragePathIgnorePatterns` 不匹配测试覆盖率的文件
5. `collectCoverageFrom` 覆盖文件
6. `testMatch` 单元测试匹配文件

```js
    "transform":{
        '\\.js?$': require.resolve('./tests/transformers/jsTransformer'),
    }
```

```js
...
{
  presets: [[require.resolve('../env/base.js'), {
    commonjs: true,
    disableTransform: true
  }]],
  plugins: [[require.resolve('babel-plugin-module-resolver'), {
    alias: {
      react: require.resolve('react'),
      'react-dom': require.resolve('react-dom'),
      enzyme: require.resolve('enzyme')
    }
  }]]
}
...
```

'babel-plugin-module-resolver' 这个插件集成了别名转换，可以解决webpack 设置了alias后，但愿测试翻译那些别名
该插件前身 jest-webpack-alias