# WXSS(WeiXin Style Sheets)

> 是一套样式语言，用于描述 WXML 的组件样式

## 与 CSS 的不同点

1. 尺寸单位 rpx
2. 样式导入
3. 内联样式
4. 选择器

### 视觉单位

1. 设备像素 (device pixels)
2. CSS 像素 (CSS pixels)
3. PPI/DPI (pixel per inch)
4. DPR (devicepixlRatio)

## 样式

> 支持外联样式 `@import` 导入样式
> 支持内联样式 导入

## 选择器

1. `.class` 选择样式类 class=“”选择器
2. `#id` 选择 id=“” 选择器
3. `element` 选择所有 element 组件
4. `element element` 选择文档下 element 下的 element 组件
5. `::after` 在 view 组件后面插入内容
6. `::before` 在 view 组件前面插入内容

### 优先级问题

1. !important —— ∞
2. style —— 1000
3. #element —— 100
4. .element —— 10
5. element —— 1
