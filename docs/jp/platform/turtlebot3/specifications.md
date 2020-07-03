---
layout: archive
lang: jp
ref: specifications
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/specifications/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 4
---

<div style="counter-reset: h1 3"></div>

# [仕様](#specifications)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_models.png)

## [ハードウェア仕様](#hardware-specifications)

| 項目                              | Burger                                                              | Waffle （製造中止）                                               | Waffle Pi                                                           |
|:-----------------------------------|:--------------------------------------------------------------------|:--------------------------------------------------------------------|:--------------------------------------------------------------------|
| 最大並進速度     | 0.22 m/s                                                            | 0.26 m/s                                                            | 0.26 m/s                                                            |
| 最大回転速度        | 2.84 rad/s (162.72 deg/s)                                           | 1.82 rad/s (104.27 deg/s)                                           | 1.82 rad/s (104.27 deg/s)                                           |
| ペイロード                    | 15kg                                                                | 30kg                                                                | 30kg                                                                |
| サイズ （長さ x 幅 x 高さ）                   | 138mm x 178mm x 192mm                                               | 281mm x 306mm x 141mm                                               | 281mm x 306mm x 141mm                                               |
| 重量（+ SBC + バッテリー + センサ） | 1kg                                                                 | 1.8kg                                                               | 1.8kg                                                               |
| 乗り越え可能な段差の高さ              | 10mmもしくはそれより低い                                                       | 10mmもしくはそれより低い                                                      | 10mmもしくはそれより低い                                                      |
| 動作時間            | 2時間 30分                                                              | 2時間                                                                  | 2時間                                                                  |
| 充電時間             | 2時間 30分                                                              | 2時間 30分                                                              | 2時間 30分                                                              |
| SBC（シングルボードコンピュータ）       | Raspberry Pi 3 Model B and B+                                       | Intel® Joule™ 570x                                                  | Raspberry Pi 3 Model B and B+                                       |
| MCU                                | 32-bit ARM Cortex®-M7 with FPU (216 MHz, 462 DMIPS)                 | 32-bit ARM Cortex®-M7 with FPU (216 MHz, 462 DMIPS)                 | 32-bit ARM Cortex®-M7 with FPU (216 MHz, 462 DMIPS)                 |
| リモートコントローラ                  | -                                                                   | -                                                                   | RC-100B + BT-410 Set (Bluetooth 4, BLE)                             |
| アクチュエータ                           | XL430-W250                                                          | XM430-W210                                                          | XM430-W210                                                          |
| LDS（2D距離センサ）         | 360 Laser Distance Sensor LDS-01                                    | 360 Laser Distance Sensor LDS-01                                    | 360 Laser Distance Sensor LDS-01                                    |
| カメラ                             | -                                                                   | Intel® Realsense™ R200                                              | Raspberry Pi Camera Module v2.1                                     |
| IMU（慣性計測装置）                                | 3軸ジャイロセンサ<br />3軸加速度センサ<br />3軸磁気センサ | 3軸ジャイロセンサ<br />3軸加速度センサ<br />3軸磁気センサ | 3軸ジャイロセンサ<br />3軸加速度センサ<br />3軸磁気センサ |
| 電源コネクタ                   | 3.3V / 800mA<br />5V / 4A<br />12V / 1A                             | 3.3V / 800mA<br />5V / 4A<br />12V / 1A                             | 3.3V / 800mA<br />5V / 4A<br />12V / 1A                             |
| 拡張ピン                    | GPIO 18ピン<br />Arduino 32ピン                                    | GPIO 18ピン<br />Arduino 32ピン                                    | GPIO 18ピン<br />Arduino 32ピン                                    |
| 周辺機器                         | UART x3, CAN x1, SPI x1, I2C x1, ADC x5, 5pin OLLO x4               | UART x3, CAN x1, SPI x1, I2C x1, ADC x5, 5pin OLLO x4               | UART x3, CAN x1, SPI x1, I2C x1, ADC x5, 5pin OLLO x4               |
| DYNAMIXELポート                    | RS485 x 3, TTL x 3                                                  | RS485 x 3, TTL x 3                                                  | RS485 x 3, TTL x 3                                                  |
| オーディオ                              | いくつかのプログラマブルなビープシークエンス                                 | いくつかのプログラマブルなビープシークエンス                                 | いくつかのプログラマブルなビープシークエンス                                 |
| プログラマブルLED                  | ユーザLED x 4                                                        | ユーザLED x 4                                                        | ユーザLED x 4                                                        |
| ステータスLED                        | ボードステータスLED x 1<br />Arduino LED x 1<br />パワーLED x 1        | ボードステータスLED x 1<br />Arduino LED x 1<br />パワーLED x 1        | ボードステータスLED x 1<br />Arduino LED x 1<br />パワーLED x 1        |
| ボタンとスイッチ               | プッシュボタン x 2, リセットボタン x 1, ディップスイッチ x 2                  | プッシュボタン x 2, リセットボタン x 1, ディップスイッチ x 2                  | プッシュボタン x 2, リセットボタン x 1, ディップスイッチ x 2                  |
| バッテリー                            | リチウムポリマー 11.1V 1800mAh / 19.98Wh 5C                          | リチウムポリマー 11.1V 1800mAh / 19.98Wh 5C                          | リチウムポリマー 11.1V 1800mAh / 19.98Wh 5C                          |
| PC接続                      | USB                                                                 | USB                                                                 | USB                                                                 |
| ファームウェアアップデート                   | USB経由 /  JTAG経由                                                  | USB経由 /  JTAG経由                                                  | USB経由 /  JTAG経由                                                  |
| 電源アダプタ(SMPS)               | 入力 : 100-240V, AC 50/60Hz, 1.5A @max<br />出力 : 12V DC, 5A    | 入力 : 100-240V, AC 50/60Hz, 1.5A @max<br />出力 : 12V DC, 5A    | 入力 : 100-240V, AC 50/60Hz, 1.5A @max<br />出力 : 12V DC, 5A    |

## [寸法と重量](#dimension-and-mass)

### [TurtleBot3 Burgerのデータ](#data-of-turtlebot3-burger)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_dimension1.png)

### [TurtleBot3 Waffleのデータ](#data-of-turtlebot3-waffle)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_dimension2.png)

### [TurtleBot3 Waffle Piのデータ](#data-of-turtlebot3-waffle-pi)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_dimension3.png)

## [コンポーネント](#components)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_burger_components.png)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_waffle_components.png)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_waffle_pi_components.png)

### [SBC（シングルボードコンピュータ）](#sbcs)

- [Raspberry Pi 3 Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
  - TurtleBot3 Burger, Waffle Pi
- [Raspberry Pi 3 Model B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)
  - TurtleBot3 Burger, Waffle Pi （2019年に出荷された商品から適用）
- [Intel® Joule™ 570x](http://ark.intel.com/products/96414/Intel-Joule-570x-Developer-Kit)
  - TurtleBot3 Waffle

### [センサ](#sensors)

- [360レーザ距離センサLDS-01](/docs/en/platform/turtlebot3/appendix_lds_01/)
  - TurtleBot3 Burger, Waffle, Waffle Pi
- [Intel® Realsense™ R200](https://software.intel.com/en-us/RealSense/R200Camera)
  - TurtleBot3 Waffle
- [The Raspberry Pi Camera Module v2.1](https://www.raspberrypi.org/products/camera-module-v2/)
  - TurtleBot3 Waffle Pi

### [組込みボード](#Embedded-board)

- [OpenCR1.0](/docs/en/platform/turtlebot3/appendix_opencr1_0/)
  - TurtleBot3 Burger, Waffle, Waffle Pi

### [アクチュエータ](#actuators)

- [XL430](/docs/en/dxl/x/xl430-w250/)
  - TurtleBot3 Burger
- [XM430](/docs/en/dxl/x/xm430-w210/)
  - TurtleBot3 Waffle, Waffle Pi
