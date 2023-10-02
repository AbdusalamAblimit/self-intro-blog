---
title: Windows配置vscode的C++环境
date: 2023-09-18 22:47:39
tags:
- Windows
- Vscode
---

## 1. 下载mingw64

从 https://github.com/niXman/mingw-builds-binaries/releases 下载mingw64。可以是最新版的这个：

<img src="https://abdusalam-typora.oss-cn-beijing.aliyuncs.com/img-for-typora/image-20231002145257213.png" alt="image-20231002145257213" style="zoom:50%;" />

解压后放到某个目录，以`C:/mingw64`为例。

## 2. 配置文件

安装下面这个扩展：

![image-20230918225454162](https://abdusalam-typora.oss-cn-beijing.aliyuncs.com/img-for-typora/image-20230918225454162.png)

然后再`.vscode`目录编写下面的文件：

c_cpp_properties.json

```json
{
    "configurations": [
        {
            "name": "Win32",
            "includePath": [
                "${workspaceFolder}/**"
            ],
            "defines": [
                "_DEBUG",
                "UNICODE",
                "_UNICODE"
            ],
            "windowsSdkVersion": "10.0.22621.0",
            "compilerPath": "C:/mingw64/bin/g++.exe",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "gcc-x64"
        }
    ],
    "version": 4
}
```

launch.json

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/${fileBasenameNoExtension}.exe",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": true,
            "MIMode": "gdb",
            "miDebuggerPath": "C:/mingw64/bin/gdb.exe",
        }
    ]
}
```

tasks.json

```json
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "cppbuild",
			"label": "C/C++: g++.exe build active file",
			"command": "C:/mingw64/bin/g++.exe",
			"args": [
				"-fdiagnostics-color=always",
				"-g",
				"${file}",
				"-o",
				"${fileDirname}\\${fileBasenameNoExtension}.exe"
			],
			"options": {
				"cwd": "C:/mingw64/bin"
			},
			"problemMatcher": [
				"$gcc"
			],
			"group": {
				"kind": "build",
				"isDefault": true
			},
			"detail": "compiler: C:/mingw64/bin/g++.exe"
		}
	]
}
```

然后就可以了。
