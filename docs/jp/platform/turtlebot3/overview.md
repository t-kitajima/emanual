---
layout: archive
lang: jp
ref: turtlebot3_overview
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/overview/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 1
---

<div style="counter-reset: h1 0"></div>

# [概要](#overview)

![](/assets/images/platform/turtlebot3/overview/turtlebot3_with_logo.png)

## [TurtleBot](#turtlebot)

[TurtleBot][turtlebot]は、[ROS][ros]標準のプラットフォームロボットです。タートルは、1967年に教育用コンピュータープログラミング言語[Logo][logo]によって駆動されたタートルロボットに由来しています。また、ROSの基本チュートリアルにて最初に登場する[turtlesim node][turtlesim]は、[ロゴタートルプログラム][logo_primer]のコマンドシステムを模倣したプログラムです。ROSのシンボルである[タートルアイコン][tuturtle]の作成にも使われています。ROSのロゴに使われている9つのドットは、亀の背中の甲羅に由来しています。Logoのタートルから派生したTurtleBotは、Logoを使ったコンピュータプログラミング言語を教えるだけでなく、TurtleBotを通してROSを初めて学ぶ人にも簡単に教えることができるように設計されています。それ以来、TurtleBotは、ROSの標準プラットフォームとして、開発者や学生の間で最も人気のあるプラットフォームとなっています。

## [TurtleBot3](#turtlebot3)

[TurtleBot][turtlebot] シリーズには3つのバージョンがあります。TurtleBot1は、Willow GarageのTully（Open Roboticsのプラットフォームマネージャー）とMelonee（Fetch RoboticsのCEO）が、iRobotのRoombaをベースにした研究用ロボットである「Create」の上にROS展開用に開発したものです。2010年に開発され、2011年から販売されています。2012年には、研究用ロボット「iClebo Kobuki」をベースにした「TurtleBot2」をYujin Robotが開発しました。2017年には、先代に不足していた機能を補うための機能や、ユーザーの要求を取り入れたTurtleBot3が開発されました。TurtleBot3は、走行にROBOTISスマートアクチュエータ[DYNAMIXEL][DYNAMIXEL]を採用しています。TurtleBotシリーズのより詳細な情報は、以下の [リンク][history]をご覧ください。

TurtleBot3は、教育、研究、ホビー、製品プロトタイピングなどで使用するための、小型で手頃、プログラマブルなROSベースの移動ロボットです。TurtleBot3の目標は、機能性と品質を犠牲にすることなく、プラットフォームのサイズを劇的に小さくして価格を下げると同時に、拡張性を提供することです。TurtleBot3は、メカニカルパーツの再構成方法や、コンピューターやセンサーなどのオプションパーツの使用方法によって、様々なカスタマイズが可能です。また、堅牢な組込みシステムや360度距離センサ、3Dプリント技術などに適した、コストパフォーマンスに優れた小型SBCに進化しています。

TurtleBot3のコア技術は、[SLAM][SLAM]、[Navigation][Navigation]、[Manipulation][Manipulation]で、家庭内サービスロボットに適しています。SLAM(Simultaneous localization and mapping)アルゴリズムを実行して地図を作成し、部屋の中を走り回ることができます。また、ノートパソコンやジョイパッド、Androidベースのスマートフォンから遠隔操作が可能です。TurtleBotは、部屋の中を歩く人の足を追いかけることもできます。また、OpenMANIPULATORのようなマニピュレータを装着することで、対象物を操作することができるモバイルマニピュレータとしても利用することができます。 [OpenMANIPULATOR][openmanipulator] は、TurtleBot3のWaffleやWaffle Piと互換性があるという利点があります。この互換性により、自由度の低さを補い、TurtleBot3が持つSLAMやナビゲーション機能でサービスロボットとしての完成度を高めることができます。

## [TurtleBot3 紹介ビデオ](#turtlebot3-introduction-video)

<iframe width="640" height="360" src="https://www.youtube.com/embed/9OC3J53RUsk" frameborder="0" allowfullscreen></iframe>

## [TurtleBot3 コラボレーションプロジェクト](#turtlebot3-collaboration-project)

TurtleBot3は、[Open Robotics][open_robotics]、[ROBOTIS][robotis]の他、[The Construct][the_construct],
[Intel][intel]、[Onshape][onshape]、[OROCA][oroca]、[AuTURBO][auturbo]、[ROS in Robotclub Malaysia][ros_in_robotclub_malaysia]、 [Astana Digital][astana digital]、[Polariant Experiment][polariant_experiment]、[東京農工大学 GVlab][gvlab]、[国立交通大学ネットワーク制御ロボティクス研究室][nctu]、[ダルムシュタット工科大学SIMグループ][sim_group]などのパートナーとのコラボレーションプロジェクトです。オープンロボティクスはソフトウェアやコミュニティ活動を担当し、ROBOTISは製造やグローバル流通を担当しています。

このTurtleBot3コラボレーションプロジェクトの最も重要な部分は、オープンソースベースのソフトウェア、ハードウェア、コンテンツです。ロボット工学分野をより豊かにするために、より多くのパートナーや共同研究者の参加を呼びかけています。

オープンソースロボティクスを実現するために、私たちとのパートナーシップに興味をお持ちの方は、フォーム [こちら][partners] にご記入ください。


### TurtleBot3 プロバイダ
![](/assets/images/platform/turtlebot3/logo_platform_providers.png)

### TurtleBot3 パートナーと共同研究先
![](/assets/images/platform/turtlebot3/logo_platform_sponsors.png)

\* 各コラボメンバーのWebページは [こちら][partners] からご覧いただけます。

### TurtleBot3 ディストリビュータ
![](/assets/images/platform/turtlebot3/logo_platform_players.png)

\* 各コラボメンバのWebページは [こちら][partners] からご覧いただけます。

### TurtleBot3 マップ
<div>
<script type="text/javascript" src="https://embed.githubusercontent.com/view/geojson/turtlebot/map/master/Distributors.geojson"></script>
</div>

[turtlebot]: https://www.turtlebot.com/
[ros]: http://www.ros.org/about-ros/
[logo]: http://el.media.mit.edu/logo-foundation/index.html
[turtlesim]: http://wiki.ros.org/turtlesim
[logo_primer]: http://el.media.mit.edu/logo-foundation/what_is_logo/logo_primer.html
[tuturtle]: http://wiki.ros.org/tuturtle
[dynamixel]: http://en.robotis.com/subindex/dxl_en.php
[history]: https://www.turtlebot.com/about/
[slam]: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
[navigation]: https://en.wikipedia.org/wiki/Robot_navigation
[manipulation]: https://en.wikipedia.org/wiki/Robotic_manipulation
[openmanipulator]: http://emanual.robotis.com/docs/en/platform/openmanipulator/

[open_robotics]: https://www.openrobotics.org/
[robotis]: http://www.robotis.com/
[the_construct]: http://www.theconstructsim.com/
[intel]: http://www.intel.com/
[onshape]: https://www.onshape.com/
[oroca]: http://www.oroca.org/
[auturbo]: https://github.com/AuTURBO/
[ros_in_robotclub_malaysia]: https://www.youtube.com/channel/UCLvvXbwPkostryBQt4MIbUw
[astana digital]: https://www.youtube.com/channel/UCWiIY_zrKH-LMlx2GBWu3yA
[polariant_experiment]: https://www.polariant.io/
[gvlab]: http://web.tuat.ac.jp/~gvlab/
[nctu]: https://sites.google.com/a/g2.nctu.edu.tw/ncrl/
[sim_group]: https://www.sim.informatik.tu-darmstadt.de/en/index/
[partners]: https://www.turtlebot.com/partners
