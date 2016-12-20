---
layout: post
title: macOS开发入门教程之一：初识Xcode
date: 2016-12-21 00:00:00 +0000
categories: macOS开发教程
tags:
- macOS
- Xcode
- 教程
---
想开发你自己的macOS app？
苹果公司现在已经将macOS app（应用程序）开发过程做得难以置信的简便了，本教程将给出一个示范，你将学会如何创建你的第一个 macOS app，即使你是一只菜鸟。

- 1.在第一部分教程中，我们将学习如何获得macOS app开发所需的工具，以及探索Xcode，学习如何构建和运行macOS app以及UI设计。  
- 2.在第二部门教程中，我们将在Xcode中剖析macOS app的组件。 从macOS app启动的方式，到UI如何构建再而如何用户处理交互进行一个系统性了解。  
- 3.在最后部分你将自己上手操作，从无到有的建立你的第一个macOS app。  

---
***提示：**在开始本教程学习之前你需要做以下准备工作：
- **如果你是Swift新手**，本教程需要Swift编程语言的相关知识。
- **如果你有iOS开发经验**，你可以粗滤浏览第一部分甚至直接跳到下一部分。
- **如果你没有iOS或macOS开发经验**，希望你能认真学习。*

## 剃牦牛
工欲善其事，必先利其器。搞开发需要配置开发环境，这个过程有时候可能会比较繁复，我们称为“剃牦牛”（Yak Shaving），但是正如前面说到的：“苹果公司现在已经将macOS app（应用程序）开发过程做得难以置信的简便了”，所以环境配置也非常简单。成为一个macOS开发者之前，你只需要获得以下工具：
- **安装了macOS系统的Mac，**一般情况下macOS（2016年，苹果公司将操作系统重命名为“macOS”）操作系统只能运行于苹果电脑上，所以你需要一台Mac来开发和运行macOS app。如果你想了解改购买哪种Mac比较合适，我认为Mac Mini再额外添加内存和固态硬盘（或Fusion drive设备）是一种经济与性能的平衡选择。
- **一个AppleID，**用于在苹果App Store下载相关工具。
- **Xcode，**这是一个用于macOS app开发的IDE和工具链，我们将学习如何安装Xcode。


### 获取工具
和其他平台不一样，开发macOS的应用程序必须安装一个工具——即Xcode。Xcode是一把开发iOS、watchOS、tvOS及macOS app的瑞士军刀，它包含你所需的一切。  
如果你没有安装 `Xcode` ，点击桌面左上角菜单栏的苹果图标并选择 `App Store` 打开Mac App Store。  
<div align=center>
![App Store](./images/AppStore.png)<br/>  
</div>  

查找并获取Xcode：  

<div align=center>
![App Store](./images/appstroe_xcode.png)<br/>  
</div>  

待Xcode下载并自动安装完成后，从 `Launchpad` 或 `应用程序` 文件夹中启动Xcode。当你第一次启动Xcode时，会要求你安装一些附加组件，按要求安装就可以了。启动Xcode后你会看到欢迎界面，如下：  

<div align=center>
![App Store](./images/xcode_welcome.png)<br/>  
</div>  

恭喜你！你已经获得了Xcode这个神器！继续学习，我们将了解它能做什么。

## Hello World!
Xcode是一个Integrated Development Environment (IDE)，它是一个从源代码编辑、编译到调试以及UI设计的工具集。  
当我们打开Xcode时可以创建一个新的项目或者打开一个已有的项目。你也可以在文件夹中直接双击一个 `.xcodeproj` 或 `.playground` 文件来打开他们。  

<div align=center>
![App Store](./images/open_finder-480x269.png)<br/>  
</div>  

### 创建一个新的app
在本教程中，我们经常会通过app实例来探索Xcode，但是国际惯例都要先学创建一个“Hello World”app，让我们也先按惯例行事。  
在Xode的欢迎界面中，点击 `Create a new Xcode project` 创建新项目：

<div align=center>
![App Store](./images/xcode_welcome.png)<br/>  
</div>  

模板选择器可以帮助你利用预设模板创建新项目，在 `macOS` 选项卡中你可以看到三种不同的核心macOS app类型：  

<div align=center>
![App Store](./images/temp_chooser.png)<br/>  
</div>  

这三种macOS app类型分别是：  
- **Cocoa Application:**基于窗口UI的macOS桌面应用，Cocoa是所有macOS应用程序的框架。  
- **Game:**基于苹果SpriteKit或SceneKit框架的游戏程序。  
- **Command Line Tool:**基于命令行文本UI，在shell中运行的实用工具。  
选择 `Cocoa Application` 并点击 `Next`，在下一界面中设置产品名称为 `HelloWorld`，设置编程语言为 `Swift` ，选定 `Use Storyboards` 的复选框：  

<div align=center>
![App Store](./images/create_options.png)<br/>  
</div>  

最后再点击 `Next`，并选择你要保存项目的位置。  
这样我们就创建了一个新的、空的项目用于把你的奇思妙想实现为macOS app。接下来我们构建并运行它，看看它是否能够运行。

### 运行你的macOS app
无论你是打开一个现成的macOS app项目，还是创建一个新的，第一要务就是构建并运行它，看看是否能够运行。  
这涉及到将源代码编译为机器码，打包所需资源，然后再执行程序。这个过程很复杂，但是幸运的是有Xcode的鼎力相助，构建和运行你的项目就像播放音乐一样简单，点击Xcode项目界面左上角的播放按钮：  

<div align=center>
![App Store](./images/build_run.png)<br/>  
</div>  

或者你也可以使用快捷键 `⌘R`。  

<div align=center>
![App Store](./images/runAnewPro.png)<br/>  
</div>  

***提示：**在你第一次在Xcode中构建和运行app时，会提示 `Enable Developer Mode on this Mac?` 你最好选择 `Enable` , `Developer Mode` 即开发人员模式允许Xcode在正在运行的进程中附加一个调试器（Debugger），这在构建应用程序时非常有用！*  

现在你的 `HelloWorld` app看上去还是空白的，让我们来完善它。
### 添加文本
你将要更新app的 `user interface (用户界面，简称UI)` 以让它成为真正的“HelloWorld”app，在这过程中我们将使用一个叫 `Interface Builder (界面生成器，简称IB)` 的工具。本教程的将教授很多关于IB的知识，但在这里你只需知道如何添加一些文字到UI布局当中。  
在项目导航中找到 `Main.storyboard` 文件并点选它：  

<div align=center>
![App Store](./images/proNavigator.png)<br/>  
</div>  

这样就在IB中打开了storyboard文件，你可以总览你的app：

<div align=center>
![App Store](./images/newAppIB.png)<br/>  
</div>  

最下面这个组件（名为“View Controller”）表示你的app的可视化外观。我们将给它添加一个文本标签来完善我们的“HelloWorld”app。
在Xcode窗口界面的右下角找到 `Object Library` 对象库，在搜索框中输入 `label` 然后选择 `Label` 条目：  

<div align=center>
![App Store](./images/labelEntry.png)<br/>  
</div>  

把 `Label` 条目从对象库拖动到 `View Controller` 的场景画布上：  

<div align=center>
![App Store](./images/labelOnViewController.png)<br/>  
</div>  

`Label` 就是文本标签，表示没有用户交互的静态文本，适合你的“HelloWord”app。我们不希望它只是显示“Label”这几个字，所以我们要设置一下它。
要配置标签，请选择它，然后打开Xcode窗口右上方的属性检查器（第4个选项卡）。将标题 `Title` 设置为“Hello macOS”，并将字体 `Font` 更新为“System 40”

<div align=center>
![App Store](./images/labelConfig.png)<br/>  
</div>  

你可能会看到标签的大小不正确 ,接下来需要修复该错误，并将其设置到正确的位置。  
可以使用称为“自动布局”的系统在macOS中定位UI元素，这允许你根据UI元素的关系指定UI元素的位置和大小。为了把“Hello macOS”标签放在窗口的中心，我们需要添加约束来实现这一点。  
再次选择文本标签，然后单击底部栏中的对齐按钮 `Align`（左起第三个）。 同时勾选“Horizontally in Container”和“Vertically in Container”复选框，并确保它们都设置为0。在“Update Frames”选择框中选择“Items of New Constraints”，最后单击“Add 2 Constraints”按钮。  

<div align=center>
![App Store](./images/alignButton.png)<br/>  
</div>  

这样就更新了storyboard，以调整标签大小并正确定位。  
构建和运行app（通过单击播放按钮或使用 `⌘R` 快捷键）查看您的“HelloWorld macOS app”。

<div align=center>
![App Store](./images/helloMacOS.png)<br/>  
</div>  

**搞定！**
