# prop-types

```javascript
import PropTypes from 'prop-types'
myComponent.propTypes = {
    // 数组
  optionalArray: PropTypes.array,
  // 布尔值
  optionalBool: PropTypes.bool,
  // 函数
  optionalFunc: PropTypes.func,
  // 数值
  optionalNumber: PropTypes.number,
  // 对象
  optionalObject: PropTypes.object,
  // 字符串
  optionalString: PropTypes.string,
  // symbol
  optionalSymbol: PropTypes.symbol,
  // 能够被渲染的数值，字符串，元素或者包含这些类型的数组
  optionalNode: PropTypes.node,
  // React元素
  optionalElement: PropTypes.element,
  // optionalMessage是Message类的实例
  optionalMessage: PropTypes.instanceOf(Message),
  // optionalEnum为['News', 'Photos']中的其中一个
  optionalEnum: PropTypes.oneOf(['News', 'Photos']),
  //optionalUnion要么为字符串，要么为数值，要么为Message实例
  optionalUnion: PropTypes.oneOfType([
      PropTypes.string,
      PropTypes.number,
      PropTypes.instanceOf(Message)
    ]),
  // optionalArrayOf是数值类型的数组
  optionalArrayOf: PropTypes.arrayOf(PropTypes.number),
  // optionalObjectOf的属性是数值
  optionalObjectOf: PropTypes.objectOf(PropTypes.number),
  // requiredFunc是函数，且必须提供。isRequired可以链接到任何值后面
  requiredFunc: PropTypes.func.isRequired,
  // requiredAny可以是任何类型，且必须提供
  requiredAny: PropTypes.any.isRequired,
  // 自定义验证器。customProp中必须包含matchme
  customProp: function(props, propName, componentName) {
      if (!/matchme/.test(props[propName])) {
        return new Error(
          'Invalid prop `' + propName + '` supplied to' +
          ' `' + componentName + '`. Validation failed.'
        );
      }
  },  // 自定义数组，对象类型的验证器,验证器会调用数组或者对象中的每一个值,customArrayProp中的每一个值都要包含matchme
  customArrayProp: PropTypes.arrayOf(function(propValue, key, componentName, location, propFullName) {
    if (!/matchme/.test(propValue[key])) {
    return new Error(
      'Invalid prop `' + propFullName + '` supplied to' +
      ' `' + componentName + '`. Validation failed.'
    );
    }
  })
}
```