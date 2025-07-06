# VR项目展示

## 项目演示

<p align="center">
  <img src="videos/2.gif" alt="项目演示1" width="800" height="auto"/>
</p>

<p align="center">
  <img src="videos/5.gif" alt="项目演示2" width="800" height="auto"/>
</p>

---

# 项目结构

## 1. 头部追踪模块

<div align="center">
  <img src="images/头显.jpg" alt="VR头显" width="550"/>
  <p style="font-size: 18px;"><strong>VR头显</strong></p>
</div>

### 技术原理

<div style="font-size: 16px;">
<p>以Arduino Micro开发板作为头部追踪核心，使用I2C接口与MPU9250传感器实现连接，实时采集三轴上的加速度、角速度和磁力计数据。板载USB-HID协议栈直接实现跟PC的通信连接，摆脱外部串口芯片，硬件设计实现精简。</p>

<p>系统采用优化后的Madgwick算法运行，按512Hz采样率对多源传感数据进行融合，以120Hz频率更新输出归一化四元数，采用定制的HID报告描述符传递到SteamVR驱动，达成存在毫秒级延迟的虚拟头部运动追踪。</p>
</div>

### 硬件组件

<!-- 使用HTML表格实现图片并列 -->
<table>
  <tr>
    <td align="center" width="50%">
      <img src="images/Arduino_Micro.png" alt="Arduino Micro开发板" width="320"/>
      <p style="font-size: 16px;"><strong>Arduino Micro</strong></p>
    </td>
    <td align="center" width="50%">
      <img src="images/mpu9250.png" alt="MPU9250传感器" width="320"/>
      <p style="font-size: 16px;"><strong>MPU9250传感器</strong></p>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="images/屏幕.jpg" alt="VR屏幕" width="320"/>
      <p style="font-size: 16px;"><strong>VR屏幕</strong></p>
    </td>
    <td align="center" width="50%">
      <img src="images/屏幕驱动板.jpg" alt="屏幕驱动板" width="320"/>
      <p style="font-size: 16px;"><strong>屏幕驱动板</strong></p>
    </td>
  </tr>
</table>

---

## 2. 手部追踪模块

<div align="center">
  <img src="images/手套.jpg" alt="VR手套" width="550"/>
  <p style="font-size: 18px;"><strong>VR手套</strong></p>
</div>

### 技术原理

<div style="font-size: 16px;">
<p>Arduino Nano开发板借助模拟输入引脚获取WH148电位器的弯曲信号，经USB串口以有线渠道传输到PC端，实现基本的手部动作捕捉效果。</p>

<p>为增进灵活性，系统升级采用ESP32开发板开展，凭借蓝牙低功耗（BLE）协议实现无线的数据传送，维持相同传感器接口的同时对穿戴舒适性进行优化。手部追踪模块可采用有线和无线双模式，用户可依照需求去选择连接方式，兼顾了低成本与高自由度的场景情形。</p>
</div>

### 硬件组件

<!-- 使用HTML表格实现图片并列 -->
<table>
  <tr>
    <td align="center" width="50%">
      <img src="images/Arduino_nano.png" alt="Arduino Nano开发板" width="320"/>
      <p style="font-size: 16px;"><strong>Arduino Nano</strong></p>
    </td>
    <td align="center" width="50%">
      <img src="images/esp32.jpg" alt="ESP32开发板" width="320"/>
      <p style="font-size: 16px;"><strong>ESP32开发板</strong></p>
    </td>
  </tr>
</table>

<div align="center" style="margin: 15px;">
  <img src="images/电位器.png" alt="WH148电位器" width="320"/>
  <p style="font-size: 16px;"><strong>WH148电位器</strong></p>
</div>

---

## 3. 肢体追踪模块

<div align="center">
  <img src="images/肢体追踪.jpg" alt="肢体追踪模块" width="550"/>
  <p style="font-size: 18px;"><strong>肢体追踪模块</strong></p>
</div>

### 技术原理

<div style="font-size: 16px;">
<p>NodeMCU（ESP8266）开发板借助I2C接口与BNO085传感器相连，读取其内置的传感器融合算法输出的已校准四元数数据，还借助Wi-Fi模块把数据无线传送到PC端。</p>

<p>每个NodeMCU节点独立承担左右大臂、小臂和手腕的动作捕捉相关工作，适配多节点同步通信需求，顺应上半身追踪需求。</p>
</div>

### 硬件组件

<!-- 使用HTML表格实现图片并列 -->
<table>
  <tr>
    <td align="center" width="50%">
      <img src="images/esp8266.jpg" alt="ESP8266开发板" width="320"/>
      <p style="font-size: 16px;"><strong>ESP8266开发板</strong></p>
    </td>
    <td align="center" width="50%">
      <img src="images/bno085.png" alt="BNO085传感器" width="320"/>
      <p style="font-size: 16px;"><strong>BNO085传感器</strong></p>
    </td>
  </tr>
</table>