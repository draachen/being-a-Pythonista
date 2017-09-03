## Python版本控制  

注：pyenv 不支持windows  

### Windows的隔离环境配置  

使用py -2制定python2的环境  
使用py -3制定python3的环境  

使用pip安装库  

pip2 install virtualenv  
pip3 install virtualenv  

pip3 list #显示当前安装的package  

### virtualenv

virtualenv venv #当前目录下创建虚拟环境venv  

virtualenv --system-site-package venv #安装和真是环境一样的隔离环境  

virtualenv venv --python=python2.7 #使用非默认Python解释器创建隔离环境  

venv\Scripts\activate.bat #激活虚拟环境  

deactivate #退出激活  
rm -f venv #删除环境  

进入virtualenv并激活  
返回主目录 python weatherquery.py  

### Changelog  

- 2017/9/3 10:12:53 draachen 创建  

参考资料：

- [virtualenv](https://virtualenv.pypa.io/en/latest/)