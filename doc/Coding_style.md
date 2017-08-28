### 编程规则 

**程序代码结构**  

    #! python3
    # -*- coding: utf-8 -*-


    def main():
        print('Hello World!')


    if __name__ == '__main__':
        main()

**PEP8 规则摘要**  

导入  

    #顺序：标准库进口 , 相关的第三方库，本地库  

注释  

    #同行注释，中间两个空格
    #慎用行内注释  
    x = x + 1  # Compensate for border

缩进  

    #括号中使用垂直隐式缩进，对准左括号  
    foo = long_function_name(var_one, var_two,
                            var_three, var_four)  

    #悬挂缩进必须加多一层缩进（注意第一行无参数）  
    foo = long_function_name(
        var_one, var_two,
        var_three, var_four)

    #右括号另起一行时，需回退  
    result = some_function_that_takes_arguments(
            'a', 'b', 'c',
            'd', 'e', 'f',
    )

if语句跨行  

    #添加额外缩进  
    if (this_is_one_thing
            and that_is_another_thing):
        do_something()

续行

    #建议在二元运算符之后  
    income = (gross_wages
              + taxable_interest
              + (dividends - qualified_dividends)
              - ira_deduction
              - student_loan_interest) 

空格  

    #括号里边避免空格，函数调用的左括号前不能有空格  
    spam(ham[1], {eggs: 2})

    #逗号，冒号，分号之前避免空格
    if x == 4: print x, y; x, y = y, x

    #索引操作中的冒号当作操作符处理前后要有同样的空格 ( 一个空格或者没有空格）  
    ham[1:9], ham[1::3], ham[1:9:]  
    ham[lower:upper]  

    #二元运算符两边放置一个空格，优先级高的运算符或操作符前后不建议有空格  
    x = x*2 - 1  
    hypot2 = x*x + y*y

    #关键字参数和默认值参数的前后不要加空格  
    def complex(real, imag=0.0):
        return magic(r=real, i=imag)

文档字符串  

    #为所有公共模块、函数、类和方法书写文档字符串  
    除单行的文档字符串，其余的结尾"""应单独成行  
    """Return a foobang 
    Optional plotz says to frobnicate the bizbaz first. 
    """

### Changelog  

- 2017/8/28 20:36:33 整理  

参考资料  

- [PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
