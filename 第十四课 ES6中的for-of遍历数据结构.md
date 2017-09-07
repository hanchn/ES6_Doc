## ES6中给的for-of遍历数据结构

ES6中新增了一些新的数据结构，早期的一些遍历数据结构的方法已经不再适用于新的数据结构，所以就产生了新的数据遍历方式for-of。

for-of可以用于遍历数组、Set及Map（后期内容会介绍到）, *注意：for-of服务与类数组对象

基础示例:

```
let arr = ['a', 'b', 'c'];
for(let i of arr){
    console.log(i);
}
```


### 早期数据遍历方式

1） for循环

for循环遍历数组

```
let arr = ['a', 'b', 'c'];
for(let i = 0; i < arr.length; i ++){
    console.log(i);
}
```

2）for in 遍历对象

```
let arr = ['a', 'b', 'c'];
for(let i in obj){
    console.log('key: ' + i + ' val: ' + obj[i]);
}
```

3) forEach 遍历数组

数组遍历

```
let arr = ['a', 'b', 'c'];    

arr.forEach(function(val, key, arr){
    console.log('val: ' + val + ' key: ' + key + ' arr: ' + arr);
})
```

4）ES6之前遍历方式的缺陷

    a）for循环只能遍历数组结构，其他数据结构及ES6中新增的数据结构爱莫能助

    b）for-in遍历方式只能遍历出键值，无法获得键名（新增数据结构键名复杂：允许为对象、字符、数字等）

    c）forEach缺陷极大，无法中断遍历和获取更新后的数组，遍历数据结果容易异常


### for-of拓展属性 entries()、keys()和values()

for-of中拓展了辅助属性方法 entries()、keys()和values()，用于辅助获取相应的数据键/值。


1）for-of keys()

```
let arr = ['a', 'b', 'c']; 
for(let key of arr.keys()){
    console.log(key);
}
```

2）for-of values()

注意* 目前浏览器解析values()异常，建议在babel尝试 （目前时间节点为：17年/09月/06日）

```
let arr = ['a', 'b', 'c']; 
for(let val of arr.values()){
    console.log(val);
}
```

3) for-of entries()

```
let arr = ['a', 'b', 'c']; 
for(let [key, val] of arr.entries()){  // key在前  val在后 和 for in 不一致
    console.log('val: ' + val + ' key: ' + key);
}
```

