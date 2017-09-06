## ES6中的数据结构Set

Set可以理解为是**无重复值**的类数组结构，具有自动去重效果，是ES6中新增的**构造函数**

*注意 Set虽然类似于数组，但是键值对中键和值一样，这一点有所区别

基础示例：

```
let set = new Set();
```

### Set

构造带数据的Set实例

Set实例传参不能直接在构造函数中填充数据，Set接受一个数组作为参数

```
let set = new Set([1, 2, 3, 1]);
for(let val of set){
    console.log(val);
}
// 1 2 3
```
Set构造的实例自动去重

### Set属性和方法

Set构造函数提供一些基础的属性和方法

1）add()

add方法用于添加值，允许链式添加

```
let set = new Set();
set.add(1); // 添加 1
set.add(2).add(1).add(2);
for(let val of set){
    console.log(val);
}
// 1 2
```
添加重复值将自动去重

2）delete()

delete用于值的删除

```
let set = new Set();
set.add(1).add(2).add(3);
set.delete(1);
for(let val of set){
    console.log(val);
}
// 2 3
```

3)has()

has用于值检测

```
let set = new Set();
set.add(1).add(2).add(3);
set.has(1); // true
```

4)clear()

clear用于清除所有值

```
let set = new Set();
set.add(1).add(2).add(3);
set.clear();
```

3)size

size是属性，用于检测当前内部元素的个数

```
let set = new Set();
set.add(1).add(2).add(3);
set.size; // 3
```

### for-of 遍历 Set实例

1） keys

```
let set = new Set(['a', 'b', 'c']);
for(let key of set.keys()){
    console.log(key);
}
// a b c  键 = 值
```

2) values

```
let set = new Set(['a', 'b', 'c']);
for(let val of set.values()){
    console.log(val);
}
// a b c
```

3）entries

```
let set = new Set(['a', 'b', 'c']);
for(let [key, val] of set.entries()){
    console.log(key, val);
}
// a a
// b b
// c c
```
