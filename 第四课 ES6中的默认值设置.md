## ES6中的默认值设置

ES6中允许直接进行默认值的设置，常用场景有解构赋值默认值设置及函数参数默认值设置。

ES6之前默认值设置方式基础示例：

```
function fun(a){
    var val = a || 10; 
}
```

### 解构赋值默认值设置

1）数组解构赋值

```
let [a = 0] = [];
console.log(a);  // a: 0
```

2) 对象解构赋值

基础示例一：
```
let {a = 0} = {};
console.log(a);  // a: 0
```

基础示例二：
```
let {b: c = 1} = {};
console.log(c);  // c: 1
```

3）默认值覆盖

如果不需要默认值，则直接赋值即可

基础示例一：

```
let [a = 0] = [1];
console.log(a);  // a: 1
```

基础示例二：
```
let {a = 0} = {a: 1};
console.log(a);  // a: 1
```

4）undefined

在解构赋值中，类型undefined不算赋值，即等于无值，即使赋值为undefined也无法覆盖默认值。

```
let [a = 0] = [undefined];
console.log(a);  // a: 0
```

### 解构赋值作为函数传参

结构赋值可以赋默认值，当然也可以作为普通的参数进行函数传参

1) 基础示例

```
function fun([a = 1, b]){
    console.log(a);
    console.log(b);
}

fun([undefined, 2]);
// a: 1
// b: 2
```

2) 解构赋值空值

```
function fun([a, b]){
    console.log(a);
    console.log(b);
}

fun([, 2]);
// a: 1
// b: 2
```

3）解构赋值对象默认值

```
function fun({a = 1, b}){
    console.log(a);
    console.log(b);
}

fun({a: undefined, b: 2});
// a: 1
// b: 2
```

### 函数默认值

ES6中可以为函数参数设置默认值

```
function fun(a = 10){
    console.log(a);
}
fun();
```