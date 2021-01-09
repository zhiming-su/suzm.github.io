---
layout: post

title: "js callback 函数方法的使用"

categories: JavaScript

tags: JS callback

author: Szm
---

* content
{:toc}

学习js call back 方法可以在使用异步方法后执行对应的方法



## js callback 示例

```javascript
let fucRet = myApi.excuteCloudFunction("test", "hello", null, (name) => {

​      console.log(name + "child")

​    })
```

异步方法

```javascript
const { cloud } = getApp();
const { function: fc } = cloud;
//调用云函数
/*
serverName:云函数名称
hander:云函数方法名
data:云函数参数json格式
mySetData:回调函数设置setData
*/
 function excuteCloudFunction(servierName, handler, data, mySetData) {

  fc.invoke(servierName, data, handler).then(res => {
    console.log(res + "father")
    mySetData(res)
    //return res;
  })

}
```







