# jade 模板引擎
* 安装
```
npm install jade -g
```

## 使用
* 直接使用
```
jade index.jade
```
可生成压缩过的html文件，
```
jade -P index.jade
```
则生成可读的，正常的html文件
```
jade -P -w index.jade
```
对jade文件的修改实时更改html文件

## 语法
```
doctype 
html
<!--[IF IE 8]--><html class='ie8'><--[endif]-->
<!--[IF IE 9]--><html class='ie9'><--[endif]-->
<!--[IF IE]--><!--><html><!--<![endif]-->
  head
    meta(charset = 'utf-8')
    title
  body
    h1#id.class1.class2(class = class3, class = class4) Hello world
    div 
    p
    ul
    strong
    p 
      | 1.aa
      | 2.33
      | 3.45
    p.
      1.aa
      2.33<span>123</span>
      3.45<strong></strong>    
     p.
      | 1.aa
      | 2.33
      span 123
      | 3.45
      strong 5324
   // 注释
   //- 非缓冲注释
    
```
