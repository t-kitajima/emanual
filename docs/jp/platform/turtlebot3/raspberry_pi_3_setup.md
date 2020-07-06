---
layout: archive
lang: jpパッケージ
ref: raspberry_pi_3_setup
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/raspberry_pi_3_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 9
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 2"></div>
<div style="counter-reset: h3 0"></div>

<!--[dummy Header 1]>
  <h1 id="setup"><a href="#setup">Setup</a></h1>
  <h2 id="sbc-setup"><a href="#sbc-setup">SBC Setup</a></h2>
<![end dummy Header 1]-->

### [Raspberry Pi 3 セットアップ](#raspberry_pi_3_setup)

{% capture notice_01 %}
**警告**:
- この章の内容は、**TurtleBot3 BurgerとWaffle Pi**のメインコンピューターとなる `Raspberry Pi 3`に対応しています。 この指示をリモートPC（デスクトップPCまたは、ラップトップ）で**実施しないでください。**
- セットアップ作業には、電源と時間が必要です。そのため、バッテリーは適していません。この作業では、SMPS(ACアダプタ)の使用をお勧めします。
{% endcapture %}
<div class="notice--warning">{{ notice_01 | markdownify }}</div>


{% capture info_01 %}
**注釈**: Raspberry Pi 3にLinuxとROSをインストールする3つの方法のいずれかを使用します。
1. Ubuntu Mateのインストールについては、`Linuxのインストール（Ubuntu MATE）`ガイドをお読みください。 TurtleBotのSBCにLinuxイメージをインストールした後、ROSおよび依存パッケージを必ずインストールしてください。 TurtleBot3のROSおよび関連パッケージをインストールするのに、約1時間かかります。
2. RaspbianベースのLinuxディストリビューションイメージのインストールについては、`Linuxのインストール（Raspbian）`ガイドをお読みください。 ディストリビューションイメージにはTurtleBot3に関連するROSおよびROSパッケージが含まれているため、追加のインストールを行う必要はありません。  
3. webOS Robotics Platformについては、`webOS Robotics Platform`ガイドをご覧ください。 TurtleBot3でパッケージをコンパイルする必要はありません。 これらは、OpenEmbeddedを使用して、高性能PC、Ubuntu 18.04ベース、およびそれらから作成されたイメージファイルでクロスコンパイルされます。
{% endcapture %}
<div class="notice--info">{{ info_01 | markdownify }}</div>

{% capture info_02 %}
**注釈**: Raspberry Pi 3 B +はTurtleBot3 BurgerとWaffle Piで利用できます。 Raspberry Pi 3 B +をご利用の場合は、以下をご参照ください。
{% endcapture %}
<div class="notice--info">{{ info_02 | markdownify }}</div>

  1. [Linuxのインストール(Ubuntu MATE)][install_linux_ubuntu_mate]

  2. [Linuxのインストール(Raspbian)][install_linux_based_on_raspbian]

  3. [Linuxのインストール(webOS Robotics Platform)](https://github.com/ros/meta-ros/wiki/OpenEmbedded-Build-Instructions)


#### [Linuxのインストール(Ubuntu MATE)](#install-linux-ubuntu-mate)

##### [1) TurtleBot PCへUbuntu MATEのインストール](#1-install-ubuntu-mate-on-turtlebot-pc)

**警告**: `Ubuntu Mate`は現在`Raspberry Pi 3B+`に対応していません。 お持ちの場合は、代わりに`Raspbian`をインストールしてください。
{: .notice--warning}

**警告**: Raspberry Pi 3にLinux（Ubuntu MATE）をインストールするには、microSDカードに少なくとも**8GB**の空き容量が必要です。
{: .notice--warning}

**[リモートPC]** 以下のリンクからリモートPCにRaspberry Pi 3の`Ubuntu MATE 16.04`イメージをダウンロードします。

- [ダウンロードリンク](https://ubuntu-mate.org/raspberry-pi/ubuntu-mate-16.04.2-desktop-armhf-raspberry-pi.img.xz)

**[リモートPC]** Ubuntu MATEイメージをmicroSDに書き込むには、XZ圧縮イメージをネイティブでサポートする`GNOME Disks`と「ディスクイメージの復元...」オプションを使用することをお勧めします。

``` bash
$ sudo apt-get install gnome-disk-utility
```

<iframe width="640" height="480" src="https://www.youtube.com/embed/V_6GNyL6Dac" frameborder="0" allowfullscreen></iframe>

**ヒント**: `GNOME Disks`を使用することをお勧めしますが、Linuxの` ddrescue`などの他のアプリケーションも使用できます。
{: .notice--info}

``` bash
$ sudo apt-get install gddrescue xz-utils
$ unxz ubuntu-mate-16.04.2-desktop-armhf-raspberry-pi.img.xz
$ sudo ddrescue -D --force ubuntu-mate-16.04.2-desktop-armhf-raspberry-pi.img /dev/sdx
```

**ヒント**: `GNOME Disks`の使用をお勧めしますが、Windowsの` Win32 Disk Imager`などの他のアプリケーションも使用できます。 [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/)
{: .notice--info}

##### [2) TurtleBot PCへのROSインストール](#2-install-ros-on-turtlebot-pc)

![](/assets/images/platform/turtlebot3/logo_ros.png)

**注釈**: この手順でTurtleBot3のROSおよび関連パッケージをインストールするのに約1時間かかります。 経過時間はネットワーク環境によって異なります。
{: .notice--info}

**[TurtleBot]** 下記のスクリプトを使用すると、ROSのインストール手順を簡略化できます。
TurtleBot PCのターミナルウィンドウでこのスクリプトを実行します。ターミナルアプリケーションは、画面の左上隅にあるUbuntu検索アイコンから起動できます。もしくは、ターミナルのショートカットキー('Ctrl'-'Alt'-'t')を使用して起動できます。 ROSをインストールした後、TurtleBot PCを再起動してください。


``` bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic_rp3.sh && chmod 755 ./install_ros_kinetic_rp3.sh && bash ./install_ros_kinetic_rp3.sh
```

**注釈**: インストールされているパッケージを確認するには、このリンクを確認してください。 [install_ros_kinetic_rp3.sh](https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic_rp3.sh)
{: .notice--info}

マニュアルインストールの場合は、以下のリンクを参照してください。

- [ROS Kineticのマニュアルインストール](http://wiki.ros.org/kinetic/Installation/Ubuntu)

##### [3) TurtleBot PCへの依存パッケージのインストール](#3-install-dependent-packages-on-turtlebot-pc)

TurtleBot3を制御するための依存パッケージのインストールする手順です。

**[TurtleBot]** githubからパッケージをダウンロードします

``` bash
$ cd ~/catkin_ws/src
$ git clone https://github.com/ROBOTIS-GIT/hls_lfcd_lds_driver.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
```

**注釈**: Raspberry Pi Cameraを使用する場合は、関連する付録を確認してください。 [Raspberry Pi Camera][appendix_raspi_cam]
{: .notice--info}

**[TurtleBot]** TurtleBot PCに必要の無いパッケージを削除します。

``` bash、
$ cd ~/catkin_ws/src/turtlebot3
$ sudo rm -r turtlebot3_description/ turtlebot3_teleop/ turtlebot3_navigation/ turtlebot3_slam/ turtlebot3_example/
```

**[TurtleBot]** 依存パッケージのインストールをします。

``` bash
$ sudo apt-get install ros-kinetic-rosserial-python ros-kinetic-tf
```

**[TurtleBot]** パッケージのインストール後、Raspberry Pi 3を再起動してください。

**[TurtleBot]** パッケージをビルドします。

``` bash
$ source /opt/ros/kinetic/setup.bash
$ cd ~/catkin_ws && catkin_make -j1
```

`catkin_make`コマンドがエラー無しで完了した場合、TurtleBot3の準備は完了です。

##### [4) USB設定](#4-usb-settings)

**[TurtleBot]** 次のコマンドを使用すると、ルート権限を取得せずにOpenCRのUSBポートを使用できます。

``` bash
$ rosrun turtlebot3_bringup create_udev_rules
```

##### [5) ネットワーク設定](#5-network-configuration)

![](/assets/images/platform/turtlebot3/software/network_configuration.png)

ROSでは、TurtleBot PCとリモートPCの間で通信をするためにIPアドレスが必要です。 リモートPCとTurtleBot PCは、同じwifiルーターに接続する必要があります。

TurtleBot PCのターミナルウィンドウで次のコマンドを入力し、TurtleBot PCのIPアドレスを確認します。

``` bash
$ ifconfig
```

長方形の赤い枠で囲っている文字列が、`TurtleBot PC`です。

![](/assets/images/platform/turtlebot3/software/network_configuration4.png)

次のコマンドを入力します。

``` bash
$ nano ~/.bashrc
```

`Alt + /`を入力するとファイルの最終行へ移動します。

`ROS_MASTER_URI`アドレスの` localhost`を[リモートPCのネットワーク構成][network_configuration]から取得したリモートPCのIPアドレスに置き換えます。 また、`ROS_HOSTNAME`アドレスの`localhost`を、上記のターミナルウィンドウから取得したIPアドレスに置き換えます。これは、TurtleBot PCのIPアドレスです。

![](/assets/images/platform/turtlebot3/software/network_configuration5.png)

次に、以下のコマンドでbashrcを実行します。


``` bash
$ source ~/.bashrc
```

[ros]: http://wiki.ros.org

#### [RaspbianベースのLinuxをインストールする](#install-linux-based-on-raspbian)

**警告**: Raspberry Pi 3にLinuxをインストールするには、SDカードに少なくとも**8GB**の空き容量が必要です。
{: .notice--warning}

RaspbianベースのLinuxディストリビューションイメージを提供しています。 それらはTurtleBot3に関連するROSおよびROSパッケージと共にプリインストールされています。 TurtleBot3 BurgerおよびWaffle Piモデルをサポートしています。 このディストリビューションイメージでは、Wolfram、Mathematica、Minecraft Pi、Oracle Java SEなどの非フリーソフトウェアが削除されています。

##### リモートPC
- Raspbian for TurtleBot3に基づくLinuxディストリビューションイメージをダウンロードします。
  - [ダウンロードリンク](http://www.robotis.com/service/download.php?no=1738)
  - SHA256 (image_rpi_20190429.img.zip) : eb8173f3727db08087990b2c4e2bb211e70bd54644644834771fc8b971856b97
  - SHA256 (image_rpi_20190429.img): 7a868c275169b1f02c04617cc0cce9654fd8222623c78b22d0a27c73a9609398
- ダウンロード後、ダウンロードしたファイルを解凍します。
- SDカードのイメージを書き込み手順
  - [etcher.io](https://etcher.io/)にアクセスし、Etcher SDカードイメージユーティリティをダウンロードしてインストールします。
  - Etcherを実行し、コンピューターまたはラップトップにダウンロードしたLinuxイメージを選択します。
  - SDカードドライブを選択します。
  - 書き込みを選択して、イメージをSDカードに転送します。
- （他の書き込み方法）Linuxでは`dd`コマンドを使用できます。Windowsではアプリケーション`win32 Disk Imager`を使用できます。 完全な手順については、[こちら](https://elinux.org/RPi_Easy_SD_Card_Setup#Using_the_Linux_command_line)（Linuxユーザーの場合）および[こちら](https://elinux.org/RPi_Easy_SD_Card_Setup#Using_the_Win32DiskImager_program)（Windowsユーザーの場合）をご覧ください。

##### TurtleBot PC
- インストール後、ユーザー名**pi**とパスワード**turtlebot**でログインできます。 この場合、Raspberry PiをモニターにHDMIケーブルで接続し、キーボードとマウスをRaspberry Piに接続する必要があります。

- SDカード全体を使用するようにファイルシステムを拡張します。
  ```
  sudo raspi-config
  (select 7 Advanced Options > A1 Expand Filesystem)
  ```

- [ワイヤレス・ネットワークへの接続ガイド](https://www.raspberrypi.org/learning/software-guide/wifi/)

- ネットワークタイムプロトコル（NTP）サーバーにクエリを送信して、コンピューターの日付と時刻を同期および設定します。
  ```
  sudo apt-get install ntpdate
  sudo ntpdate ntp.ubuntu.com
  ```

- パスワード、ロケール、タイムゾーンを変更したい場合(オプション):
  1. sudo raspi-config > 1 Change User Password
  1. sudo raspi-config > 4 Localisation Options > I1 Change Locale
  1. sudo raspi-config > 4 Localisation Options > I2 Change Timezone

- ROSのネットワーク設定 [(reference link)][network_configuration]
	```
	nano ~/.bashrc
	(modify `localhost` to REMOTE_PC_IP and RASPBERRY_PI_3_IP)

	export ROS_MASTER_URI=http://REMOTE_PC_IP:11311
	export ROS_HOSTNAME=RASPBERRY_PI_3_IP
	```

	```
	source ~/.bashrc
	```

##### リモートPC
- ワイヤレス構成が完了したら、デスクトップまたはラップトップからSSH経由でRaspberry Piに接続できます。[(参照リンク)][enable_ssh_server_in_raspberry_pi]:
  ```
  ssh pi@192.168.xxx.xxx (The IP 192.168.xxx.xxx is your Raspberry Pi's IP or hostname)
  ```

{% capture notice_03 %}
**注釈**: **公式Raspbian Stretchとの変更点**
- [Raspbian Stretch with desktop](https://www.raspberrypi.org/downloads/raspbian/)をベースにしています。 RaspbianはDebian Stretchをベースにしています。
- Wolfram、Mathematica、Minecraft Pi、Oracle Java SEなどの非フリーソフトウェアを削除しています。
- libreofficeを削除してイメージのサイズを小さくしています。
- raspi-configを使用してSSHおよびカメラ機能を有効化しています。
- パスワードを変更しています: **turtlebot**
- ROSおよびTurtleBot3のソフトウェアがインストール済みです。
  - [ROS Kinetic Kame](http://wiki.ros.org/kinetic)と依存パッケージ
  - [raspicam_node](https://github.com/UbiquityRobotics/raspicam_node) Raspberry Pi Cameraの依存パッケージ
  - [hls_lfcd_lds_driver](https://github.com/ROBOTIS-GIT/hls_lfcd_lds_driver)レーザ距離センサの依存パッケージ
  - [turtlebot3](https://github.com/ROBOTIS-GIT/turtlebot3)および、 [turtlebot3_msgs](https://github.com/ROBOTIS-GIT/turtlebot3_msgs)
  のパッケージ
  - インストール済みのROSパッケージ (132パッケージ): actionlib, actionlib_msgs, angles, bond, bond_core, bondcpp, bondpy, camera_calibration_parsers, camera_info_manager, catkin, class_loader, cmake_modules, collada_parser, collada_urdf, common_msgs, compressed_image_transport, control_msgs, cpp_common, cv_bridge, diagnostic_aggregator, diagnostic_analysis, diagnostic_common_diagnostics, diagnostic_msgs, diagnostic_updater, diagnostics, dynamic_reconfigure, eigen_conversions, eigen_stl_containers, executive_smach, filters, gencpp, geneus, genlisp, genmsg, gennodejs, genpy, geometric_shapes, geometry, geometry_msgs, hls_lfcd_lds_driver, image_transport, joint_state_publisher, kdl_conversions, kdl_parser, message_filters, message_generation, message_runtime, mk, nav_msgs, nodelet, nodelet_core, nodelet_topic_tools, octomap (plain cmake), opencv3 (plain cmake), orocos_kdl (plain cmake), pluginlib, python_orocos_kdl (plain cmake), python_qt_binding, random_numbers, raspicam_node, resource_retriever, robot, robot_model, robot_state_publisher, ros, ros_base, ros_comm, ros_core, rosbag, rosbag_migration_rule, rosbag_storage, rosbash, rosboost_cfg, rosbuild, rosclean, rosconsole, rosconsole_bridge, roscpp, roscpp_core, roscpp_serialization, roscpp_traits, roscreate, rosgraph, rosgraph_msgs, roslang, roslaunch, roslib, roslint, roslisp, roslz4, rosmake, rosmaster, rosmsg, rosnode, rosout, rospack, rosparam, rospy, rosserial_msgs, rosserial_python, rosservice, rostest, rostime, rostopic, rosunit, roswtf, self_test, sensor_msgs, shape_msgs, smach, smach_msgs, smach_ros, smclib, std_msgs, std_srvs, stereo_msgs, tf, tf_conversions, tf2, tf2_kdl, tf2_msgs, tf2_py, tf2_ros, topic_tools, trajectory_msgs, turtlebot3_bringup, turtlebot3_msgs, urdf, urdf_parser_plugin, visualization_msgs, xacro, xmlrpcpp
{% endcapture %}
<div class="notice--info">{{ notice_03 | markdownify }}</div>

[install_linux_ubuntu_mate]: /docs/en/platform/turtlebot3/raspberry_pi_3_setup/#install-linux-ubuntu-mate
[install_linux_based_on_raspbian]: /docs/en/platform/turtlebot3/raspberry_pi_3_setup/#install-linux-based-on-raspbian
[install_ubuntu]: /docs/en/platform/turtlebot3/joule_setup/#install-linux-ubuntu

[appendix_raspi_cam]: /docs/en/platform/turtlebot3/appendix_raspi_cam/#raspberry-pi-camera
[pc_network_configuration]: /docs/en/platform/turtlebot3/pc_setup/#network-configuration
[network_configuration]: #5-network-configuration
[enable_ssh_server_in_raspberry_pi]: /docs/en/platform/turtlebot3/faq/#enable-ssh-server-in-raspberry-pi
