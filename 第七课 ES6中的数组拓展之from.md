## ES6中的数组拓展之from

### from

from用于将类似于数组的**对象**转换成数组格式

1) 数组属性组成如下：

    a）键/值对

    b）length属性

2) 转换示例;

```
let obj = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    'length': 3
}

let arr = Array.from(obj);
console.log(arr); // ['a', 'b', 'c']
```

3) 空数组定义

let obj = {
    'length': 3
}

let arr = Array.from(obj);
console.log(arr); // [undefined, undefined, undefined]

4) 返回值

from接收两个参数，第二个参数为遍历的返回值，接受处理后返回给最终的数组

```
let obj = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    'length': 3
}

let arr = Array.from(obj, (val) => val + '&more');
console.log(arr); // ['a&more', 'b&more', 'c&more']
```