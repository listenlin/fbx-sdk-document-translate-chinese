在Mac OS上的配置
==============

### 下载安装FBX SDK

在Mac OS上下载安装如下步骤所示：

1. 打开官网[http://www.autodesk.com/fbx](http://www.autodesk.com/fbx)
2. 找到下载页面，然后跟着下面步骤走。
3. 找到适配Mac OS系统的FBX SDK安装包下载。
4. 安装包是一个被压缩的安装程序（ *\*.pkg.tgz* ）。
5. 解压安装文件。
6. 点击执行安装程序。
7. 安装程序需要指定一个空白文件夹作为安装路径，这个路径在接下来的文档中会用<你的FBX SDK安装路径>替代。
8. 阅读文件 *<你的FBX SDK安装路径>/readme.txt* ，它包含了最新版本的更新说明，以及最新的文档。

### Mac OS上的运行库

以下是Mac OS上不同运行库的相关说明：

|库文件|描述|
|-----|---|
|<你的FBX SDK安装路径>/lib/clang/release/libfbxsdk.a|苹果LLVM编译器5.0版本，静态链接库，release版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/release/libfbxsdk.dylib|苹果LLVM编译器5.0版本，动态链接库，release版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/debug/libfbxsdk.a|苹果LLVM编译器5.0版本，静态链接库，debug版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/debug/libfbxsdk.dylib|苹果LLVM编译器5.0版本，动态链接库，debug版，intel处理器32(i386)/64(x86_64)位。| 
|下面的库只适用于用 *stdlib=stdc++* 替换了默认库 *-stdlib=libc++* 的程序|
|<你的FBX SDK安装路径>/lib/clang/libstdcpp/release/libfbxsdk.a|苹果LLVM编译器5.0版本，静态链接库，release版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/libstdcpp/release/libfbxsdk.dylib|苹果LLVM编译器5.0版本，动态链接库，release版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/libstdcpp/debug/libfbxsdk.a|苹果LLVM编译器5.0版本，静态链接库，debug版，intel处理器32(i386)/64(x86_64)位。|
|<你的FBX SDK安装路径>/lib/clang/libstdcpp/debug/libfbxsdk.dylib|苹果LLVM编译器5.0版本，动态链接库，debug版，intel处理器32(i386)/64(x86_64)位。|

### 使用makefile来帮助引导

你可以在示例代码(<你的FBX SDK安装路径>/samples/)里找到相应makefile文件。每个示例都有一个makefile文件，你可以使用这些文件作为项目模型。


*翻译者：listenlin*  
*原文档地址： [http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_724E9FAD_AFA0_4348_BDAA_6CF2FDF2FF55_htm](http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_724E9FAD_AFA0_4348_BDAA_6CF2FDF2FF55_htm)*  
*时间：2016.11.23*  
*联系邮箱：<listenlin521@foxmail.com>*