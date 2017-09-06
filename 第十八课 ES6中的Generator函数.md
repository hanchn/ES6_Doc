## ES6中的Generator函数

Generator函数ES6提供的另一种异步编程的解决方案，Generator与Promise不一样不是构造函数！

基本示例：

Generator写法和普通函数一样，唯一区别就是在函数名前添加*号

```
function *fun(){

}
```

Generator 函数无法执行，需要在执行后配合next函数获取内部yield的值

### Generator结构组成

1） 基本结构

与普通方法类似，方法名带有*号前缀

```
function *fun(){
    return 'Hello World !';
}
```

2）无法直接执行

执行后需要配合next函数，执行内部操作

基本示例：

```
function *fun(){
    return 'Hello World !';
}

let getVal = fun().next();
console.log(getVal);

// {value: "Hello World !", done: true}
```

3) yield

Generator为多操作函数，可以不止一个返回内容，需要配合yield操作符使用

```
function *fun(){
    yield 'Hello World one!';
    yield 'Hello World two!';
    yield 'Hello World three!';
    return 'Hello World four!'
 }
 
 let doFun  = fun();
 let val01 = doFun.next();
 let val02 = doFun.next();
 let val03 = doFun.next();
 let val04 = doFun.next();
 let val05 = doFun.next();
 console.log(val01);  // {value: "Hello World one!", done: false}
 console.log(val02);  // {value: "Hello World two!", done: false}
 console.log(val03);  // {value: "Hello World three!", done: false}
 console.log(val04);  // {value: "Hello World four!", done: false}
 console.log(val05);  // {value: undefined, done: false}
```

yield类似于返回值，会将yield后的内容以对象的形式返回

4) 返回对象解析

返回对象包含一个基本返回值，以及返回所有的yield分支是否已经全部执行完成（完成则true否则false）。

```
{value: "Hello World one!", done: false}
```

5) 函数运算

```
let plus = function(a, b){
     return (a + b);
}

let minus = function(a, b){
    return (a - b);
}

function *fun(a, b){
    yield plus(a, b);
    yield minus(a, b);
    return 'Calculations';
 }
 
 let doFun  = fun(1, 2);
 let val01 = doFun.next();
 let val02 = doFun.next();
 let val03 = doFun.next();
 console.log(val01); // {value: 3, done: false}
 console.log(val02); // {value: -1, done: false}
 console.log(val03); // {value: 'Calculations', done: true}
```

### yield运算

1）yield参与运算必须要加（）运算符

空yield参与运算返回值为undefined

```
function *fun(){
    console.log('Hello ' + (yield)); // Hello undefined
    console.log('Hi ' + (yield)); // Hi undefined
    return 'Over'; 
}

let funs = fun();
funs.next();
funs.next();
funs.next();
```

2) 数值运算


```
function *fun(){
    console.log(1 + (yield)); // Nan
    console.log(0 + (yield)); // Nan
    return 'Over'; 
}

let funs = fun();
funs.next();
funs.next();
funs.next();
```

3) 带参yield

yield中如果携带参数，则算作上一个yield的返回值。

```
function* foo(x) {
  var y = 2 * (yield (x + 1));
  var z = yield (y / 3);
  return (x + y + z);
}

var a = foo(5);
a.next() // Object{value:6, done:false}
a.next() // Object{value:NaN, done:false}
a.next() // Object{value:NaN, done:true}

var b = foo(5);
b.next() // { value:6, done:false }
b.next(12) // { value:8, done:false }
b.next(13) // { value:42, done:true }
```

### 遍历Generator

1）for-of

for-of可以代替next，获取每个yield分支中的value值，如果遇到done的状态为true则主动放弃遍历

```
function *fun(){
    yield 'a';
    yield 'b';
    yield 'c';
    yield 'd';
    return;
}

for(let val of fun()){
    console.log(val);
}  // a b c d
```

2) spread操作符

spread也具有遍历Generator函数并且组合成数组的能力

```
function *fun(){
    yield 'a';
    yield 'b';
    yield 'c';
    yield 'd';
    return;
}

let arr = [...fun()]; // ['a', 'b', 'c', 'd']
```

3) from

Array.form()函数可以将直接Generator函数转换成数组

```
function *fun(){
    yield 'a';
    yield 'b';
    yield 'c';
    yield 'd';
    return;
}

let arr = Array.from(fun());  // ['a', 'b', 'c', 'd']
```