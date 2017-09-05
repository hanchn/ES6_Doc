## ES6中的数组拓展之fill

fill用于数组填充

### 参数设置

数组.fill(填充值， 填充的起始位置， 填充的结束位置)

### 基础示例

1) 空填充

填充类似于覆盖填充，如果当前数组无值，则数组仍然为空

```
let arr = [];
arr.fill(10);
console.log(arr); // []
```

2）覆盖填充

```
let arr = [1, 2, 3];
arr.fill(10);
console.log(arr); // [10, 10, 10]
```

3）按位填充

```
let arr = [1, 2, 3];
arr.fill(10, 1, 2);
console.log(arr); // [1, 10, 3]
```