# python爬虫笔记



## HTML网页结构

```html
<!DOCTYPE HTML>//inform browser that this is a html file
<html>//start
    <body>
        <h1>biggest title</h1>
        <p>this is a sentence</p>
    </body>
</html>//finish
```

所有元素都要放在两个html中间，按缩进区分元素



## 常见标签

### 标题

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
```

以此类推，格式如上，共有六级标题。但是我们可以通过css更改网页样式，一般来说也可以做h2字号和h1字号一样大

### 文本

```html
<p>yes<br>no</p>
//<br>表示强制换行，没有配对的闭合标签。当然也可以写很多<p></p>换行
<b></b>加粗
<i></i>斜体
<u></u>下划线
```

### 图片与跳转链接

```html
<img src="xxx(图片路径)",height="xx",width="xx">插入图片
<a href="xxx(url链接)"target="_self">xxx(xxx显示文本，点击xxx进入前面的链接)</a>
//注意，target用于指定链接页面的打开方式
//默认为_self，在当前页面直接跳转
//_blank，在新窗口里打开
```

### 容器

```html
<div style="xxx">
    xxx
</div>

<span style="xxx">
    xxx
</span>
```

两种容器形式，往里面放东西就行，区别是`div`为块级，一行只能放一个div元素

`span`为内联元素，不会独占一块，一行可以有多个span

### 列表

![image-20231202134832394](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202134832394.png)

![image-20231202134916434](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202134916434.png)



### 表格

![image-20231202135136907](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202135136907.png)



### class属性

![image-20231202135239219](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202135239219.png)





## beautiful soup提取数据

![image-20231202144531359](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202144531359.png)

![image-20231202145252861](C:\Users\Sandiverse\AppData\Roaming\Typora\typora-user-images\image-20231202145252861.png)