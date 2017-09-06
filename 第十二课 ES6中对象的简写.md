## ES6中对象的简写

ES6中可以用简写的方式来拓展对象属性

1）获取定义好的变量作为参数

```
let key = 'val';
let obj = {key}; // 左边的操作等于  {key: 'val'}
```

2）等值简写

```
function fun(val){
    return {val}
}
```
以上示例等同于下：

```
function fun(val){
    return {val: val}
}
```

3）函数参数简写

```
let obj = {
    fun(){
        console.log('test');
    }
}
```
以上示例等同于下：

```
let obj = {
    fun: function(){
        console.log('test');
    }
}
```