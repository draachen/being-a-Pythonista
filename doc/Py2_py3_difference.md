## Py2和Py3的区别

### 程序调用

- 方法1
	- py -2 hello.py
	- py -3 hello.py
- 方法2: 代码中加说明后在CLI中使用py hello.py运行
	- \#! python2
	- \# coding: utf-8
	- \#! python3

### pip使用  

- py -2 -m pip install xxx
- py -3 -m pip install xxx

### 主要区别  

- print  
    - py2中print 后直接跟变量  
    - py3中print后需跟括号，且其中括号中的空格不会作为空格字符输出  
      - print后跟括号在Py2中可以运行，**但是若跟多个变量，则括号也会被输出**  
      - 在Py2中，print后的变量间加逗号，则变量们在同一行显示  
      - 在Py3中，print后括号结束则换行  
- raw_input()及input()函数  
    - py2中raw_input()用于接收字符串，input()用于接收数字  
    - Py3中input()函数输出字符变量，raw\_input函数在Py3中不适用  

- 除法  
    - Py2地板除法;  
    - Py3中默认除法保留小数点后位数，Py3中使用地板除法，应为10//3

- 编码  
    - Py2中默认不能直接输入中文  
    - Py3采用Unicode编码，支持中文输入  
    - Py3中采用Unicode编码，会造成内存的损耗，故可以在读取源代码时，让它按照UTF-8编码读取:

        > \# -\*- coding: utf-8 -*-

### Changelog  

- 2017/8/27 11:30:31 init

参考资料  

- [廖雪峰Python3教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)  

