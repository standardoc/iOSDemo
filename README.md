#### 这个Demo是作为原生iOS的项目框架整理，希望能够统一以这种方式去构建iOS项目

##### 一、项目结构说明：

项目的第三方库以CocoaPods工具管理，安装好CocoaPods后使用.xcworkspace打开项目  

**一级目录说明：**

Src: 存放源代码

Resource: 存放资源文件，图片、音频等

ProConfig: 当项目存在多个target时，用来区分配置

ThirdPart: 存放第三方资源（某些不能通过cocoapods管理的库）

**二级目录结构说明**

项目源码主要以 `功能模块` 区分，如Demo中功能分为四个：Home, News, Find, Mine  
Demo介绍的是使用MVC模式管理，按照MVC创建文件夹

Home:  Model, View, Controller  
News:  Model, View, Controller  
Find:  Model, View, Controller  
Mine:  Model, View, Controller  

Tools: 这个文件夹下边，存放公共的工具类，网络请求封装，自定义UI，全局宏定义等等文件

---

##### 二、技术栈
	
网络通讯：NSURLSession、AFNetworking

* NSURLSession: iOS提供的NSURLSession，比在iOS9以后弃用的NSURLConnection强大,坑少,好用。

* AFNetworking: 是iOS开发网络请求使用特别广泛的第三方库，推荐使用

数据存储：CoreData、Sqlite

* CoreData: iOS提供的使开发者可以把数据当做对象来操作的框架，底层用sqlite实现

* FMDB：是iOS平台的SQLite数据库框架，FMDB以OC的方式封装了SQLite的C语言API

页面布局：StoryBoard、Masonry、XIB

* StoryBoard: iOS提供的方便实现UI约束布局的方式，AutoLayout效率高，用来搭建项目整体框架

* Masonry: 是一个轻量级的布局框架，采用优雅的链式语法，是实现纯代码布局的最佳方式

* XIB：实现小的、不复杂的布局比较方便

单元测试：XCTest

* XCTest: 是iOS提供的测试框架，保证测试函数在持续开发中的正确性

内存检测：Instruments

* Instruments: 内存检测工具，及时发现定位问题，并解决问题

类库管理：CocoaPods

* CocoaPods: 类库管理工具, 自动升级和维护项目中的第三方库

---

##### 三、统一规范

1. 项目目录结构如上统一
2. 视图使用StoryBoard和Masonry相结合的方式，Masonry适用于页面十分复杂的情况
3. 线下断点调试，线上用友盟统计搜集奔溃信息
4. 第三方库统一使用CocoaPods管理
5. 开发模式使用MVC（MVVM如更合适，可提出学习方案并使用）