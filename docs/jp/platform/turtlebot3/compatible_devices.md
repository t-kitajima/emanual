---
layout: archive
lang: jp
ref: compatible_devices
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/compatible_devices/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 13
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 4"></div>

<!--[dummy Header 1]>
  <h1 id="setup"><a href="#setup">Setup</a></h1>
<![end dummy Header 1]-->

## [対応デバイス](#compatible-devices)

- 基本構成に含まれているコンピュータとセンサの代わりに他の製品を使用したい場合は、このページを参照してください。

### [コンピュータ]](#computer)

- TurtleBot3のメインコンピュータは、 `Raspberry Pi 3`（TurtleBot3 BurgerとWaffle Pi）と`Intel Joule 570x`（TurtleBot3 Waffle）です。 これらのSBC（シングルボードコンピュータ）は、TurtleBot3の基本機能を使用するには十分ですが、ユーザはCPUパフォーマンスを向上させるか、GPUを使用するか、他の目的でRAMサイズを追加する必要があります。 この章では、SBCを交換する方法について説明します。

- 次の図に示すように、SBCには様々なタイプがあります。 各SBCの仕様は異なります。 ただし、使用するSBCにLinuxとROSをインストールできる場合は、そのSBCをTurtleBot3のメインコンピューターとして使用できます。 SBCに加えて、[Intel NUC][intel_nuc]、ミニPC、小型ノートブックも利用できます。

![](/assets/images/platform/turtlebot3/setup/sbcs.png)

- TurtleBot3開発チームは、いくつかのSBCをテストしました。 テストしたSBCのリストは次のとおりです:
  - [Raspberry Pi 3][raspberry_pi_3]
  - [Intel Joule 570x][intel_joule_570x]
  - [DragonBoard 410c][dragonboard_410c]
  - [NVIDIA Jetson TX2][nvidia_Jetson_tx2]
  - [UP Board][up_board]
  - [UP Core][up_core]
  - [LattePanda][lattepanda]
  - [ODROID-XU4][odroid_xu4]

#### ハードウェアアセンブリ

- TurtleBot3に組み込まれている`PCB support`を使用すると、ほとんどのSBCを問題なく組み立てることができます。 参考までに、PCB support（[リンク](http://www.robotis-shop-en.com/?act=shop_en.goods_view&GS=3284&GC=GD070003)）などの追加パーツを購入し、Onshapeで共有されている[ファイル](http://www.robotis.com/service/download.php?no=676)をダウンロードし、3Dプリンターを使用して印刷します。

![](/assets/images/platform/turtlebot3/setup/pcb_support.png)

- 次の図に示すように、使用するSBCの固定穴のPCB supportを使用して、SBCをTurtleBot3のWaffleプレートに固定できます。

![](/assets/images/platform/turtlebot3/setup/pcb_support_and_sbc.png)

#### 電源供給

- SBCのハードウェアアセンブリは単純ですが、電源は単純ではありません。 使用するコンピュータの`電源ケーブル`に合わせて、既存の電源ケーブルを変更するか、新しい電源ケーブルを作成する必要があります。

- TurtleBot3の基本パーツとして、以下の`電源ケーブル`が付属しています。 左の図はRaspberry Pi用、右の図はIntel Joule 570x用です。 電源ケーブルは、使用しているコンピュータの電源仕様に合わせて作成する必要があります。 [OpenCR][open_cr]には、SBCで一般的に使用されている5V（4A）電力と12V（1A）電力の両方があります。

![](/assets/images/platform/turtlebot3/setup/power_cable.png)

- SBCの電源は、下記の[OpenCR][open_cr]ピンマップの左側にある3つのコネクタです。

![](/assets/images/parts/controller/opencr10/opencr_pinout.png)

### [センサ](#sensors)

- `TurtleBot3 Burger`は、研究開発に強化された[360°LiDAR][lds]、[9軸慣性測定ユニット][imu]、[精密エンコーダ][dynamixel]を使用します。 `TurtleBot3 Waffle`も同様の360°LiDARを搭載していますが、さらに認識SDKを備えた強力な[Intel®RealSense™][realsense]も提案しています。 `TurtleBot3 Waffle Pi`は、使用率の高い[Raspberry Pi Camera][raspi_cam]を使用しています。 これは、移動ロボットを作るための最良のハードウェアソリューションになります。

- 追加センサを使用する場合は、センサをロボットに取り付けて使用できます。 ROSは、前述のセンサのドライバとライブラリを使用できる開発環境を提供します。 すべてのセンサがROSパッケージでサポートされているわけではありませんが、センサ関連のパッケージが増加しています。

![](/assets/images/platform/turtlebot3/setup/sensors.png)

- 新しいセンサを探している場合は、ROS Wikiの[センサページ][sensors]を確認し必要なセンサーと関連するROSパッケージを見つけてください。

- 組み込みボードに接続されたアナログセンサを使用する場合は、OpenCRで使用できます。 USBまたはイーサネット通信以外のアナログセンサを使用する必要がある場合は、[追加センサー][additional_sensors]ページを参照してください。

[raspberry_pi_3]: https://www.raspberrypi.org/products/
[intel_joule_570x]: https://ark.intel.com/products/96414/Intel-Joule-570x-Developer-Kit
[dragonboard_410c]: https://developer.qualcomm.com/hardware/dragonboard-410c
[nvidia_Jetson_tx2]: https://developer.nvidia.com/embedded/buy/jetson-tx2-devkit
[up_board]: http://www.up-board.org/up/
[up_core]: http://www.up-board.org/upcore/
[lattepanda]: https://www.lattepanda.com/
[odroid_xu4]: http://www.hardkernel.com/
[intel_nuc]: https://www.intel.com/content/www/us/en/products/boards-kits/nuc.html

[open_cr]: /docs/en/parts/controller/opencr10/
[lds]: /docs/en/platform/turtlebot3/appendix_lds_01/
[imu]: /docs/en/platform/turtlebot3/appendix_opencr1_0/#specifications
[dynamixel]: /docs/en/platform/turtlebot3/appendix_dynamixel/
[realsense]: /docs/en/platform/turtlebot3/appendix_realsense/
[raspi_cam]: /docs/en/platform/turtlebot3/appendix_raspi_cam/
[sensors]: http://wiki.ros.org/Sensors
[additional_sensors]: /docs/en/platform/turtlebot3/additional_sensors/
