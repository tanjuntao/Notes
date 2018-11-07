## 在 Windows 中同时安装 Python2 和 Python3

1. 首先需要去 [python官网](http://www.python.org) 下载最新的 python 安装包，分别下载`python2` `python3` 的安装包
2. 如果在安装时有选项：`add python to PATH`，那么就勾选，否则就需要设置一下`环境变量`
    + 编辑变量`PATH`
    + 对于 python2，先后添加下面两个环境变量(假设安装在 ``C:\python27`` 文件夹中)
        * `C:\python27\`
        * `C:\python27\Scripts\` 
    + 对于 python3，先后添加下面两个环境变量(假设安装在 `C:\python37`文件夹中)
        * `C:\python37\`
        * `C:\python37\Scripts\`
3. 修改`python27`文件夹中`python.exe`为`python2.exe`；修改`python37`文件夹中`python.exe`为`python3.exe`。这样做的目的是为了能够在使用 python2 和 python3 时有所区分。
4. 在 `cmd` 中直接输入 `python2`，那么使用的将是`python2.exe`，输入`python3`那么使用的将是`python3.exe`.
5. 在`pycharm`中选择`interpreter`时可以选择`python2.exe`也可以选择`python3.exe`