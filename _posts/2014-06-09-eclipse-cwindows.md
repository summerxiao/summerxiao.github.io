---
layout: post
title: "Eclipse C++在windows下进行开发"
description: ""
category: 
tags: []
---
{% include JB/setup %}


#### 1. 在Project Explore空白区域点右键， 选择Import。出现如下对话框：
![Import-project.png](/assets/image/posts/eclipse-import-project.png)

#### 2. 选择 Existing Code as Makefile Project 选项， 点击 Next 按钮：
![Import-code.png](/assets/image/posts/eclipse-import-code.png)

#### 3. 选择Project 所在目录， 如果是linux下程序开发， 选择GNU Autotools Toolchain， 点击完成。

Eclipse工程配置。

在 <https://code.google.com/p/google-styleguide/source/browse/trunk> 下载需要的google style。

![google-styleguide.png](/assets/image/posts/google-styleguide.png)


#### 4. 导入此xml文件。

![eclipse-import-xml-1.png](/assets/image/posts/eclipse-import-xml-1.png)

选中当前工程的名称， 右击， 会出现上图所示的对话框。 选择属性，选中c/c++ general 中的formatter 会出现如下对话框。

![eclipse-import-xml-2.png](/assets/image/posts/eclipse-import-xml-2.png)

选中Enable project specific settings, 点击Import 按钮， 导入刚才你下载的所需要的google style.


#### 5. 将centos 6.3下的头文件导入依赖， 这样， 就可以找到相关依赖， 去掉警告。相关路径：

	<?xml version="1.0" encoding="UTF-8"?>
	<cdtprojectproperties>
	<section name="org.eclipse.cdt.internal.ui.wizards.settingswizards.IncludePaths">
	<language name="C Source File">

	</language>
	<language name="C++ Source File">
	<includepath>C:\header\usr\include</includepath>
	<includepath>C:\header\usr\local\include</includepath>
	<includepath>C:\header\usr\include\c++</includepath>
	<includepath workspace_path="true">H:\branch\XXX\src</includepath>
	<includepath>C:\header\usr\lib\gcc\x86_64-redhat-linux\4.4.4\include</includepath>
	<includepath>C:\header\usr\include\c++\4.4.4\backward</includepath>
	<includepath>C:\header\usr\include\c++\4.4.4</includepath>
	<includepath>C:\header\usr\include\c++\4.4.4\x86_64-redhat-linux</includepath>

	</language>
	</section>
	<section name="org.eclipse.cdt.internal.ui.wizards.settingswizards.Macros">
	<language name="C Source File">

	</language>
	<language name="C++ Source File">

	</language>
	</section>
	</cdtprojectproperties>

选中当前工程的名称， 右击选择Index->Rebuild， 生成Index。
