# ApredenFlask
Información paso a paso que eh logrado capturar sobre flask los ultimos 2 años.

```
import webview
from flask import Flask,request



app = Flask(__name__)
wiwdow=webview.create_window( "Nombre de la app",app,)

@app.route('/',methods=['GET','POST'])
def index():
    return "<h1>Hello, Desktop!</h1>"


if __name__ == '__main__':
    webview.start()
```
