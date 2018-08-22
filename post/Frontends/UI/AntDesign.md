# Ant Design

## 组件

### 通用

#### Button

>TypeScript源

##### button——index导出

```ts
import Button from './button';
export { ButtonProps, ButtonShape, ButtonSize, ButtonType } from './button';
export { ButtonGroupProps } from './button-group';
export default Button;
```

这里导出了Button组件

关联枚举属性值  `ButtonShape`,`ButtonSize`,`ButtonType`,

```ts
export declare type ButtonType = 'primary' | 'ghost' | 'dashed' | 'danger';
export declare type ButtonShape = 'circle' | 'circle-outline';
export declare type ButtonSize = 'small' | 'default' | 'large';
```

实现的属性接口

```ts
export interface ButtonProps {
    type?: ButtonType;
    htmlType?: string;
    icon?: string;
    shape?: ButtonShape;
    size?: ButtonSize;
    onClick?: React.FormEventHandler<any>;
    onMouseUp?: React.FormEventHandler<any>;
    onMouseDown?: React.FormEventHandler<any>;
    onKeyPress?: React.KeyboardEventHandler<any>;
    onKeyDown?: React.KeyboardEventHandler<any>;
    tabIndex?: number;
    loading?: boolean | {
        delay?: number;
    };
    disabled?: boolean;
    style?: React.CSSProperties;
    prefixCls?: string;
    className?: string;
    ghost?: boolean;
    target?: string;
    href?: string;
    download?: string;
}
```

样式文件在组件目录下style，全局导出.首先都集成了全局主题样式

```less
@import "../../style/themes/default";
@import "../../style/mixins/index";
@import "./mixin";
```

### 布局

### 导航

### 数据入口

### 数据展现

### 反馈
