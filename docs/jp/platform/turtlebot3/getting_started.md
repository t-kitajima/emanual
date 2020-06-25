---
layout: archive
lang: en
ref: getting_started
read_time: true
share: true
author_profile: false
permalink: /docs/en/platform/turtlebot3/getting_started/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 5
---

<div style="counter-reset: h1 4"></div>

# [はじめに](#getting-started)
このページは、TurtleBot3の初心者の方ためのページです。マニュアルの内容は膨大な量になりますが、このページでは、その内容の構成（章立て）について説明します。

## [TurtleBot3について](#about-turtlebot3)
まずは、[Overview][overview]、[Notices][notices]、[Features][features]、そして [Specifications][specifications]のページから情報を集めて、TurtleBot3の全体像を把握しましょう。

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_models_800.png)

## [TurtleBot3を使用するための最初のステップ](#first-steps-for-using-turtlebot3)

**注意**: このページは、ROS1をベースに書かれています。TurtleBot3でROS2を使用する場合は、e-Manualの関連ページを参照してください。

上記の手順でTurtleBot3についての理解が深まったところで、ソフトウェアとハードウェアのセットアップを行います。ロボットを組み立てるよりも、先にSBCとPCをセットアップしておいた方が時間の節約になります。以下の順番で進めていくことをお勧めします。

1. [PCのセットアップ](/docs/en/platform/turtlebot3/pc_setup/)
  - 主にTurtleBot3との通信に使用している **Remote PC** にアプリケーション（ROS 1、特定のLinuxバージョン、依存パッケージ）をインストールします。
2. [SBCのセットアップ](/docs/en/platform/turtlebot3/sbc_setup/#sbc-setup)
  - **リモートPC** との通信に使用される **Single Board Computer**（SBC）に、いくつかのアプリケーション（ROS 1、特定のLinuxバージョン、依存パッケージ）をインストールします。

    **注釈**：TurtleBot3で異なる種類のSBCやセンサを使用したい場合には、[Compatible Devices][compatible_devices]ページを参照してください。

3. [OpenCRのセットアップ](/docs/en/platform/turtlebot3/opencr_setup/#opencr-setup)
  - TurtleBot3の最新のファームウェアをOpenCR組み込みボードにアップロードします。
4. [ハードウェアのセットアップ][hardware_setup]
  - 説明書を参考にして、TurtleBot3を組み立てます。

  ![](/assets/images/platform/turtlebot3/setup/setup.png)

## [基本操作を始める](#lets-try-the-basic-operation)
以上の手順が完了したら、付属の[Bringup][bringup]パッケージを使ってロボットを動かし、遠隔操作機能を使ってロボットを遠隔操作してみましょう。  
次に、ロボットに搭載されている各種センサの値を確認したり、[基本操作][basic_operation]ページを読んでロボットの制御方法を学んでみましょう。

- [Bringup][bringup]
- [基本操作][basic_operation]

![](/assets/images/platform/turtlebot3/example/operation.png)

## [TurtleBot3の要素技術](#keep-turtlebot3s-various-technologies-with-you)
TurtleBot3のコア技術は、[SLAM][SLAM]、[ナビゲーション][Navigation]、[マニピュレーション][Manipulation]であり、家庭内のサービスロボットに適しています。これらの技術は、実在するロボットにも、[シミュレーション][simulation]機能を備えた仮想ロボットにも適用できます。  
もちろん、[自動駐車][autonomous_driving]や[機械学習][machine_learning]などをTurtleBot3に実装することも可能です。また、TurtleBot3 Friendsとして12種類の[Locomotion][locomotion]と共に差動駆動型の移動ロボットを紹介しています。このオープンエンドコンポーネントにより、様々な特徴を持ったTurtleBot3 Frendsを作ることができます。今までにない全く新しいロボットを作ることができます。また、Followerデモ、パノラマデモ、自動駐車などの面白いアプリケーションも用意されています。応用例は[応用編][応用編]ページをご覧ください。

- [[ROS 1] SLAM][slam]
- [[ROS 1] ナビゲーション][navigation]
- [[ROS 1] シミュレーション][simulation]
- [[ROS 1] マニピュレーション][manipulation]
- [[ROS 1] 自動運転][autonomous_driving]
- [[ROS 1] 機械学習][machine_learning]
- [ロコモーション][locomotion]
- [アプリケーション][applications]

![](/assets/images/platform/turtlebot3/example/technologies.png)

## [より学び、調べる](#learn-and-explore-more)
上記はTurtleBot3の使用例です。以下の情報を参考にして、より多くのことを学び、挑戦することができます。

コンストラクトが提供するROS講座や、TurtleBot3ユーザーが作成した各種講座、Webコンテンツ、YouTube講座、無料書籍などを利用することで、より多くのことを[学ぶ][learn]ことができます。また、ROBOTISが制作した様々な[ビデオ][videos]も参考になり、TurtleBot3研究協力者やTurtleBot3ユーザーが公開している様々な[プロジェクト][projects]でTurtleBot3を利用したユースケースを確認することができます。また、[チャレンジ][challenges]では様々なチャレンジに挑戦することができます。

- [学ぶ][learn]
- [ビデオ][videos]
- [プロジェクト][projects]
- [チャレンジ][challenges]

![](/assets/images/platform/turtlebot3/example/projects.png)

## [参考文献と連絡先](#references-and-contacts)
[付録][appendixes]には、TurtleBot3で使用されているDYNAMIXEL、OpenCR、LDSなどのコンポーネントの情報が掲載されています。TurtleBot3で使用されているオープンソースは、[オープンソースとライセンス][opensource_and_licenses]ページに記載されており、このページには各ライセンスの情報が記載されています。TurtleBot3についてご不明な点があれば、[FAQ][faq]をご覧になるか、[問い合わせ先][contact_us]からご連絡ください。  

- [付録][appendixes]
- [オープンソースとライセンス][opensource_and_licenses]
- [FAQ][faq]
- [お問い合わせ][contact_us]

[概要]: /docs/en/platform/turtlebot3/overview/
[お知らせ]: /docs/en/platform/turtlebot3/notices/
[特徴]: /docs/en/platform/turtlebot3/features/
[仕様]: /docs/en/platform/turtlebot3/specifications/

[はじめに]: /docs/en/platform/turtlebot3/getting_started/

[セットアップ]: /docs/en/platform/turtlebot3/setup/
[PCのセットアップ]: /docs/en/platform/turtlebot3/pc_setup/
[SBCのセットアップ]: /docs/en/platform/turtlebot3/sbc_setup/
[OpenCRのセットアップ]: /docs/en/platform/turtlebot3/opencr_setup/
[ハードウェアのセットアップ]: /docs/en/platform/turtlebot3/hardware_setup/
[対応機器]: /docs/en/platform/turtlebot3/compatible_devices/

[bringup]: /docs/en/platform/turtlebot3/bringup/
[基本操作]: /docs/en/platform/turtlebot3/basic_operation/

[SLAM]: /docs/en/platform/turtlebot3/slam/
[ナビゲーション]: /docs/en/platform/turtlebot3/navigation/
[シミュレーション]: /docs/en/platform/turtlebot3/simulation/
[マニピュレーション]: /docs/en/platform/turtlebot3/manipulation/
[自動運転]: /docs/en/platform/turtlebot3/autonomous_driving/
[機械学習]: /docs/en/platform/turtlebot3/machine_learning/
[ロコモーション]: /docs/en/platform/turtlebot3/locomotion/
[アプリケーション]: /docs/en/platform/turtlebot3/applications/

[ラーニング]: /docs/en/platform/turtlebot3/learn/
[ビデオ]: /docs/en/platform/turtlebot3/videos/
[プロジェクト]: /docs/en/platform/turtlebot3/projects/
[チャレンジ]: /docs/en/platform/turtlebot3/challenges/

[appendixes]: /docs/en/platform/turtlebot3/appendixes/
[opensource_and_licenses]: /docs/en/platform/turtlebot3/opensource/
[faq]: /docs/en/platform/turtlebot3/faq/
[contact_us]: /docs/en/platform/turtlebot3/contact_us/
