         首个基于MSP430的微型四轴—Flappy430
Flappy430—The first nano quadcopter which use MSP430 as MCU

•	Author : HHY
•	Version : v1.0
•	Update : 2014/08/27
•	video：  http://v.youku.com/v_show/id_XNzYyNjI2Njg4.html

 Function：用于控制微型四旋翼飞行器。应该是首次在微型四旋翼飞行器上采用TI公司的MSP430系列单片机
           
           目前实现的功能：1 可以飞行，虽然还不是特别稳定；2 与C#单片机通信，显示各个数据； 3 完成部分说明书工作
            
           4 code内部均有详细注释。

 Waring： 本代码仅仅用作学习之用，禁止用于任何商业目的。但欢迎爱好者对其进行改进。
 
 描述： 这是Flappy430的开发代码。Flappy430是基于TI公司的MSP430F5310的一个代码，用于控制微型四轴飞行器。Flappy430既是
 代码的名字，也是我们的微型四旋翼飞行器的名字。事实上，它应该是首个基于MSP430的微型四轴飞行器/飞控/开发板。
 
 部分硬件定义：作者 HHY  Flappy430  Team
//     →   
//     1    2
//       X
//     3   4
//  PWM: PWM1-P1.5-TA4  PWM2--P1.2-TA1  PWM3--P1.3-TA2  PWM4--P1.4-TA3
//  PWM2    PWM1
//          x
//    PWM3     PWM4

版权声明
代码向430与四旋翼爱好者开源。但仅限学习之用。禁止用于商业目的。
授权：软硬件均保留所有权利。爱好者们可以作为学习之用
![image](https://github.com/yue435/flappy430/raw/master/images/jiaosi.jpg)
Flappy430的基本特性：
MCU:采用MSP430F5310 （应该是首个采用430芯片的小四轴）；
传感器：ITG3205（陀螺）+ADXL345（加速度计），预留mag3110磁强计位置；
无线：天地飞2.4G微型接收机，可以配合天地飞6及以上遥控器使用；
调试：FT232芯片，MicroUSB接口，可以直接连接电脑上位机；
电机：716电机+45MM螺旋桨 或者 720电机+55mm 螺旋桨；
驱动：MOS管驱动。MOS管开启后连接GND
电池：600mah，20c电池；
仿真：430标准14针接口。

上位机：amo网友多啦C梦写的上位机，C++编写，体积小，可以收发17个通道数据，能显示从4个电机数值到欧拉角等数据；

程序：编译环境：IAR5.20
       算法：核心姿态解算用的S.O.H madwick 提出的IMU.C（未加磁力计）。
       传感器：软件IIC 读取上面传感器的数据；
       中立点校正： 解锁后自动校正；
      
       学习及修改：PID参数在程序最开始，用IAR打开后可以自己修改；
       程序中有较为丰富注释；

     操作：加解锁与MWC飞控基本一致；各通道正反向方面，基本与天6A默认的通道正反一致。油门需要调至反向。
     
  
![image](https://github.com/yue435/flappy430/raw/master/images/hardware.jpg)
![image](https://github.com/yue435/flappy430/raw/master/images/yuanlitu.jpg)

2 代码 
代码分为头文件与源文件，都可以在本处下载。主要有以下部分：
     1 串口收发，上位机协议
     2 四元数算法，飞行器姿态解算
     3  GPIO的使用
     4  IIC总线，姿态传感器的使用
     5  PWM波的生成和调节
     6 定时器的使用
     7 外部中断以及与定时器配合捕获PWM波
     8 时钟设置，各个时钟分频，分配。
![image](https://github.com/yue435/flappy430/raw/master/images/code.jpg)

3 功能，效果。视频
目前可以进行飞行，效果见视频。
各种功能还说不是很完善，飞行也不是很稳定。代码的IIC使用软件IIC,容易扩展，板子上留有各种借口。您可以访问我们的淘宝网址获得这一硬件。


4 一起开发
目前还不是很完善，如果有获得代码的朋友进行了重要改进，可以把代码传给我们，我们将修正到github当中。谢谢~！

联系方式 ：flappy430@163.com
网址/获得硬件： http://shop112974196.taobao.com


--COPYRIGHT--
Flappy430-Copter by HHY 
 * Copyright (c) 2014, HHY,Flappy430 Team ，CHN
 * All rights reserved.
 * Can be used to study
 * shall not be used for any commercial purpose
 * thanks Alex，Holger Buss，gale，madwick and their codes
 * they give me much insperiation
   Function：This code IS created to control a  Four rotor aircraft 
              We use Texas Instruments' MSP430F5310 as MCU
              All circuits are integrated in a PCB board as large as 10*10 cm
             So it is a tiny  Four rotor aircraft， we call it "flappy430"
版权声明
Flappy430飞行器 by HHY
* Copyright (c) 2014, HHY,Flappy430 Team， CHN
* 我们保留一切权利
* 此代码仅仅可以用于学习
* 禁止用于任何商业目的


email：flappy430@163.com
website：http://shop112974196.taobao.com

2014 8 27



     







































 
 
            



