在Windows上的配置
===============

### 下载和安装FBX SDK

在Widnows上下载安装：

1. 前去[http://www.autodesk.com/fbx](http://www.autodesk.com/fbx)
2. 找到下载页面，跟随指引走。
3. 找到Windows版本的FBX SDK。
4. 下载Windwos版本的分发文件到你电脑上。这个分发文件是一个安装程序。
5. 运行安装程序，跟随步骤走。
6. 安装程序会让你指定安装路径。指定的安装路径应该是一个新文件夹或者空文件夹，在这个章节，这个文件夹会用“<你的FBX SDK安装路径>”替代。

你可以阅读“<你的FBX SDK安装路径>/readme.txt”来了解更多详细信息和版本变更信息，也包含了最新的文档信息。

**注意：**

* 安装程序不会修改Widnows注册表或者开始目录。
* 你可以在一台电脑上安装多个版本的FBX SDK，只需要指定不同的安装路径即可。

### 卸载FBX SDK

为了移除FBX SDK，你只需要运行“<你的FBX SDK安装路径>/uninstall.exe”。

### Windows的运行库


确保你使用了和Visual Studio版本相匹配的运行库，这可以保证应用程序能在目标平台处理器架构上运行。在“<你的FBX SDK安装路径>/lib”目录中的FBX库文件如何储存组织，会依赖你所使用的Visual Studio版本、处理器类型和构建模式：

*<你的FBX SDK安装路径>/lib/\<compiler_version>/\<processor_type>/\<build_mode>*

比如：

*<你的FBX SDK安装路径>\lib\vs2012\x64\release*

每个安装目录下的lib子目录都会包含很多版本的库文件，很多不同的编译模式。下面的表格展示了FBX库文件的名称和描述说明。

**注意：** 在软件运行时，库文件 *.lib* 需要依赖对应的 *.dll* 动态链接库文件（可以查看表格中的“应用依赖”一列）。如果你想使用FBX SDK的库文件，就必须将对应版本的.dll动态链接库打包到应用中。

|库文件|描述|必需的运行库选项|必需的预处理定义|应用依赖|
|-----|---|--------------|-------------|-------|
|libfbxsdk.lib|动态链接||FBXSDK_SHARED|fbxsdk-\<version>.dll|
|libfbxsdk-md.lib|静态链接|/MD|||
|libfbxsdk-mt.lib|静态链接，多线程|/MT|||

下面的表格提供了运行库选项的相关说明描述。这些描述可在微软官网找到[http://msdn.microsoft.com/en-us/library/2kzt1wy3.aspx](http://msdn.microsoft.com/en-us/library/2kzt1wy3.aspx)。

|运行库选项|描述|
|--------|---|
|/MT|这代表了应用程序会使用多线程，并且使用静态链接版本的运行库，即将.lib文件打包进exe。定义_MT，是因为编译器要将LIBCMT.lib文件放入.obj文件，以便链接器再使用LIBCMT.lib去解决外部符号链接。|
|/MD|这代表了应用程序会使用多线程，并且使用动态链接库，即exe依赖.dll文件。定义_MT和_DLL，是因为编译器要将MSVCRT.lib文件放入.obj文件，应用程序就会静态链接MSVCRT.lib这个库，即打包进exe。这个MSVCRT.lib库其实只是一个封装层，它可以让链接器在链接时解决外部引用关系。而在真正运行程序时，它会调用MSVCR100.DLL这个动态链接库来执行真正的功能代码。也因此，用这种方式编译的程序，在运行时需依赖MSVCR100.DLL文件。|

**注意：** 这些库可以在微软的多线程库中链接使用，但是FBX SDK不能保证多线程安全。

### 配置Visual Studio

下面的示例都是基于Visual Studio 2010版本。

**注意：** 如果想编译和运行FBX SDK的示例程序，请查阅《[编译和运行示例程序](../../Sample Programs/Building and Running the Sample Programs.md)》

使用FBX SDK来创建一个Visual Studio工程：

1. 打开Visual Studio。
2. 点击菜单栏 New -> Project the File menu. ![创建项目图片](http://help.autodesk.com/cloudhelp/2016/ENU/FBX-Developer-Help/images/GUID-11F78F6D-D5DB-4285-8C06-E795F1F687AF-low.png)
3. 选择Visual C++ -> Win32。
4. 按照经验一步一步下去，直到点击Finish。新的工程和解决方案就出来了。
5. 在工程上点击右键，选择Properties。会如下显示对话窗口。 ![属性对话窗口](http://help.autodesk.com/cloudhelp/2016/ENU/FBX-Developer-Help/images/GUID-0F232FE1-5434-45AC-8275-16FAD8E0C3B6-low.png)
6. 在窗口左边的树形菜单中，选择Configuration Properties -> C/C++ -> General。
7. 在窗口右边的属性表中，在增加文件夹(Include Directories)的下拉菜单选择 <Edit>，然后 Additional Include Directories 窗口会显现。 ![窗口](http://help.autodesk.com/cloudhelp/2016/ENU/FBX-Developer-Help/images/GUID-0D5DCDEB-83CF-403B-BBDD-7830B08F80A0-low.png)
8. 在窗口的最上面，有一系列的方框，点击最上面的空白行，直到看见文件夹浏览。
9. 将“<你的FBX SDK安装路径>/include”路径添加进去。
10. 在窗口左边树形菜单中，选择Code Generation。 ![图](http://help.autodesk.com/cloudhelp/2016/ENU/FBX-Developer-Help/images/GUID-967C4D00-9BEE-42B9-A397-1F648D4DAF42-low.png)
11. 在属性表的右边，选择运行库的类型。对Visual C++编译器来说，有选项/MD, /MDd,/MT, /MTd等等。对于 Visual Studio，不是所有的编译选项都可用(具体看上方《Windows的运行库》一节)。
12. 在属性对话框中，选择Linker -> General。
13. 在Additional Library Dependencies中下拉选择<Edit>，会看见窗口弹出。
14. 输入“<你的FBX SDK安装路径>/lib”全路径。 ![图](http://help.autodesk.com/cloudhelp/2016/ENU/FBX-Developer-Help/images/GUID-E3C0656E-A356-40D8-8B49-A7FF828790F4-low.png)
15. 在属性窗口方框中，选择Linker -> Input。在Additional Dependencies下拉菜单中，选择<Edit>。在弹出的对话框中，输入正确的FBX SDK库文件所在文件夹路径，文件夹的组织，请看上方《Windows的运行库》一节。
16. 在上一步，如果你选择了在debug模式中使用静态链接库，你还需要按以下步骤操作：
	1. 在Ignore Specific Default Library下拉菜单，选择<Edit>，会有窗口弹出。
	2. 输入“LIBCMT”，点击OK。
	3. 在Additional Dependencies下拉菜单中，选择<Edit>，弹出窗口。
	4. 输入“wininet.lib”，点击OK。

**注意：** 如果你使用FBX SDK作为动态链接库，需要给预处理器增加“FBXSDK_SHARED”定义。

### 项目中关于预处理定义的注意点

如果你使用FBX SDK作为动态链接库，需要给预处理器增加“FBXSDK_SHARED”定义。在Visual Studio中，需要在项目中右键点击，选择Properties -> Configuration Properties -> C/C++ -> Preprocessor，然后编辑Preprocessor Definitions字段值。

**注意：** 从FBX SDK 2012版开始，下述问题已不再需要：

* 作为动态链接库使用时，不需要定义“KFBX_DLLINFO”。
* 从FBX SDK 2012版本开始，静态链接库需要构建于“_SECURE_SCL=1”之上，对于Visual Studio 2010及最新版本，这个是默认值。如果你使用的是Visual Studio 2010及以上版本，但却用了更老版本的FBX SDK，需要明确的设置“_SECURE_SCL=0”。如果你使用的是Visual Studio 2008，又用了FBX SDK 2012及最新版，你需要明确的设置“_SECURE_SCL=1”，否则，你可以删除定义的参数_SECURE_SCL。


*翻译者：listenlin*  
*原文档地址： [http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_6E7B1A2E_584C_49C6_999E_CD8367841B7C_htm](http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_6E7B1A2E_584C_49C6_999E_CD8367841B7C_htm)*  
*时间：2016.11.13*  
*联系邮箱：<listenlin521@foxmail.com>*

