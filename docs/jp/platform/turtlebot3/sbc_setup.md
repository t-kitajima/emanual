---
layout: archive
lang: jp
ref: sbc_setup
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/sbc_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 8
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 1"></div>

<!--[dummy Header 1]>
  <h1 id="pc-setup"><a href="#pc-setup">PC Setup</a></h1>
<![end dummy Header 1]-->

## [SBC セットアップ](#sbc-setup)

**警告**: セットアップ作業には、電源と時間が必要なためバッテリーは適していません。この作業では、SMPS(ACアダプタ)の使用を推奨します。
{: .notice--warning}

**注釈**: TurtleBot3の3つのモデルを提供しています。TurtleBot3 BurgerとWaffle PiはRaspberry Pi 3 BおよびB+を使用し、TurtleBot3 WaffleはIntel Joule 570xを使用しています。各モデルで使用されているSBCに応じて、下記のページから選択してください。
{: .notice--info}

### [Raspberry Pi 3](#raspberry-pi-3)

{% capture info_01 %}
**注釈**: Raspberry Pi 3にLinuxとROSをインストールする3つの方法のいずれかを使用します。
1. Ubuntu Mateのインストールについては、`Linuxのインストール（Ubuntu MATE）`ガイドをご覧ください。 TurtleBotのSBCにLinuxイメージをインストールした後、ROSおよび依存パッケージを必ずインストールしてください。 TurtleBot3のROSおよび関連パッケージをインストールするのに、約1時間かかります。
2. RaspbianベースのLinuxディストリビューションイメージのインストールについては、`Linuxのインストール（Raspbian）`ガイドをご覧ください。 ディストリビューションイメージにはTurtleBot3に関連するROSおよびROSパッケージが含まれているため、追加のインストールを行う必要はありません。
3. webOS Robotics Platformについては、`webOS Robotics Platform`ガイドをご覧ください。 TurtleBot3でパッケージをコンパイルする必要はありません。 これらは、OpenEmbeddedを使用して、高性能PC、Ubuntu 18.04ベース、およびそれらから作成されたイメージファイルでクロスコンパイルされます。
{% endcapture %}
<div class="notice--info">{{ info_01 | markdownify }}</div>

{% capture info_02 %}
**注釈**: Raspberry Pi 3 B+はTurtleBot3 BurgerとWaffle Piで利用できます。 Raspberry Pi 3 B+をご利用の場合は、以下をご参照ください。
{% endcapture %}
<div class="notice--info">{{ info_02 | markdownify }}</div>

  1. [Linuxのインストール(Ubuntu MATE)][install_linux_ubuntu_mate]

  2. [Linuxのインストール(Raspbian)][install_linux_based_on_raspbian]

  3. [Linuxのインストール(webOS Robotics Platform)](https://github.com/ros/meta-ros/wiki/OpenEmbedded-Build-Instructions)

### [Intel Joule 570x](#intel-joule-570x)

  - [Linuxのインストール(Ubuntu)][install_ubuntu]

[install_linux_ubuntu_mate]: /docs/en/platform/turtlebot3/raspberry_pi_3_setup/#install-linux-ubuntu-mate
[install_linux_based_on_raspbian]: /docs/en/platform/turtlebot3/raspberry_pi_3_setup/#install-linux-based-on-raspbian
[install_ubuntu]: /docs/en/platform/turtlebot3/joule_setup/#install-linux-ubuntu
