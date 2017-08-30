## Python 教程

索引

- 脚本声明  
- 字符串  
- 列表与元组  
- 字典与set  
- 函数  
- 高级特征  
- 函数式编程  
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

### 列表与元组  

list.append('test')  
test = list.pop(i) #i用于删除指定位置的元素的索引，默认空时则删除最后元素  

将列表转换为字典  

    > a = ['a', 'b']  
    > data.update({list[0]:list[1]})  
    > data  
    {'a': 'b'}  

元组不可变，指的是元素的指向不可变  
一个“可变”的元组  

    >t = ('a', 'b', ['A', 'B'])
    >t[2][0] = 'X'
    >t[2][1] = 'Y'
    >t
    ('a', 'b', ['X', 'Y'])

故，想要创建一个内容不变的元组，意味着元组中每一个元素都不能变

break：循环过程中直接退出循环  
continue：提前结束本轮循环，并直接开始下一轮循环  

### 字典与set  

dict['key'] = value  
判断key是否存在：dict['key'], key in dict, d.get('key', -1)  
删除key：dict.pop('key')  
dict的key必须是不可变对象，如字符串和整数；不能是list。  

set和dict类似，是key的集合，但不存储value。  
set中没有重复的key  
创建set需提供list作为输入集合  

    > s = set([1, 1, 2, 2, 3, 3])  
    > s  
    {1, 2, 3}  #重复元素自动被过滤  

s.add(key)  
s.remove(key)  

两个set可以做数学意义上的交集、并集等操作  

    > s1 = set([1, 2, 3])  
    > s2 = set([2, 3, 4])  
    > s1 & s2  
    {2, 3}  
    > s1 | s2  
    {1, 2, 3, 4}  

### 函数  

常见函数：abs(), max(), min(), int(),isinstance(),  
位置参数，默认参数  
可变参数（*args):  

    def person(name, age, **kw):  
        print('name:', name, 'age:', age, 'other:', kw)

关键字参数（'**kw含参数名的参数）:

    >def person(name, age, **kw):
        print('name:', name, 'age:', age, 'other:', kw)

**递归函数**  

一个在内部调用自身的函数，称为递归函数  

    def fact(n):
        if n==1:
            return 1
        return n * fact(n - 1)

注意，过深的调用会导致栈溢出  

### 高级特征

**切片**：list[10"20]  
**迭代**：for循环来遍历list或tuple  

    for key in dict:  
    for value in dict.values():  
    for key, value in dict.items():  

**列表生成式**  

    > [x * x for x in range(1, 11)]
    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]  

    # 两层循环，生成全排列  
    > [m + n for m in 'ABC' for n in 'XYZ']
    ['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']

**生成器**  

一边循环一边计算的机制  

    > g = (x * x for x in range(10))  #用()代替[]
    > for n in g:
            # print(n)
            yield n  #yield关键字定义generator  

    >next(g)  #一个个获取值  

    > def fib(max):
        n, a, b = 0, 0, 1
        while n < max:
            yield b
            a, b = b, a + b
            n = n + 1
        return 'done'  
    > g = fib(6)
    > while True:
        x = next(g)
        print('g:', x)

**迭代器**  

> 可以被next()函数调用并不断返回下一个值的对象称为迭代器：Iterator

### 函数式编程  

高阶函数:把函数做为参数传入的函数  

map():接收两个参数，一个是函数，一个是Iterable，map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回  

    >list(map(str, [1, 2, 3, 4, 5, 6, 7, 8, 9]))
    ['1', '2', '3', '4', '5', '6', '7', '8', '9']

reduce():把一个函数作用在一个序列[x1, x2, x3, ...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算  
    > from functools import reduce
    > def fn(x, y):
         return x * 10 + y
    
    > reduce(fn, [1, 3, 5, 7, 9])
    13579

filter  

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

- 2017/8/30 22:24:17 增补高级特征及函数式编程  
- 2017/8/28 22:01:16 增补字符串，列表内容  
- 2017/8/27 14:06:52 init  

参考资料  

- [廖雪峰Python3教程](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
