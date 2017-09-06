## ES6中的Module模块化

模块化的解决方案比较多，ES6中拓展了原生的模块啊方案

### NodeJS中的模块化方案

1) 模块化函数封装 exports

```
let fun = function(){

};

exports.fun = fun;
```

2）module.exports

```
module.exports = function(){
    alert(1);
}
```

module.exports = exports

NodeJS中的模块化写法如上，本文不再赘述

### ES6中的模块化

1）封装模块中的变量和方法

文件 test.js

```
export let val = 10;

export let fun = function(val){
    console.log(val);
}
```

2) 调用模块中的变量和方法

```
let {val , fun} = require('test');

fun(val); //执行模块方法 
```

