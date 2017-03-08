在Linux上的配置
=============

### 下载安装FBX SDK

在Linux上下载安装步骤如下所示：

1. 打开官网[http://www.autodesk.com/fbx](http://www.autodesk.com/fbx)
2. 找到下载页面，接着下述步骤执行。
3. 找到适配Linux的安装包文件。
4. 下载到电脑上，这是一个压缩过的安装包( *.tar.gz* )。
5. 解压安装包到某个空目录中，接下来这个目录径路会使用<你的FBX SDK安装路径>替代。
6. 接着需要按照文件 *<你的FBX SDK安装路径>/Install_FbxFileSdk.txt* 中所诉执行操作。
7. 阅读文件 *<你的FBX SDK安装路径>/readme.txt* ，它包含了最新版本的更新说明，以及最新的文档。

### Linux上的运行库

以下是Linux上不同运行库的相关说明：

|库文件|描述|
|-----|---|
|<你的FBX SDK安装路径>/lib/gcc4/x86/release/libfbxsdk.so|gcc4.0编译器，动态链接库，release版，32位。|
|<你的FBX SDK安装路径>/lib/gcc4/x86/debug/libfbxsdk.so|gcc4.0编译器，动态链接库，debug版，32位。|
|<你的FBX SDK安装路径>/lib/gcc4/x86/release/libfbxsdk-static.a|gcc4.0编译器，静态链接库，release版，32位。|
|<你的FBX SDK安装路径>/lib/gcc4/x86/debug/libfbxsdk-static.a|gcc4.0编译器，静态链接库，debug版，32位。|
|<你的FBX SDK安装路径>/lib/gcc4/x64/release/libfbxsdk.so|gcc4.0编译器，动态链接库，release版，64位。|
|<你的FBX SDK安装路径>/lib/gcc4/x64/debug/libfbxsdk.so|gcc4.0编译器，动态链接库，debug版，64位。|
|<你的FBX SDK安装路径>/lib/gcc4/x64/release/libfbxsdk-static.a|gcc4.0编译器，静态链接库，release版，64位。|
|<你的FBX SDK安装路径>/lib/gcc4/x64/debug/libfbxsdk-static.a|gcc4.0编译器，静态链接库，debug版，64位。|

### 使用makefile来帮助引导

你可以在示例代码(<你的FBX SDK安装路径>/samples/)里找到相应makefile文件。每个示例都有一个makefile文件，你可以使用这些文件作为项目模型。


*翻译者：listenlin*  
*原文档地址： [http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_408B9928_104E_463E_994D_ACD4CB8341A9_htm](http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_408B9928_104E_463E_994D_ACD4CB8341A9_htm)*  
*时间：2016.11.23*  
*联系邮箱：<listenlin521@foxmail.com>*