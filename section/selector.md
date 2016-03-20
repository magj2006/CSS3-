##  一、  为文档添加样式的三种方法
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

##  二、  CSS命名规则
![alt text](../pic/named_rule.JPG "css named rule")

CSS 命名规则有两部分：即选择符和声明。 声明又由两部分组成，即属性和值。
声明包含在一对{}中。

##  三、  上下文选择符
  严格来讲，叫后代组合式选择符，就是一组以空格分隔的标签名。用于选择作为指定祖先元素的后代的标签。  
  
  **格式：**  标签1 标签2 {声明}   
    其中，标签2就是我们想要选择的目标，而且只有标签1是其祖先元素被选中的情况下。<br>
    `article p {font-size: 12px;}`  
    这个例子中的上下文选择符表明，只有是article的后代的p元素才会应用后面的样式。

##  四、  特殊的上下文选择符
  1.  子选择符 >
    > 标签1 > 标签2 标签2必须是标签1的子元素   
      `section > h2 {font-size: 12px;}`
  2.  紧邻同胞选择符 +
    > 标签1 + 标签2 标签2必须紧跟在标签1的后面  
      `h2 + p {font-size: 12px;}`
  3.  一般同胞选择符 ~
    > 标签1 ~ 标签2 标签2必须跟（不一定紧跟）在其同胞标签1后面  
      `h2 ~ a {color: red;}`
  4.  通用选择符 *
    
##  五、  ID和类选择符
  * \#id {样式声明}
  * .class_name {样式声明}
  > 两者区别：ID可以用于**页内**导航链接中。 
    ```html
    <a href="#foo">Foo</a>
    <a href="#">Back To Top </a>
    ```
    ID 用于页面中唯一的标识一个元素   
    类 用于标识一组具有相同特征的元素
    
##  六、  属性选择符
  > 基于HTML标签的属性选择元素
  
  * 标签名[属性名]
    > `img[title] {border: 2px solid bule}`
  * 标签名[属性名="属性值"]
    > `img[title="red flower"] {border: 4px solid green}`
    
##  七、  伪类
  - UI伪类
      > 基于特定HTML元素的状态应用样式
      
      1.  链接伪类
          ```
          a:link {color: black;}
          a:visited {color: blue;}
          a:hover {text-decoration: none;}
          a:active {color: red;}
          ```
      2.  :focus 伪类   
          eg: `input:focus {border: 1px solid blue;}`
      3.  :target 伪类  
          `<a href="#foo"> Foo </a>`  
          `#foo:target {blackcolor: red;}`
          
  - 结构化伪类  
      1.  :first-child :last-child
      2.  :nth-child
     
##  八、  伪元素
  1.  ::first-letter
    > `p::first-letter {font-size: 300%;}`
  2.  ::first-line
  3.  ::before  ::after
    > `<p class="age"> 25 </p>`  
      `p.age::before {content: "Age: ";}`  
      `p.age::after {content: " years.";}`
    
##  九、  继承

##  十、  层叠
  > 层叠是**CSS**中的核心机制
  
  ####  来源样式的顺序：
  * 浏览器默认样式表
  * 用户样式表
  * 作者链接样式表
  * 作者嵌入样式表
  * 作者行内样式表
  
  ####  层叠规则：
  - 规则一：ID选择符 > 类选择符 > 签名选择符
  - 规则二：行内样式 > 嵌入样式 > 链接样式
  > 规则一 > 规则二
  - 规则三：设定的样式 > 继承的样式
  
  ####  计算特指值
  I-C-E