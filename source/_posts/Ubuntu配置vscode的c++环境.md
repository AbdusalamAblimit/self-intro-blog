---
title: Ubuntu安装Visual Studio Code
date: 2023-09-15 13:30:34
tags:
-Ubuntu
-vscode
---



 首先安装vscode或者在vscode里连接上你的ubuntu系统，然后安装一下依赖：

```bash
apt install gcc g++ make gdb
```

然后在vscode里安装下面这两个依赖：

![image-20230915133703524](https://abdusalam-typora.oss-cn-beijing.aliyuncs.com/img-for-typora/image-20230915133703524.png)

![image-20230915133713002](https://abdusalam-typora.oss-cn-beijing.aliyuncs.com/img-for-typora/image-20230915133713002.png)

接着点击左下方的齿轮，再点击`setting`，在输入框里输入`code runner in Terminal`，然后勾选那个选项：

![image-20230915133833602](https://abdusalam-typora.oss-cn-beijing.aliyuncs.com/img-for-typora/image-20230915133833602.png)

然后用vscode进入一个空目录创建一个文件`main.cpp`然后编写以下程序：

```c++
#include<bits/stdc++.h>
using namespace std;
int main()
{
    cout<<"hello"<<endl;
    return 0;
}
```

点击F5即可调试运行这个程序。

推荐使用以下配置：

launch.json:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "C/C++",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}/${fileBasenameNoExtension}",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "preLaunchTask": "compile",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ]
        }
    ]
}

```

tasks.json:

```json
{
    "version": "2.0.0",
    "tasks": [{
            "label": "compile",
            "command": "g++",
            "args": [
                "-g",
                "${file}",
                "-o",
                "${fileDirname}/${fileBasenameNoExtension}"
            ],
            "problemMatcher": {
                "owner": "cpp",
                "fileLocation": [
                    "relative",
                    "${workspaceRoot}"
                ],
                "pattern": {
                    "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
                    "file": 1,
                    "line": 2,
                    "column": 3,
                    "severity": 4,
                    "message": 5
                }
            },
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}

```



**注意**：当前这个方法里，只会编译当前打开的.cpp文件。如果你的程序是有自定义的头文件和多个源文件，那么还需要进一步修改`.vscode`目录里的json文件。后续我会将这个方法的连接放在这里。

