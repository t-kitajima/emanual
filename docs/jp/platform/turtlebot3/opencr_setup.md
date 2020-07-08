---
layout: archive
lang: jp
ref: opencr_setup
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/opencr_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 11
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 2"></div>

<!--[dummy Header 1]>
  <h1 id="setup"><a href="#setup">Setup</a></h1>
<![end dummy Header 1]-->

## [OpenCRのセットアップ](#opencr-setup)

![](/assets/images/platform/turtlebot3/software/remote_pc_and_turtlebot.png)

**注釈**：OpenCRの詳細を知りたい場合は、[OpenCR WiKi][opencr]にお問い合わせください
{: .notice--info}

### [TB3用のOpenCRファームウェアのアップロード](#opencr-firmware-upload-for-tb3)

{% capture notice_01 %}
**注釈**：ファームウェアのアップロード方法を1つ選択できます。 ただし、**シェルスクリプト**を使用することを強くお勧めします。 TurtleBot3のファームウェアを変更する必要がある場合は、2番目の方法を使用できます。
- 方法＃1：[**シェルスクリプト**](＃shell-script)、シェルスクリプトを使用してビルド済みのバイナリファイルをアップロードします。
- 方法＃2：[**Arduino IDE**](＃arduino-ide)、提供されたソースコードをビルドし、Arduino IDEを使用して生成されたバイナリファイルをアップロードします。
{% endcapture %}

<div class="notice--info">{{ notice_01 | markdownify }}</div>

#### [シェルスクリプト(推奨)](#recommended-shell-script)

この指示は、`Ubuntu 16.04`、`Ubuntu Mate`、`Linux Mint`、`Raspbian`でテストされました。 OpenCRをリモートPC（デスクトップまたはラップトップPC）に接続後、次のコマンドを使用するか、OpenCRをTurtleBot PC（`Intel®Joule™`、`Raspberry Pi 3`）に接続して次のコマンドを実行できます。

- TurtleBot3 Burger

  ``` bash
  $ export OPENCR_PORT=/dev/ttyACM0
  $ export OPENCR_MODEL=burger
  $ rm -rf ./opencr_update.tar.bz2
  $ wget https://github.com/ROBOTIS-GIT/OpenCR-Binaries/raw/master/turtlebot3/ROS1/latest/opencr_update.tar.bz2 && tar -xvf opencr_update.tar.bz2 && cd ./opencr_update && ./update.sh $OPENCR_PORT $OPENCR_MODEL.opencr && cd ..
  ```

  ![](/assets/images/platform/turtlebot3/opencr/shell01.png)

ファームウェアのアップロードが成功した場合、ターミナルに`jump_to_fw`の文字が表示されます。

- TurtleBot3 Waffle or Waffle Pi

  ``` bash
  $ export OPENCR_PORT=/dev/ttyACM0
  $ export OPENCR_MODEL=waffle
  $ rm -rf ./opencr_update.tar.bz2
  $ wget https://github.com/ROBOTIS-GIT/OpenCR-Binaries/raw/master/turtlebot3/ROS1/latest/opencr_update.tar.bz2 && tar -xvf opencr_update.tar.bz2 && cd ./opencr_update && ./update.sh $OPENCR_PORT $OPENCR_MODEL.opencr && cd ..
  ```

  ![](/assets/images/platform/turtlebot3/opencr/shell02.png)

ファームウェアのアップロードが成功した場合、ターミナルに`jump_to_fw`の文字が表示されます。

#### [Arduino IDE(代替) ](#alternative-arduino-ide)

**警告**: この章の内容は、TurtleBot3を制御する`リモートPC`（デスクトップまたはラップトップPC）に対応しています。 この手順をTurtleBot3に**適用しない**でください。
{: .notice--warning}

この手順を実施する前に、リモートPCでArduino IDEのセットアップを行ってください。

  - [OpenCRのためのArduino IDEのインストール][install_arduino_ide_for_opencr]

TurtleBot3のOpenCRファームウェアは、DYNAMIXELの制御、またはセンサーのデータを取得して送信するタスクを実行します。ファームウェアは、ボードマネージャーのOpenCRの例にあります。

TurtleBot3 Burgerの場合

**[リモートPC]** `ファイル` → `例` → `turtlebot3` → `turtlebot3_burger` → `turtlebot3_core`を選択します。

TurtleBot3 Waffleまたは、Waffle Piの場合

**[リモートPC]** `ファイル` → `例` → `turtlebot3` → `turtlebot3_waffle` → `turtlebot3_core`を選択します。

![](/assets/images/platform/turtlebot3/opencr/o1.png)

**[リモートPC]** `Upload`ボタンを選択し、OpenCRへファームウェアをアップロードします。

![](/assets/images/platform/turtlebot3/opencr/o2.png)

![](/assets/images/platform/turtlebot3/opencr/o3.png)

**注釈**: ファームウェアのアップロード中にエラーが発生した場合は、`ツール` → `ポート`に移動し、正しいポートが選択されているかどうかを確認します。 OpenCRの`リセット`ボタンを押して、ファームウェアのアップロードを再試行してください。
{: .notice--info}
  
**[リモートPC]** ファームウェアのアップロードが完了した場合、`jump_to_fw`の文字が表示されます。

### [基本的な操作](#basic-operation)

![](/assets/images/platform/turtlebot3/opencr/opencr_models.png)

`PUSH SW 1`および` PUSH SW 2`ボタンを使用して、ロボットが正しく組み立てられているかどうかを確認できます。 このプロセスでは、左右のDYNAMIXELとOpenCRボードをテストします。

1. TurtleBot3の組み立て後、バッテリーをOpenCRに接続し電源スイッチをオンにします。 OpenCRの`電源LED`が点灯しているのがわかります。
2. ロボットを床に置きます。 テストでは、1メートル（約40 インチ）の安全半径が推奨されます。
3. `PUSH SW 1`を数秒間押し続けて、ロボットに30センチメートル（約12 インチ）前進するように命令します。
4. `PUSH SW 2`を数秒間押し続けて、ロボットに所定の位置で180度回転するように命令します。

[opencr]: /docs/en/parts/controller/opencr10/
[install_arduino_ide_for_opencr]: /docs/en/parts/controller/opencr10/#arduino-ide
