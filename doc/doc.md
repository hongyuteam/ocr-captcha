# Doc

### 依赖

```
# 生成依赖文件
pip freeze > requirements.txt

# 安装依赖文件
pip install -r requirements.txt

# 安装依赖文件 腾讯云 源
pip install -r requirements.txt -i https://mirrors.cloud.tencent.com/pypi/simple

# 查看依赖包位置
pip show flask
/home/ubuntu/.local/lib/python3.10/site-packages

# requirements.txt 依赖
onnxruntime
Pillow
numpy
opencv-python==3.4.16.59
Flask

```

### 运行

```
# 启动
/usr/bin/python3 main.py --port 8080 --ocr --old --det
```


### 打包步骤和命令

- 安装 pyinstaller

```
pip install pyinstaller
```

- 尝试打包生成 main.spec 文件

```
pyinstaller -D main.py -p E:\code\python\ocr_api_server\envs\ocr_api_server\Lib\site-packages

pyinstaller -F -w -i favicon.ico -p E:\code\python\ocr_api_server\envs\ocr_api_server\Lib\site-packages main.py

```

- 修改 main.spec 配置文件 pathex=[] datas=[]

```

a = Analysis(
    ['main.py'],
    pathex=['E:\\code\\python\\ocr_api_server\\envs\\ocr_api_server\\Lib\\site-packages'],
    datas=[
        ('E:\\code\\python\\ocr_api_server\\envs\\ocr_api_server\\Lib\\site-packages\\onnxruntime','onnxruntime'),
        ('E:\\code\\python\\ocr_api_server\\envs\\ocr_api_server\\Lib\\site-packages\\ddddocr','ddddocr')
    ],
)
```


- 打包

```
pyinstaller main.spec
```

