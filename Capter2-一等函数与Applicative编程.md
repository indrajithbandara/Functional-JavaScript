# Capter2-一等函数与Applicative编程

## 函数式一等公民

> 函数式语言应该是促进创造和使用函数的。“一等”通常用来描述值，但函数被看作“一等公民”时，它就可以去任何值可以去的地方

一个高阶函数应该可以执行下列至少一项操作
- 以一个函数作为参数
- 返回一个函数作为结果

### 多种JavaScript编程方式

- 命令式编程，通过详细描述行为的编程方式
- 基于原型的面向对象编程，基于原型对象及其示例的编程方式
- 元编程，对JavaScript执行模型数据进行编写和操作的编程方式

元编程示例

```javascript
function Point2D(x, y) {
  this._x = x
  this._y = y
}
new Point2D(0, 1)
// {_x: 0, _y: 1}
function Point3D(x, y, z) {
  Point2D.call(this, x, y)
  this._z = z
}
```

## Applicative 编程

> Applicative编程定义为函数A作为参数提供给函数B，如 `_.map`、`_.reduce`、`_.filter`

### 集合中心编程

Alan Perlis 提出

> 用100个函数操作一个数据结构，比用10个函数操作10个数据结构要好。

## 数据思考

### “表状（Table-Like）”数据
