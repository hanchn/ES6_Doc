## ES6中的let变量声明

let用于声明变量，作用与var类似，但是let受作用于{}（花括号作用域，而非函数作用域）

示例：

```
let val = 10;
```


### 花括号作用域

ES6中拓展了花括号作用域即{}，示例如下：

```
{

}
```

使用let声明的变量只作用于当前作用域之内（花括号作用域）

### let声明变量的特性

1）作用于花括号作用域

let声明的变量只能作用域当前作用域之内，如果在作用域之外使用将会报未定义的错误。

```
{
    let a = 10;
}
console.log(a);
// 报错： a is not defined
```

2）单作用域只能声明一次

let声明变量在单作用域只能声明一次，无法多次声明。

```
{
    let a = 10;
    let a = 'test';
}
// 报错： 'a' has already been declared
```

3）不存在变量提升

let声明的变量不存在变量提升，在声明之前无法使用。

```
console.log(a);
let a = 10;
```

### 经典示例

示例需求：当前网页中有五个按钮，点击按钮输出当前按钮ID。

HTML示例:

```
<input type="button">
```

ES5中的解决办法：

```
var btns = document.querySelectorAll('input');
for(var i = 0; i < btns.length; i ++){
    (function(i){
        btns[i].onclick = function(){
            alert(i);
        }
    })(i)
}
```

ES6中let的用法：

let作用域{}花括号作用域，当前{}作用域中的i并不会自增

```
var btns = document.querySelectorAll('input');
for(let i = 0; i < btns.length; i ++){
    btns[i].onclick = function(){
        alert(i);
    }
}
```