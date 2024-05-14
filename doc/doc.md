# Doc

### 依赖

```
# 生成依赖文件
pip freeze > requirements.txt

# 安装依赖文件
pip install -r requirements.txt
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

