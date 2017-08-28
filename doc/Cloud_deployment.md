## 部署到云端  

**Heroku**  

选择云容器的独享服务器，配置requirements.txt,runtime.txt以及Procfile  

    使用Heroku建立应用
    >pip install -r requirements.txt  
    >heroku git:remote -a fast-garden-97353

**SAE**  

选择Python共享服务器，应用配置文件config.yaml和代码配置文件index.wsgi。  

使用virtualenv  

    >virtualenv venv  
    >. venv/Scripts/activate  #set up a virtual env w/ same package like real environment  
    >virtualenv --systemsite-packages venv

    进入virtualenv并激活，然后返回主目录  
    >python weatherquery.py  
    >result = requests.get(url, timeout=1)  #Heroku访问remote API, requests.get不能返回数据，将timeout=1删除即可。

10分钟让你的APP发布到互联网  

    注册 (2 mins)
    
    打开 www.pythonanywhere.com ，注册你的账户。
    创建 Web App (1 mins)

        登录后，切换到 Web 选项卡，点击 Add a new web app，根据提示进行初始设置。
        打开 yourname.pythonanywhere.com ，居然就可以正常访问了，帅！

    上传你的文件 ( 2 ~ 5 mins)

        切换到页面的 Files 选项卡，进入 mysite/ 文件夹，将 flask_app.py 修改成你 ch4 用 Flask 写好的主程序 ，点击 右上角 Save 保存。
        如果你还有其他程序运行需要的文件和文件夹，都上传到mysite/ 文件夹下。页面左边的 Directories 可以用于新建文件夹，页面右边的 Upload a File 可用来上传文件。

    大功告成 ( 2 mins)

        点击左上角 pythonanywhere 的图标返回，切换到 Web 选项卡，点击 Reload yourname.pythonanywhere.com
        再打开 yourname.pythonanywhere.com ，你会发现，你的网站就出现啦！大功告成！

代码调试  

每次更改本地代码查看效果，需push到云服务器然后通过微信交互验证代码是否ok，且本地运行脚本无法接收到微信端服务器的请求。  
搜索后了解到可以通过ngrok来实现上述功能。试用之发现ngrok的官方网页国内访问太慢，故选用汉化的ngrok。  

参考资料  

- ["微信开发如何做本地调试？"](https://www.zhihu.com/question/25456655)  
- [汉化的ngrok](http://qydev.com/)

### Changelog  

- 2017/8/27 19:01:34 创建

参考资料  

- [Getting Started with Python on Heroku](https://devcenter.heroku.com/articles/getting-started-with-python#introduction)  
- [Deploying Python and Django Apps on Heroku](https://devcenter.heroku.com/articles/deploying-python)  

