# JavaScript 函数式编程简介

## 一、案例

- 案例一

```javascript
function splat (fun) {
  return function(array) {
    return fun.apply(null, array)
  }
}
var addEleFun = splat(function (x, y) {
  return x + y
})
addEleFun([1, 2]) // 3
```

个人理解

> 通过这样写的一大好处是行为与结果分步进行，更好的解耦、组合

- 案例二

```javascript
function unsplat(fun) {
  return function() {
    return fun.call(null. _.toArray(arguments))
  }
}
var joinEle = unsplat(function(array) {
  return array.join(' ')
})
joinEle('1', '$', '&')
// 1 $ &
```

注：`apply` 将参数放到数组中调用，`call` 与方法参数一样


## 二、开始函数式编程

### 函数式初始

- `existy` 函数，主要用于 `null` 与 `undefined` 值判断，注意使用的是 `!=` 不是 `!==`

```javascript
function existy(x) {
  return x != null
}
existy(null) // false
existy(undefined) // false
existy(0) // true
existy(false) // true
```

- `truthy` 函数，用于 `真` 值判断，主要为 `false`、 `null`、`undefined`三个值， 如果希望数字 `0` 也为 `假` 值，请不要用这个方法

```javascript
function truthy(x) {
  return x !== false && existy(x)
}
truthy(0) // true
truthy(false) // false
truthy(undefined) // false
truthy(null) // false
```

### 加速

- 静态分析器
- 谷歌的闭包编译器([Goggle's Closure compiler](https://github.com/google/closure-compiler/))


## 三、总结

- 确定抽象，并为其构建函数
- 利用已有的函数来构建更为复杂的抽象
- 通过将现有的函数传给其他的函数来构建更加复杂的抽象
