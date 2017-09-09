## Jupyter Notebook  

> Jupyter 是 **Ju**lia、**Pyt**hon 以及 **R** 语言的组合，字形相近于木星（Jupiter），现在支持的语言也远超这三种。

### Jupyter in Windows

Jupyter notebook 在windows下基本无法使用，欲使用jupyter只能通过安装anaconda来实现。

### Why Jupyter?

- 为什么有了Markdown还需要Jupyter Notebook:  
    - 缘由：准备整理Andrea Ng Machine Learning纸质笔记的时候，发现使用Markdown来表示数学符号，简直是impossible。

- Jupyter相比于Markdown优势：  
    - Jupyter是集成环境：你既可以通过写文字笔记，又能在笔记中嵌入代码及其运行结果，还可以直接在环境中进行命令行交互  
    - 支持超过 40 种数据科学相关的编程语言，例如 R/Python/Scala 等  
    - 支持 MathJax 渲染（也就是说 LaTex 公式可以渲染出来）  

### 安装及运行  

安装：建议通过安装Anaconda来安装Jupyter Notebook

运行：安装成功后在CLI下运行jupyter notebook

### 常用命令  

- Enter键:
    - Enter: 转入编辑模式
    - Shift-Enter：运行本单元，选中下个单元
    - Ctrl-Enter：运行本单元
    - Alt-Enter：运行本单元，在其下插入新单元
- 命令模式下：
    - Y：单元转入代码
    - M：单元转入markdown
    - R：单元转入raw
    - 1:设定1级标题
- 选中单元
    - Up/Down键，多选按Shift
- 插入新单元：
    - A：在上方插入新单元
    - B：在下方插入新单元
- 操作单元：
    - X：剪切选中的单元
    - C：复制选镇南关的单元
    - V：粘贴到下方单元
    - Shift-V：粘贴到上方单元
    - Z：恢复删除的最后一个单元
    - DD：删除选中的单元
    - Shift-M：合并选中的单元
    - Crtl-S：文件存盘
    - S：文件存盘
- H：显示帮助
- F：寻找及替代  

### 进阶功能  

- 数学公式编辑  
    - $$expression$$ 会使expression强制独立一行，而$erpression$不会导致换行  
    - z = x/y: $$ z = \frac{x}{y} $$  
- 幻灯片制作  
- 魔术关键字  

### Changelog  

- 170909 init create  

参考资料  

- [A Primer on Using LaTeX in Jupyter Notebooks](http://data-blog.udacity.com/posts/2016/10/latex-primer/)  