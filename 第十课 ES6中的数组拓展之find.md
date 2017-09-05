## ES6中的数组拓展之find

find用于查询操作，可以匹配查询数组中的值，并提供了一个回调函数用于值的筛选。

### find

1）参数组成

目标数组.find(内部的值，当前值的索引，当前目标数组)

2）find查询示例:

```
let arr = [1, 2, 3, 4, 5, 6];
arr.find(function(val, key, arr){
    if(val > 3){
        console.log('值：' + val + ',' + '索引：' + key);
    }
    // 值：4, 索引： 3
    // 值：5, 索引： 4
    // 值：6, 索引： 5        
})
```

### findIndex

1）参数组成

目标数组.findIndex(内部的值，当前值的索引，当前目标数组)

2）findIndex查询示例:

```
let arr = [1, 2, 3, 4, 5, 6];
arr.findIndex(function(val, key, arr){
    if(val > 3){
        console.log('值：' + val + ',' + '索引：' + key);
    }
    // 值：4, 索引： 3
    // 值：5, 索引： 4
    // 值：6, 索引： 5        
})
```

### find与findIndex区别

findIndex与find非常相似，甚至基本参数都一致。
如果为findIndex与find设置返回值，返回值的参数为当前符合条件的第一个参数值。

**find返回当前符合条件的val值**
**findIndex返回当前符合条件的布尔值（符合条件返回1，否则-1）**

1）find返回值示例

```
let arr = [1];
console.log(arr.find(function(val, key, arr){
    if(val > 3){
        return val
    }  
})); // undefined 未查询到
```

2）find返回值示例

```
let arr = [1];
console.log(arr.find(function(val, key, arr){
    if(val > 3){
        return val
    }  
})); // 0
```


