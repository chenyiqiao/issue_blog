1. 忽略数组的空位

```js
var sparse = [1,,3,,6]
var dense = a.filter(() => {
  return true
})
```

2. 遍历对象的属性
- for...in: （自身及继承的）可枚举属性
- Object.keys: 自身的可枚举属性
- Object.getOwnPropertyNames: 自身的全部属性

比较下来可以看出 `for...in` 是比较鸡肋的，因为很少会需要原型链上的（可枚举）属性。在`Object.keys`实现之前，通常会用以下代码来模拟实现：

```js
for (var i in obj) {
	if (obj.hasOwnProperty(i)) {
		//...
	}
}
```

有了`Object.keys`之后就不需要再这样做了。
