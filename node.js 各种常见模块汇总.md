# node.js 各种常见模块汇总

### 1.  http

### 2.  fs  主要操作文件和文件夹

```js
//c(creat) u(upload) r(read) d(del)创建,上传,读取,删除
//文件操作
//文件夹操作
//流操作

```



### 3.  path

```js
let fullpath = path.join(__dirname,'staic','a.html')//获取绝对路径
```



### 4.  url

```js
// 使用url.parse获取url中的get参数  false:就是以字符串的方式返回,true就是以对象的形式返回

let urlObj = url.parse(request.url,true);
let queryParamsObj = urlObj.query;//获取请求路径对象中的query对象(包含了url中的get参数)
```



### 5.  multparty

### mine    用于获取文件扩展名

```js

let nimeName = mine.getType(filepath)//根据后缀名来获取该文件类型,并返回
response.setHeader('Content-Type',deps);//主要是方便在此
```

### 6.  express 对http模块的封装

```js
const express = require("express");
const app = express();//创建服务器对象
app.use(express.static('web'));//暴露web文件夹 让外部访问
app.listen(8881,()=>{});//开启服务器
app.get('/foodInfo',(req,res)=>{
    //这里的
    res.send({
        name:'xxx',
        color:"yyy"
    })
});
app.post('/foodAdd',(req,res)=>{
    res.send({});
})
```

### 7.  nodemailer

```js
"use strict";
const nodemailer = require("nodemailer");

//1.创建邮件的对象
  let transporter = nodemailer.createTransport({
    host: "smtp.qq.com",//发送方的邮箱 qq lib/well-know/servers.json
    port: 465,//端口号
    secure: true, // true for 465, false for other ports
    auth: {
      user: "624981658@qq.com", // generated ethereal user 发送方的邮箱地址
      pass: "piqbdxmyphdqbdcj" // generated ethereal password    smtp验证码
    }
  });

  // 2.邮件信息
  let mailobj = {
    from: '"Fred Foo 👻" <624981658@qq.com>', // sender address
    to: "624981658@qq.com,892383995@qq.com, 939172425@qq.com", // list of receivers
    subject: "Hello ✔", // Subject line
    text: "Hello world?", // plain text body
    // html: "<b>Hello world?</b>" // html body  text文本和网页html 只能选一个
  };
//3.发送邮件
  transporter.sendMail(mailobj,(err,data)=>{
      console.log(err);
      console.log(data);
        
      
  });
// setInterval(() => {
//     transporter.sendMail(mailobj);  //邮箱轰炸 慎用
// }, 1000);



//作业
xxx.sender('mail',msg)
```

### 8.  body-parser  用来处理post请求,只能处理文本数据

```js
const bodyParser = require('body-parser');
const app = express();
//2.设置body-parser的数据解析格式
// parser application/x-www-form-urlencoded
app.use({bodyParser.urlencoded({extended:false})});
//通过request.body获取 浏览器post过来的[文本数据!!!]
```

















