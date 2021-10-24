# FreeRtos配置过程
参考资料*FreeRTOS内核实现与应用开发指南*
### 1，下载源码
官网地址：https://www.freertos.org 选择V9.0.0版本
主要需要的代码在Source/portable文件夹里
### 2，提取FreeRTOS最简源码
* 首先在裸机工程模板根目录下下新建``FreeRTOS``文件夹，并在此文件夹下新建``src``与``port``文件夹
* 将``FreeRTOSv9.0.0\FreeRTOS\Source\potable``下的``MemMang``与``RVDS``俩文件夹复制到工程中的port文件夹中
* 将``FreeRTOSv9.0.0\FreeRTOS\Source``目录下的所有c文件复制到工程的``src``文件夹
* 将``FreeRTOSv9.0.0\ FreeRTOS\Source``目录下的``include``文件复制到工程``FreeRTOS``文件夹下，该文件主要提供需要用到的头文件
* 将FreeRTOSv9.0.0\FreeRTOS\Demo\CORTEX_STM32F103_Keil下的FreeRTOSConfig.h文件复制到工程user文件夹下
### 3，添加 FreeRTOS 源码到工程组文件夹
* 在开发环境里面新建 ``FreeRTOS/src`` 和 ``FreeRTOS/port`` 两个组文件夹
* ``FreeRTOS/src`` 用于存放`` src`` 文件夹的内容
* ``FreeRTOS/port`` 用于存放 ``port\MemMang`` 文件夹与 ``port\RVDS\ARM_CM4``文件夹的内容，
* 在 ``FreeRTOS/port`` 分组中添加 ``MemMang`` 文件夹中的heap_4.c文件与``RVDS\ARM_CM4``（F407芯片）中的``port.c``文件
* 在 ``user`` 分组中添加我们 FreeRTOS 的配置文件``FreeRTOSConfig.h``
  最终效果
  ![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v2d4e9d95808e947108d6b863b46c08c0f.png)
**最后要在软件中指定头文件路径**
### 4修改FreeRTOSConfig.h
官方下载的代码与书本的代码有矛盾之处，会出现很多奇奇怪怪的错误，我感觉直接参考天穹飞控的配置比较好，毕竟人家经过了实践考验。初学也没什么必要去特殊配置该文件。
### 5修改 stm32f10x_it.c
该文件夹主要实现时钟的作用，会与``port.c``文件冲突。
主要修改的点是屏蔽``PendSV_Handler()``与 ``SVC_Handler()``两个函数。
**在实践中发现该文件中的``SysTick_Handler()``函数会报重定义的错误，需要把该函数屏蔽才行，不知道为什么书里没提及。**(天穹飞控的代码也把这一函数屏蔽处理)
### 6修改main.c文件
main.c 文件函数的配置也是参考天穹飞控，要增加空闲钩子函数等函数，需要添加的函数与``FreeRTOSConfig.h``中的配置有关，如果.h文件中有选择，而在``main.c``中没添加相应函数会出现报错。
### 这样一个最小的RTOS工程就配置完毕