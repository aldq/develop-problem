# flask跨域处理


- 安装 
  - pip install flask_cors
- 初始化的时候加载配置，这样就可以支持跨域访问了
  ```
    from flask_cors import CORS
    app = Flask(__name__)
    CORS(app, supports_credentials=True)
    if __name__ == "__main__":
        app.run()
  ```