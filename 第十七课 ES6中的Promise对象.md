## ES6中的Promise对象

Promise是ES6中的一种异步解决方案，是一种构造函数

基本示例

resolve是指执行成功之后执行的方法

reject是指执行失败后执行的方法

```
let pro = new Promise(function(resolve, reject){
    if(成功){
        resolve
    } else {
        reject
    }
})


// 方法执行
pro().then(function(){
   // success
}, function(){
   // error
})
```

### Promise

1) 基础示例

题目：设置倒计时，5秒之后弹出弹窗

```
function timeOut(time){
    return new Promise(function(reslove, reject){
          setTimeout(reslove, time*1000);
    })
}

timeOut(5).then(function(){
    alert('5秒倒计时完成！');
})
```

2) Ajax封装

题目：进行一个 Ajax POST 请求封装

```
function post(url, reqData){
    return new Promise(function(reslove, reject){
        let xhr = new XMLHttpRequest();
        xhr.open('POSR', url, true);
        xhr.send(reqData);

        xhr.onreadystatechange = function(){
            if(xhr.readyState == 4 && xhr.status == 200){
                reslove(xhr.responseText)
            } else {
                reject('readyState = ' + xhr.readyState + ' status = ' + status);
            }
        }
    })
}

post('/', {}).then(function(data){
    console.log(data)
}).catch(function(err){
    console.log(err);
});
```

3） 懒加载异步封装

```
let lazyLoad = function(arr){
    new Promise(function(reslove, reject){
        let len = arr.length;
        let load = 0;
        const imgs = {};
        
        for(let i = 0; i < imgs.length; i++){
            var pic = new Image();
            pic.onload = function(){
                load ++;
                if(load == len){
                    reslove(imgs);
                }
            }
            pic.src = imgs[i];

            let name = imgs[i].split(".")[0];
            imgs[name] = pic;     
        }        
    })
}

lazyLoad(arr).then(function(imgs){
    console.log(imgs); 
})
```


