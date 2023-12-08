# 大寰夹爪插件
---
**该AddOn适用于大寰夹爪PGE系列。包括夹爪指令块、夹爪控制页面**

## 插件信息

* 名称：dh_custom_cmd
* 版本：v2.2

## 安装指南

* 系统要求：

    控制器：v1.7.1.19 及以上  
    App：v1.7.1.16 及以上  
    JAKA-AddOn-Kit：v1.3及以上  

* 安装插件

    打开App-设置-系统设置-附加程序，点击右上角的“+”按钮，安装该插件。

    <div align="center"><img width="700"  src="./img/安装插件.png"/></div>


* 安装夹爪
  
    1. 通过控制柜RS485通道连接
   
    <div align="center"><img width="500"  src="./img/cab485.png"/></div>
   
    2. 通过大寰提供的JAKA专用转接线连接到TIO接口连接夹爪。
   
    <div align="center"><img width="500"  src="./img/TIO485.png"/></div>


## 配置指南    

* 配置插件
  
    运行插件，点击插件操作选项栏中的“齿轮”按钮，进入配置页面。

    <div align="center"><img width="700"  src="./img/AddOn_Config.png"/></div>

    1. Socket port: 夹爪自定义指令使用了socket通讯，会占用一个socket端口，如有冲突可以修改使用的端口号。
    2. modbus type: 夹爪连接方式选择，若通过末端TIO连接请选择TIO，若通过控制柜RS485连接请选择Cabinet。

* 配置通讯

    TIO连接时需要如下配置：   
      1. 配置模拟输入通道，复用为RS482通道2。
   
    <div align="center"><img width="500"  src="./img/TIO通道.png"/></div>

      2. 添加信号量status_init,status_run,speed,force,position。

    <div align="center"><img width="500"  src="./img/485配置.png"/></div>

    通过控制柜RS485连接：
      3. 要保证夹爪的从站id为1，波特率115200，数据位长度8，停止位长度1，无校验。


## 使用说明

**指令块**  
在App编程页面-扩展中找到夹爪指令块。

<div align="center"><img width="800"  src="./img/夹爪指令块.png"/></div>

1. 初始化夹爪：可以选择两种初始化方式，可参考大寰夹爪使用手册。
2. 控制夹爪：支速度（1-100）、力度（20-100）、位置控制（0-100）。单位均为百分比，超出上/下限视为使用上/下限。
3. 获取夹爪状态：初始化状态（0,1,2）、加持状态(0,1,2)、位置。返回字符串类型数据。

**控制页面**
在附加程序页面，AddOn的操作选项一列中找到"地球"按钮，点击打开控制页。

<div align="center"><img width="800"  src="./img/找到控制页面.png"/></div>

* 使用示例
  
<div align="center"><img width="800"  src="./img/程序示例.png"/></div>


## **故障排除**

* 常见问题
  暂无

<!-- * 插件日志

如果插件生成日志文件，则需说明该如何查看、分析这些日志以解决问题。 -->

## **更新和升级**

<!-- * 更新指南

提供如何获取、安装插件以进行更新的说明。 -->

**版本历史**

* v2.2.0

    * 基于AddOn3.0开发，支持控制柜rs485和tio。
    * 基于PGE系列通讯手册开发。
    * 控制页面控制支持



**支持和联系方式**

* 了解更多[AddOn信息](https://jakacobot.github.io/guide/addOn/aboutaddOn.html)
* 学习该AddOn的[开发教程](https://jakacobot.github.io/guide/addOn/demo_DHGripper.html)。

**插件获取方式**

* 联系JAKA销售或技术人员获取。
* 通过GitHub自行下载打包，[点击跳转](https://github.com/JakaCobot/jaka_addon_kit/tree/main/Template)。

