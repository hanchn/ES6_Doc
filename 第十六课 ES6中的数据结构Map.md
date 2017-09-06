## ES6中的数据结构Map

Map的键名可以是任意类型，类似于JSON对象，但是键值对以逗号分割，并允许接受数组作为基本参数。

*注意 Map并非JSON对象

基础示例:

```
let map = new Map();

```

### Map中的属性方法

Map中的属性和方法和Set非常类似

1） 为Map示例添加内容

```
let map = new Map(['name', 'test']);
```

2) set()

添加一条数据

```
let map = new Map();
map.set('name', 'test');
```

3）get()

获取数据

```
let map = new Map(['name', 'test']);
map.get('name'); // test
```

4）has()

存在查询

```
let map = new Map(['name', 'test']);
map.has('name'); // true
```

5) delete()

删除指定数据

```
let map = new Map(['name', 'test']);
map.delete('name'); // true
```

6）clear()

清除所有数据

```
let map = new Map(['name', 'test']);
map.clear(); // true
```

7）size

检测数据量

```
let map = new Map(['name', 'test']);
map.size; // 1
```

### 遍历Map数据结构

1）for-of keys

```
let map = new Map([
    ['uName', 'admin'],
    ['uPwd', '123'],
    ['uGender', 'men']
]);

for(let key of map.keys()){
    console.log(key);
}
// "uName"
// "uPwd"
// "uGender"
```

2) for-of values

```
let map = new Map([
    ['uName', 'admin'],
    ['uPwd', '123'],
    ['uGender', 'men']
]);

for(let val of map.values()){
    console.log(val);
}
// "admin"
// "123"
// "men"
```

3) for-of entires

```
let map = new Map([
    ['uName', 'admin'],
    ['uPwd', '123'],
    ['uGender', 'men']
]);

for(let [key, val] of map.entries()){
    console.log('key: ' + key + ' val: ' + val);
}
// "key: uName val: admin"
// "key: uPwd val: 123"
// "key: uGender val: men"
```







