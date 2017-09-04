## ES6中的const常量声明

const用于常量声明，ES6之前，并没有常量的声明。

示例:

```
const a = 10;
```

### const声明常量的特点

let和const声明的特性非常相似

1）唯一性

const常量声明只能被声明一次，且不允许重复赋值

```
const a = 10;
a = 20; // 报错
```

2）不存在变量提升

const和let一样不存在变量提升，不能在声明之前使用

```
console.log(a); // 报错
const a = 10;
```

3）受制于{}作用域

和let类似

```
{
   const a = 10;
}

console.log(a); // 未定义
```

4）使用场景

const声明的常量，通常用于带有唯一性特性的值，比如说模块声明，唯一性较高的构造函数声明等。

### const对象声明

1）const可以用于声明对象

示例：

```
const obj = {};
```

2) const对象声明允许拓展属性

```
const obj = {};
obj['a'] = 1; // 合法
```

3) const对象声明不允许重新**赋值**

```
const obj = {};
obj['a'] = 1; // 合法
const obj = {}; // 属于重新赋值行为 不合法
```

