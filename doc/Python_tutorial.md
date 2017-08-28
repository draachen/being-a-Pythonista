## Python 教程

索引

- 脚本声明  
- 字符串  
- 列表  
- IO操作  

---

### 脚本声明  

脚本中定义使用Python3打开文件，编码格式采用utf-8

    #! python3  
    # -*- coding: utf-8 -*-

### 字符串  

字符串分解为字典  

    list.split('，')或者list.index('，')  

json中取值  

    import json  
    text = json.loads(rtn) # rtn 为 API 返回的数据  
    temperature = text['results'][0]['now']['temperature']  

格式化输出  

    print('i like %s' % a )  
    print('i like %{}'.format(a))  

### 列表  

将列表转换为字典  

    > a = ['a', 'b']  
    > data.update({list[0]:list[1]})  
    > data  
    {'a': 'b'}  

### IO操作  

读取数据  

    >fhand = open('weather_info.txt' ,'r', encoding='utf-8', errors='ignore')  
    要读取二进制文件，如图片，视频等，用'rb'模式打开文件  
    要读取非UTF-8编码的文本文件，需要给open()函数传入encoding参数  
    若遇到UnicodeDecodeError，有的情况下可以忽略,使用errors参数来忽略  
    >f = open('test.txt', 'r', encoding = 'gbk')  
    >f.read()  

写数据

    调用open()函数，传入标识符'w'或者'wb'表示写文本文件或二进制文件  
    > f = open('/Users/michael/gbk.txt', 'w')  
    > f.write('Hello World!')  
    >f.close()  #文件打开后记得关闭  

### Changelog  

- 2017/8/28 22:01:16 增补字符串，列表内容
- 2017/8/27 14:06:52 init  

参考资料  

- [廖雪峰Python3教程](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
