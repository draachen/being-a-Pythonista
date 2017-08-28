### Tkinter库教程  

Py3.X后tkinter模块名称变更：  

    > Tkinter → tkinter  
    > tkMessageBox → tkinter.messagebox  
    > tkColorChooser → tkinter.colorchooser  
    > tkFileDialog → tkinter.filedialog  
    > tkCommonDialog → tkinter.commondialog  
    > tkSimpleDialog → tkinter.simpledialog  
    > tkFont → tkinter.font  
    > Tkdnd → tkinter.dnd  
    > ScrolledText → tkinter.scrolledtext  
    > Tix → tkinter.tix  
    > ttk → tkinter.ttk  

使用tkinter创建GUI应用程序的步骤  

    - 导入tkinter模块.  
    - 创建GUI应用程序的主窗口  
    - 添加上述部件之一或更多的GUI应用程序  
    - 进入主事件循环的由用户触发每个事件响应  

创建新窗口

    >import tkinter  
    >top = tkinter.Tk()  
    >top.mainloop()  

tkinter的部件  

- Button： 显示文字或图像，按下按钮，可以自动调用附加的函数或方法  
- Canvas：是长方形的面积，图画或其他复杂的布局  
- Checkbutton: 用于显示切换按钮的用户多项选择  
- Entry: 用于接受用户Entry小窗口部件单行文本字符串  
- Frame: Used as container widget to organize other widgets  
- Label: 常见选项： text, textvariable, etc  
- Listbox： 用于显示一个项目列表  
- Menubutton： 一个菜单按钮就是一个下拉菜单  	
- Menu： 创建菜单，弹出式，顶层，和下拉式  
- Message：类似Label  
- tkinter.messagebox： used to display message boxes in your applications.
- Scrollbar： 实现滚动条  
- Text： 编辑文本格式  
- ...

tkinter标准属性  

- Dimensions： 常见的长度选项：width, height, borderwidth, etc
- Colors： 常见的颜色选项：foreground, background, etc  
- Fonts： tuple字体，e.g.（"Times", "24", "bold italic"）  
- ...

tkinter几何管理  

- pack()： widget.pack(pack_options)  
- gird()： 组织在父部件中的表状结构中的部件
- place()： 组织在父部件的某一个特定的位置  

### Changelog  

- 2017/8/27 14:58:06 初步整理Tkinter

参考资料  

- [易百Tk教程](http://www.yiibai.com/python)