## Flask 教程  

Flask is FUN  

    from flask import Flask
    app = Flask(__name__)
    
    @app.route("/")
    def hello():
        return "Hello World!"

And Easy to Setup  

    $ pip install Flask
    $ FLASK_APP=hello.py flask run
     * Running on http://localhost:5000/

### Changelog  

- 2017/9/3 13:10:15 draachen创建  

参考资料  

-[Flask: web development, one drop at a time](http://flask.pocoo.org/)