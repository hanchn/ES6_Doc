## ES6中的Class类定义

ES6之前JS并没有类的概念，ES6中拓展了Class类，使得JS更加严谨了。

ES6中的class类属于构造函数的语法糖，行业约定class类名和构造函数名首字母大写。


基础示例


```
class getVal{
    constructor(val){
        this.val = val;
    };

    toString(){
        return (this.val);
    };
}

let val = new getVal('Hello World !');
console.log(val.toString()); // Hello World !
```

### Class类定义

1) class中的构造器

如果没有给constroctor显示定义构造器，class会自动创建，构造器默认指向构造对象（class类）

```
class getVal{
    constructor(val){  //构造器
        this.val = val;
    };

    toString(){ // toString
        return (this.val);
    };
}

let val = new getVal('Hello World !');
console.log(val); // Hello World !
```

2) class中的toString

class中自带一个toString方法，如上示例所示

3）class调用

class是构造函数的语法糖，调用方式即和构造函数创建实例类似

借用上例：

```
let val = new getVal('Hello World !');
```

4）自定义方法

```
class getVal{
    constructor(val, name){  //构造器
        this.val = val;
        this.name = name;
    };

    toString(){ // toString
        return (this.val);
    };

    plus(){
        return (this.name + this.val);
    }
}

let val = new getVal('Hello World !', 'Jerry');
console.log(val.plus()); // Jerry Hello World !
```


### 类继承

1)基础示例:

```
class Per{
    constructor(){
        this.val = 'Hello World !';
    };

    toString(){
        return this.val;
    };
}

class Son extends Per{

};
```

2)调用方法

class中提供了一个super函数用于调用父类对象

```
class Per{
    constructor(){
        this.val = 'Hello World !';
    };

    toString(){
        return this.val;
    };
}


class Son extends Per{
    constructor(){
        super();
    };    

    toString(){
        return super.toString();
    }
};

let getVal = new Son();
console.log(getVal.toString()); // 'Hello World !'
```

