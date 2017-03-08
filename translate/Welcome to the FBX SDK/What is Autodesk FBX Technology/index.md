什么是Autodesk FBX技术？
=====================


本篇会大致说明Autodesk FBX技术和它的功能特性。

Autodesk FBX SDK技术包含了一整套工具，用来让开发者对3D模型进行快捷的导入、修改和导出等操作，而FBX SDK是整套工具的一部分。通过Autodesk FBX来开发混合2D和3D数字内容的应用程序，有助于许多组织团队更有效的参与到数字媒体娱乐行业中来。

### 3D场景中的FBX文件格式

FBX格式文件(.fbx)一般是以二进制形式保存，也支持ascii形式，并且都是使用的 *.fbx* 后缀名。

FBX格式会将3D场景里的相机、灯光、网格、NURBS或其他的一些元素都保存进去。很多软件比如3ds max、maya、MotionBuilder等都可以从FBX格式里导入全部或部分场景元素，自然也可以将这些软件里的3D场景信息导出到FBX中，而这些功能实现都是使用的FBX SDK。

下面的示例是从ascii形式保存的FBX文件中，截取的部分内容。忽略的行数用“...”代表，然后人为增加了一些注释说明，这些注释都以“;”开头。

<pre>
; FBX 7.1.0 project file
; Copyright (C) 1997-2010 Autodesk Inc. and/or its licensors.
; All rights reserved.
; ----------------------------------------------------
FBXHeaderExtension:  {
       ; header information: global file information.
    FBXHeaderVersion: 1003
    FBXVersion: 7100
    CreationTimeStamp:  {
        Version: 1000
        Year: 2010
        Month: 1
        Day: 19
        Hour: 16
        Minute: 30
        Second: 28
        Millisecond: 884
    }
    Creator: "FBX SDK/FBX Plugins version 2011.2"
    SceneInfo: "SceneInfo::GlobalInfo", "UserData" {
 ...
}
GlobalSettings:  {
    Version: 1000
    Properties70:  {
        P: "UpAxis", "int", "Integer", "",1
        P: "UpAxisSign", "int", "Integer", "",1
        P: "FrontAxis", "int", "Integer", "",2
        P: "FrontAxisSign", "int", "Integer", "",1
        P: "CoordAxis", "int", "Integer", "",0
        P: "CoordAxisSign", "int", "Integer", "",1
        P: "OriginalUpAxis", "int", "Integer", "",-1
        P: "OriginalUpAxisSign", "int", "Integer", "",1
        P: "UnitScaleFactor", "double", "Number", "",1
        P: "OriginalUnitScaleFactor", "double", "Number", "",1
        P: "AmbientColor", "ColorRGB", "Color", "",0,0,0
        P: "DefaultCamera", "KString", "", "", "Producer Perspective"
        P: "TimeMode", "enum", "", "",6
        P: "TimeSpanStart", "KTime", "Time", "",0
        P: "TimeSpanStop", "KTime", "Time", "",46186158000
    }
}
 ...
; Object definitions
;------------------------------------------------------------------
Definitions:  {
    Version: 100
    Count: 2251
    ObjectType: "GlobalSettings" {
        Count: 1
    }
    ObjectType: "Model" {
        Count: 86
        PropertyTemplate: "FbxNode" {
            Properties70:  {
                P: "QuaternionInterpolate", "bool", "", "",0
                P: "RotationOffset", "Vector3D", "Vector", "",0,0,0
                P: "RotationPivot", "Vector3D", "Vector", "",0,0,0
                P: "ScalingOffset", "Vector3D", "Vector", "",0,0,0
                P: "ScalingPivot", "Vector3D", "Vector", "",0,0,0
 ...}
    ObjectType: "Material" {
        Count: 1
        PropertyTemplate: "FbxSurfacePhong" {
            Properties70:  {
                P: "ShadingModel", "KString", "", "", "Phong"
                P: "MultiLayer", "bool", "", "",0
                P: "EmissiveColor", "ColorRGB", "Color", "",0,0,0
                P: "EmissiveFactor", "double", "Number", "",1
                P: "AmbientColor", "ColorRGB", "Color", "",0.2,0.2,0.2
 ...}
    Model: 21883936, "Model::Humanoid:Hips", "LimbNode" {
        Version: 232
        Properties70:  {
            P: "ScalingMin", "Vector3D", "Vector", "",1,1,1
            P: "NegativePercentShapeSupport", "bool", "", "",0
            P: "DefaultAttributeIndex", "int", "Integer", "",0
            P: "Lcl Translation", "Lcl Translation", "", "A+",-271.281097412109,-762.185852050781,528.336242675781
            P: "Lcl Rotation", "Lcl Rotation", "", "A+",-1.35128843784332,2.6148145198822,0.42334708571434
            P: "Lcl Scaling", "Lcl Scaling", "", "A+",1,0.99999988079071,1
 ...
</pre>

**注意：**FBX格式并不全是纯文本化的(大多数是二进制)。为了更好的兼容性，程序应该使用FBX SDK从FBX文件中读取和写入场景信息。

### FBX软件开发工具包

开发者可以使用FBX SDK来创建应用程序，或者将其嵌入已有的应用程序。

注意FBX SDK并不是开源软件，不存在GPL等开源许可证，所以它的源代码也是不公开的。有些功能代码是包含到FBX SDK扩展部分的，并不在FBX SDK本身之中，比如Maya和3ds Max的一些自定义插件。最新版本或历史版本都可以在Autodesk FBX官网[http://www.autodesk.com/fbx](http://www.autodesk.com/fbx)中找到。没有Autodesk的许可授权，不能再次分发或打包FBX SDK。如果你想在开源项目中使用，必须给予用户一个Autodesk FBX官网的链接，以便其自行下载安装FBX SDK。

本章节还包含内容  
 
* [FBX程序示例](Sample FBX Applications.md)
* [适用FBX的情形](Where FBX Fits in the Creation Pipeline.md)


*翻译者：listenlin*  
*原文档地址： [http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_274163DA_9E89_4DCC_8AF6_10B0C498582E_htm](http://help.autodesk.com/view/FBX/2016/ENU/?guid=__files_GUID_274163DA_9E89_4DCC_8AF6_10B0C498582E_htm)*  
*时间：2016.11.8*  
*联系邮箱：<listenlin521@foxmail.com>*