## ES6中的箭头函数

ES6针对带有返回值的函数做了语法糖的处理，是的函数书写更加简洁。

1）ES6之前的书写方式：

```
var fun = function(val){
    return val;
}
```

2）箭头函数

```
let fun = val => val;
console.log(fun(10));
```

### 多场景中的箭头函数

1） 基础示例

```
let fun = val => val;
console.log(fun(10));
```

2） 多参数示例

多参数传递需要借助括号

```
let fun = （a, b） => a + b;
console.log(fun(1, 2));
```

3） 返回值为对象

如果返回值为对象，则需要用利用（）表达式包裹住对象，因为{}在ES6中被解析为花括号作用域。

```
let fun = （a, b） => ({c: a, d: b});
console.log(fun(1, 2));
```


