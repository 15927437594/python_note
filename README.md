# <p align = "center"> python_note </p>

### python3+PyQt5+QtDesigner+pycharm安装及配置+将ui文件转py文件+PyInstaller打包程序
- 安装python3 : 下载官网的python3最新版本,然后将python.exe的父目录加入到系统变量Path中

- 安装PyQt5 : pip/pip3/pip3.7 install PyQt5

- 安装QtDesigner : pip/pip3/pip3.7 install PyQt5-tools

- 安装pycharm : 下载官网的pycharm-community最新版本

- 配置QtDesigner : pycharm中,依次打开Settings -> tools -> External Tools ->  "+" -> Create Tool ->

	Name : QtDesigner

	Description : 设计UI界面,生成.ui文件

	Program : C:\Users\jid\AppData\Local\Programs\Python\Python37\Lib\site-packages\pyqt5_tools\Qt\bin\designer.exe

	Working directory : $FileDir$

	-> OK

- 配置PyUIC : pycharm中,依次打开Settings -> tools -> External Tools ->  "+" -> Create Tool ->

	Name : PyUIC

	Description : 将.ui文件转换成.py文件

	Program : C:\Users\jid\AppData\Local\Programs\Python\Python37\python.exe

	Arguments : -m PyQt5.uic.pyuic  $FileName$ -o $FileNameWithoutExtension$.py

	Working directory : $FileDir$

	-> OK
	
- 安装PyInstaller : pip/pip3/pip3.7 install PyInstaller,然后将PyInstaller.exe的父目录加入到系统变量Path中

- 配置pip工具 : 将pip/pip3/pip3.7.exe的父目录加入到系统变量Path中


### 常用命令
- 查看python的版本 : `python -V`

- 查看第三方库的版本 : 举例 `import numpy -> numpy.__version__`

- 列出所有安装的库 : `pip3 list`

- 列出所有已过期的库 : `pip3 list --outdated`

- 单个更新库 : `pip3 install --upgrade lib_name`

- 安装指定版本的库 : `pip3 install lib_name==xxx`

- 更新pip : `python.exe -m pip install --upgrade pip`


### 打包注意事项
- 项目打包使用到.egg文件时,需要在spec文件中的coll = COLLECT()添加a.zipfiles

### 制作egg文件
```bash
python setup.py bdist_egg
```

### 生成包引用文件
```bash
pip3 freeze > requirements.txt
```

### 从aliyun等服务器上安装python库
```bash
pip3 install PyQt5 -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com
```

### 安装包引用文件
```bash
pip3 install -r requirements.txt
```

### 安装某些实际库名和显示库名不一致的python库
```bash
pip3 install opencv-python(显示为cv2)
pip3 install pycryptodome(显示为Crypto)
pip3 install Pillow(显示为PIL)
```
							
