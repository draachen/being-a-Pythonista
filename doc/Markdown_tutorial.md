## Markdown教程  

### Markdown常见操作

-   标题

    文本前边加\# 或者在下边加==或-  
    *注： # 后要跟空格，以便正确显示* 

-   粗体

    文本两端加**或__

-   分隔线

    使用3个以上的星号，减号，底线  


-   列表格式

    文本前加-，或者1.  

    -   python  
    -   java
        1.  python
        2.  java  


-   超链接

    This is [an example](http://example.com/ "Title") inline link.    

-   插入图片

    ![描述]（www.xxx.com.jpg?raw=true）  

-   引用

    文本前加>  

    > this is a program.  


-   代码引用

    或者使用1个制表符，或4个空格  

    this is a program.   

​	若多行，则文本两端各加三个单引号'''  

-   列表

| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |
​	注： MarkdownPad2未正确显示*

### Github Flavored Markdown

-   删除线：使用两个~: ~~I Hate PYTHON~~


-   任务复选框: 使用- [x] 和- [ ] 来  

- [ ] This is a complete item
- [x] This is a todo item  

-   @某人或Issue  

    使用@或#来实现，例如@draachen, # 151  

-   添加emoji表情

    :sparkles:  :camel:  :boom:  :dragon:  
    *注： MarkdownPad2未正确显示*

-   HTML标签

    HTML区块标签间的Markdown格式语法不会被处理    

    <table>

        <tr>
            <td>Foo</td>
        </tr>

    </table>  

### Markdown Editor: Typora

Windows下可以使用MarkdownPad2，Typora等编辑器 
Typora相对于MarkdownPad 2最大的优点：

- 支持Latex数学公式的实时预览 ，例如 $h_\theta (x) = \theta_0 + \theta_1 x $ 

#### Typora常见命令

-   Ctrl + T : 新建表格

| Hello                       | World                        |
| --------------------------- | ---------------------------- |
| This is the first statement | this is the second statement |
| so cool                     | so good                      |

-   $$ + Enter: 进入Latex公式编辑模式

$$
y = 3x + 2x^2 +5
$$
-   使用[TOC]命令: 自动根据层级生成目录

[TOC]

-   插入图片：

    除原先的![]() 命令外，还支持直接拖入。

    其中MacOS版本支持利用iPic插件直接将图片上传图床

-   使用$符号包裹Tex命令

  ​$lim_{x \to \infty} \ exp(-x) = 0$

  ​下标：$H_2 O$ 

  ​上标：$y^2 = 4$

-   插入表情使用--> :表情: :happy::sad::e-mail:


-   下划线: this is underline</u>

-   删除线:  ~~一键上传本地图片至图床（仅支持MacOS）~~

-   代码：

    使用`包裹的内容，以代码样式显示

    `print("Hello World")`

    输入~~~+Enter或者```+Enter：输入代码块，并且可以选择代码语言

~~~python
def test():
    pass
~~~

-   标注：使用[^]形式

    某些人用过了才知道[^注释]

    [^注释]: somebody that i used to know


### Changelog  

- 17.09.10 新增Typora编辑器
- 2017/8/28 23:42:36 新增Write on Github
- 2017/8/27 11:29:07 创建

参考资料：  

- [Markdown语法说明（简体中文版）](http://wowubuntu.com/markdown/)  
- [Writing on GitHub / Basic writing and formatting syntax ](https://help.github.com/articles/basic-writing-and-formatting-syntax/)  
- [安利一下Typora：极致简洁的markdown编辑器](http://www.jianshu.com/p/5256ecc06eec)
- [Typora For Markdown 语法](http://www.jianshu.com/p/092de536d948)