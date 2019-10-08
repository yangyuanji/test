# 这是一个express后台

## 1.配置express

# <img src="images/13_03.png"  />

```
var express=require("express");
var app=express();  //创建http服务器
var bodyParser = require("body-parser")
app.engine('html', require('express-art-template'));//引用模板引擎
var router=require("./router")
app.use(bodyParser.urlencoded({ extended: false }))  //设置中间件，一定比路由先建立
app.use(bodyParser.json())
```

## 2.设置路由

路由要require（./router.js）文件，代码xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

# 这是视图层

## 1.核心代码

```

<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
  <meta name="description" content="">
  <meta name="author" content="">
  <link rel="icon" href="../../favicon.ico">

  <title>Dashboard Template for Bootstrap</title>

  <!-- Bootstrap core CSS -->
  <link href="/node_modules/bootstrap/dist/css/bootstrap.css" rel="stylesheet">


  <!-- Custom styles for this template -->
  <link href="/public/css/dashboard.css" rel="stylesheet">



  <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
  <!--[if lt IE 9]>
  <!--<script src="/node_modules/html5shiv/dist/html5shiv.js"></script>
  <script src="/node_modules/respond/main.js"></script>-->

</head>

<body>

<nav class="navbar navbar-inverse navbar-fixed-top">
  <div class="container-fluid">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
      <a class="navbar-brand" href="#">Project name</a>
    </div>
    <div id="navbar" class="navbar-collapse collapse">
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#">Dashboard</a></li>
        <li><a href="#">Settings</a></li>
        <li><a href="#">Profile</a></li>
        <li><a href="#">Help</a></li>
      </ul>
      <form class="navbar-form navbar-right">
        <input type="text" class="form-control" placeholder="Search...">
      </form>
    </div>
  </div>
</nav>

<div class="container-fluid">
  <div class="row">
    <div class="col-sm-3 col-md-2 sidebar">
      <ul class="nav nav-sidebar">
        <li class="active"><a href="#">Overview <span class="sr-only">(current)</span></a></li>
        <li><a href="#">Reports</a></li>
        <li><a href="#">Analytics</a></li>
        <li><a href="#">Export</a></li>
      </ul>
      <ul class="nav nav-sidebar">
        <li><a href="">Nav item</a></li>
        <li><a href="">Nav item again</a></li>
        <li><a href="">One more nav</a></li>
        <li><a href="">Another nav item</a></li>
        <li><a href="">More navigation</a></li>
      </ul>
      <ul class="nav nav-sidebar">
        <li><a href="">Nav item again</a></li>
        <li><a href="">One more nav</a></li>
        <li><a href="">Another nav item</a></li>
      </ul>
    </div>
    <div class="col-sm-9 col-sm-offset-3 col-md-10 col-md-offset-2 main">
      <h1 class="page-header">Dashboard</h1>

      <div class="row placeholders">

       {{each fruit}}
        <div class="col-xs-6 col-sm-3 placeholder">
          <img src="data:image/gif;base64,R0lGODlhAQABAIAAAHd3dwAAACH5BAAAAAAALAAAAAABAAEAAAICRAEAOw==" width="200" height="200" class="img-responsive" alt="Generic placeholder thumbnail">
          <h4>{{$value}}</h4>
          <span class="text-muted">Something else</span>
        </div>
        {{/each}}
      </div>

      <h2 class="sub-header">Section title</h2>
      <a href="/student/new" class="btn btn-success">添加学生</a>
      <div class="table-responsive">
        <table class="table table-striped">
          <thead>
          <tr>
            <th>#</th>
            <th>姓名</th>
            <th>性别</th>
            <th>年龄</th>
            <th>爱好</th>
            <th>操作</th>
          </tr>
          </thead>
          <tbody>
          {{each students}}
          <tr>
            <td>{{$value.id}}</td>
            <td>{{$value.name}}</td>
            <td>{{$value.gender}}</td>
            <td>{{$value.age}}</td>
            <td>{{$value.hobbies}}</td>
            <td>
              <a href="/students/edit?id={{$value.id}}">编辑</a>
              <a href="/students/delete?id={{$value.id}}">删除</a>
            </td>
          </tr>
          {{/each}}


          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>


</body>
</html>

```

## 2.最终效果

<img src="./images/1.png"  />