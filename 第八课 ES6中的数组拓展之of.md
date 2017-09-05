## ES6中的数组拓展之of

Array中的of用于创建数组，用途类似于Array构造函数，但是弥补了Array构造函数的部分缺陷。

### Array构造函数的缺陷

Array构造函数在构造对象时，因为参数的传递不一致，得到的结果区别差异也较大

1） 创建空数组

```
var arr = new Array();
console.log(arr); // arr = []
```

2) 创建多值数组

```
var arr = new Array(3); 
console.log(arr); // arr = [ , ,]
```

3) 创建多值数组，并赋值

```
var arr = new Array(1, 2, 3); 
console.log(arr); // arr = [ 1, 2, 3]
```

### of创建数组对象

Array构造函数创建数组对象的时候存在二义性（如上示例），of方法则弥补了这一缺陷

1）创建空数组

```
var arr = Array.of();
console.log(arr); // []
```

2）创建单值数组

```
var arr = Array.of(3);
console.log(arr); // [3]
```

2）创建多值数组

```
var arr = Array.of(1, 2, 3);
console.log(arr); // [1, 2, 3]
```
