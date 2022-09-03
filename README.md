# FreeSound项目

本项目是我一次小的尝试，使用了扩音锥，360度发声音箱。使用D类功放和DSP，小体积大能量

**项目完全开源、任何人都可以根据本Github内容进行白嫖，也可以顺手点个Star**

## 介绍

本项目使用了威发的2.5寸全频喇叭，TPA3118 D类功放，ADAU1701 DSP，QCC5125。整体大小为8.3*15.3CM

项目成本<500RMB（自有3D打印机）

### 视频介绍：[https://www.bilibili.com/video/BV1xe4y1h7ed/?vd_source=25617b52e7e0b6d56790cc1bea5b5be1](https://www.bilibili.com/video/BV1xe4y1h7ed/?vd_source=25617b52e7e0b6d56790cc1bea5b5be1)
![Image](https://github.com/ZhaJiHu/FreeSound/blob/main/4.Doc/Pic/%E8%93%9D%E5%85%89.PNG)
## 资料说明

- 3D模型设计文件
- 电源模块、音频模块、触摸模块硬件工程
- DSP程序文件和ESP32 BIN文件
- 各类文档和图片
- STL打印文件

## 结构设计

采用全向扩音锥设计，360度发声。为了提高低音，采用两个2寸对称式被动振膜。采用了大量3D打印件，打印的时候可调高填充率，震动会少点，emm，为了避免漏气的问题，最好补上热熔胶。顶部为了透光性，使用了透明的3M胶，给每个LED都单独设计了一个隔光栅格。

- 提供了一份完整的step设计文件

## 电路模块

### 电源模块：

- 电池使用2S锂电，使用TP5100充电模块，TYPE-C引电采用CH224K，默认引12V电
- 使用一颗ESP32，主要处理触摸输入，蓝牙输入，开关机，未来还可以与DSP通信，在线调音

### 音频模块

- 使用TPA3118 D类功放，7.4V供电
- 使用ADI ADAU1701 DSP IC，可使用USBi进行在线调参，也可以下载到EEPROM自启动
- 蓝牙采用QCC5125模块，输出I2S音频信号
- 使用SRC4192IDB间接输出MCLK给到DSP
- 使用FPC 蓝牙天线

### 触摸模块

- 使用BS814A-1触摸模块，为了得到最大的感应厚度，没有焊接对地电容
- 使用28颗WS2812B-2020

## 固件说明

本次由于时间关系，还没有整理好代码，因此先提供esp32的bin文件。DSP使用的是图形化编程，工程文件已提供，需要自行下载SigmaStudio

## 打样说明

### 3D打印：

- 文件位于：/6.Process**/3D打印，**该文件为STL格式，数量都是为1

### PCB打样

- 可以使用github内的工程文件导出Gerber文件，也可以使用提供好的Gerber文件，文件位于：/6.Process**/**Gerber

### BOM

- 在整理