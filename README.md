# <p align = "center"> python_note </p>

### python3+PyQt5+QtDesigner+pycharm安装及配置+将ui文件转py文件+PyInstaller打包程序
- 安装python : 下载官网的python最新版本后,将C:\Users\Administrator\AppData\Local\Programs\Python\Python36配置到系统变量的Path中

- 配置pip环境变量 : 将C:\Users\Administrator\AppData\Local\Programs\Python\Python36\Scripts配置到系统变量的Path中

- 安装PyQt5 : pip install  PyQt5==5.12

- 安装QtDesigner : pip install PyQt5-tools==5.12.3.1.5

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
	
- 安装PyInstaller : pip install PyInstaller,然后将PyInstaller.exe的父目录加入到系统变量Path中

- 配置pip工具 : 将pip.exe的父目录加入到系统变量Path中


### 常用命令
- 查看python的版本 : `python -V`

- 查看第三方库的版本 : 举例 `pip show numpy`

- 列出所有安装的库 : `pip list`

- 列出所有已过期的库 : `pip list --outdated`

- 单个更新库 : `pip install --upgrade lib_name`

- 安装指定版本的库 : `pip install lib_name==xxx`

- 更新pip : `python -m pip install --upgrade pip`


### 打包注意事项
- 项目打包使用到.egg文件时,需要在spec文件中的coll = COLLECT()添加a.zipfiles

### 制作egg文件
```bash
python setup.py bdist_egg
```

### 生成包引用文件
```bash
pip freeze > requirements.txt
```

### 删除全部包引用文件
```bash
pip uninstall -r requirements.txt -y
```

### 从aliyun等服务器上安装python库
```bash
pip install PyQt5 -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com
```

### 安装包引用文件
```bash
pip install -r requirements.txt
```

### 安装某些实际库名和显示库名不一致的python库
```bash
pip install opencv-python(显示为cv2)
pip install pycryptodome(显示为Crypto)
pip install Pillow(显示为PIL)
```
							
