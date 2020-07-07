---
layout: archive
lang: jp
ref: joule_setup
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/joule_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 10
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 2"></div>
<div style="counter-reset: h3 1"></div>

<!--[dummy Header 1]>
  <h1 id="setup"><a href="#setup">Setup</a></h1>
  <h2 id="sbc-setup"><a href="#sbc-setup">SBC Setup</a></h2>
<![end dummy Header 1]-->

### [Joule セットアップ](#joule-setup)

**警告**: セットアップ作業には、電源と時間が必要です。そのため、バッテリーは適していません。この作業では、SMPS(ACアダプタ)の使用をお勧めします。
{: .notice--warning}

#### [Linux(Ubuntu) インストール](#install-linux-ubuntu)

このセクションでは、Alternative Ubuntu Desktop 16.04 LTSがIntel®Joule™にインストールされます。

**[リモートPC]** 以下のリンクから`Alternative Ubuntu 16.04 for Intel® Joule™`をダウンロードします。

- [Ubuntu 16.04 for Intel® Joule™ ダウンロード](http://people.canonical.com/~platform/snappy/tuchuck/desktop-final/tuchuck-xenial-desktop-iso-20170317-0.iso)

**[リモートPC]** 起動可能なインストールUSBドライブを作成するには、以下のリンクから[Alternative install(Ubuntu Desktop 16.04 LTS)][alternative-installubuntu-desktop-1604-lts]セクションに従ってください。

- [起動可能なインストールUSBドライブを作成する](https://developer.ubuntu.com/core/get-started/intel-joule)

**[リモートPC]** 始める前に、Ubuntu ImageをインストールするにはボードのBIOSを[BIOSバージョン＃193][bios-version-193]に更新する必要があります。 [BIOSバージョン＃193][bios-version-193]をダウンロードし、下記リンクの指示に従いBIOSをJouleにフラッシュします。

- [BIOSのアップデート](https://software.intel.com/en-us/flashing-the-bios-on-joule)

**警告**: 最新のBIOS（1J2以降）に更新すると、Ubuntu 16.04 LTSで`Intel®Joule™`の予期しない問題が発生する可能性があります。 推奨される[BIOSバージョン＃193][bios-version-193]のみを使用してください。
{: .notice--warning}

**警告**: `Intel®Joule™`は、パッケージに`パッシブヒートシンク`が付属しています。 ヒートシンクの使用をお勧めします。 ヒートシンクなしでJouleを操作するには、追加の[説明](https://software.intel.com/en-us/node/721471)に従ってください。
{: .notice--warning}

[bios-version-193]: https://downloadmirror.intel.com/26206/eng/joule-firmware-2017-02-19-193-public.zip
[alternative-installubuntu-desktop-1604-lts]: https://developer.ubuntu.com/core/get-started/intel-joule#alternative-install:-ubuntu-desktop-16.04-lts


次のインストール手順が必要な場合は、以下のリンクを参照してください。

  - [ステップバイステップ Ubuntuのインストール][step_by_step_to_install_ubuntu_on_joule]{: .popup}

#### [ROSインストール](#install-ros)

**警告**: この章の内容は、**TurtleBot3 Waffle**のメインコンピューターとなるIntel®Joule™に対応しています。 この指示をリモートPC（デスクトップPCまたはラップトップ）に**適用しないでください。**
{: .notice--warning}

**注釈**: この手順でTurtleBot3のROS関連パッケージをインストールするには約2時間かかります。 経過時間はネットワーク環境によって異なります。
{: .notice--info}

![](/assets/images/platform/turtlebot3/logo_ros.png)

**ヒント**: 端末アプリケーションは、画面の左上隅にあるUbuntu検索アイコンで見つけることができます。 端末のショートカットキーはCtrl-Alt-Tです。
{: .notice--info}

**[TurtleBot]** ROSのインストール

``` bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh && chmod 755 ./install_ros_kinetic.sh && bash ./install_ros_kinetic.sh
```

**注釈**: インストールされているパッケージを確認するには、このリンクを確認してください。[install_ros_kinetic](https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh)
{: .notice--info}

**注釈**: ROSのインストール後、Intel®Joule™を再起動してください。
{: .notice--info}

マニュアルインストールの場合は、下記のリンクを参照してください。

- [Install ROS on Ubuntu](http://wiki.ros.org/kinetic/Installation/Ubuntu)

#### [依存パッケージのインストール](#install-dependent-packages)

TurtleBot3を制御するための依存パッケージのインストールする手順です。

**[TurtleBot]** GitHubからパッケージをダウンロードします。

``` bash
$ cd ~/catkin_ws/src
$ git clone https://github.com/ROBOTIS-GIT/hls_lfcd_lds_driver.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
```

**注釈**: Intel®RealSense™を使用する場合は、[Intel® RealSense™](http://emanual.robotis.com/docs/en/platform/turtlebot3/appendix_realsense/#realsense)の関連付録を確認してください

{: .notice--info}

**[TurtleBot]** TurtleBot SBCに必要の無いパッケージを削除します。

``` bash
$ cd ~/catkin_ws/src/turtlebot3
$ sudo rm -r turtlebot3_description/ turtlebot3_teleop/ turtlebot3_navigation/ turtlebot3_slam/ turtlebot3_example/
```

**[TurtleBot]** 依存パッケージのインストールします。

``` bash
$ sudo apt-get install ros-kinetic-rosserial-python ros-kinetic-tf
```

**注釈**: パッケージのインストール後、Intel®Joule™を再起動してください。
{: .notice--info}

**[TurtleBot]** パッケージをビルドします。

``` bash
$ cd ~/catkin_ws && catkin_make
```

`catkin_make`コマンドがエラー無しで完了した場合、TurtleBot3の準備は完了です。

#### [USBの設定](#usb-settings)

**[TurtleBot]** 次のコマンドを使用すると、ルート権限を取得せずにOpenCRのUSBポートを使用できます。

``` bash
$ rosrun turtlebot3_bringup create_udev_rules
```

#### [ネットワーク設定](#network-configuration)

![](/assets/images/platform/turtlebot3/software/network_configuration.png)

ROSでは、TurtleBot3とリモートPCの間で通信をするためにIPアドレスが必要です。 リモートPCとTurtleBot3は、同じwifiルーターに接続する必要があります。

TurtleBot3のターミナルウィンドウで次のコマンドを入力し、TurtleBot3のIPアドレスを確認します。

``` bash
$ ifconfig
```

長方形の赤い枠で囲っている文字列が、`TurtleBot`です。

![](/assets/images/platform/turtlebot3/software/network_configuration4.png)

下記のコマンドを入力します。

``` bash
$ nano ~/.bashrc
```

`Alt + /`を入力するとファイルの最終行へ移動します。

ROS_MASTER_URIアドレスの`localhost`を、[リモートPCネットワーク構成](http://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/#network-configuration)から取得したIPアドレスに置き換えます。 また、`ROS_HOSTNAME`アドレスの `localhost`を、上記のターミナルウィンドウから取得したIPアドレス（TurtleBot3のIPアドレス）に置き換えます。

![](/assets/images/platform/turtlebot3/software/network_configuration5.png)

次に、以下のコマンドでbashrcを実行します。

``` bash
$ source ~/.bashrc
```

[ros]: http://wiki.ros.org
[step_by_step_to_install_ubuntu_on_joule]: /docs/en/platform/turtlebot3/step_by_step_to_install_ubuntu_on_joule
