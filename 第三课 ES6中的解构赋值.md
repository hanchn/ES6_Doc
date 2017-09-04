## ES6中的解构赋值

解构赋值用于按照一定的结构进行更灵活地单值或者多值赋值。

1) 基本示例：

```
let [a, b, c] = [1, 2, 3];
```

2) 结构赋值特性

结构赋值必须按照一定结构进行对称赋值，否则将报错：

```
let [a] = 10; // 报错
```

### 类数组结构解构赋值

1）类数组结构解构赋值

基本示例：
```
let [a, b, c] = [1, 2, 3];
console.log('a: ' + a);  // a: 1
console.log('b: ' + b);  // b: 2
console.log('c: ' + c);  // c: 3
```

2) 类数组结构嵌套赋值

基本示例：
```
let [a, [b, c]] = [1, [2, 3]];
console.log('a: ' + a);  // a: 1
console.log('b: ' + b);  // b: 2
console.log('c: ' + c);  // c: 3
```

3) 类数组结构缺省赋值

基本示例：
```
let [a, [b, c]] = [1, [2, ]];
console.log('a: ' + a);  // a: 1
console.log('b: ' + b);  // b: 2
console.log('c: ' + c);  // c: undefined
```

4) 交换赋值

```
let [a, b] = [1, 2];
[a, b] = [b, a];
console.log('a: ' + a);  // a: 2
console.log('b: ' + b);  // b: 1
```

### 类对象结构解构赋值

1）类对象结构解构赋值

为对象解构进行解构赋值时要注意，名可以不是标准对象解构，但赋值必须按照对象解构进行赋值操作。

```
let {a, b, c} = {a: 1, b: 2, c: 3};
console.log('a: ' + a);  // a: 1
console.log('b: ' + b);  // b: 2
console.log('c: ' + c);  // c: 3
```

2）注意对象解构赋值的**被赋值者**

*注意：在进行对象类型的解构赋值的时候，千万不要把索引/属性名当成变量名，属性值才是变量。

```
let {a: b} = {a: 1};
console.log("b: " + b); // b: 1
console.log("a: " + a); // a 未定义
```

3）缺省赋值

以下示例直接无法运行，会发生报错。
对象中的缺省赋值类似于给对象赋值，不允许赋如下空值。

```
let {a, b, c} = {a: , b: 2, c: 3}; // 报错
console.log('a: ' + a);  // a: 1
console.log('b: ' + b);  // b: 2
console.log('c: ' + c);  // c: 3
```

4）空值赋值

```
let {a} = {};
console.log(a);
```

5) 复杂解构赋值

```
let {a: {b: c}} = {a: {b: 1}};
// console.log(a); // a未定义
// console.log(b); // b未定义
console.log(c); // c: 1
```

### 嵌套结构赋值

嵌套解构赋值类似于组合赋值，可以将数组结构和对象解构嵌套复合

基础示例：

```
let {a: [b]} = {a: [1]};
console.log(b);  // b: 1
```

