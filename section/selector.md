##  为文档添加样式的三种方法
  1.  行内样式
  ```html
    <p style="font-size: 12px; font-weight: bold;"> 演示行内样式 </p>
  ```
  
  2.  嵌入样式
  ```html
    <head>
      <style type="text/css">
        h1 {font-size: 16px;}
        p {font-color: red;}
      </style>
    </head>
    <p>演示嵌入样式</p>
  ```
  
  3.  链接样式
  ```html
    <link href="style.css" rel="stylesheet" type="text/css" />
  ```