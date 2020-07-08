---
layout: archive
lang: jp
ref: hardware_setup
read_time: true
share: true
author_profile: false
permalink: /docs/jp/platform/turtlebot3/hardware_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 12
---

<div style="counter-reset: h1 6"></div>
<div style="counter-reset: h2 3"></div>

<!--[dummy Header 1]>
  <h1 id="setup"><a href="#setup">Setup</a></h1>
<![end dummy Header 1]-->

## [ハードウェアセットアップ](#hardware-setup)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_models.png)

### [パーツリスト](#part-list)

TurtleBot3には、`Burger`、`Waffle`、`Waffle Pi`の3つのモデルがあります。 次のリストは、それらのコンポーネントを示しています。 3つのモデルの大きな違いは、モータ、SBC（シングルボードコンピュータ）、センサです。 TurtleBot3 Waffle モデルは、Intel®Joule™の販売終了により廃止されました。

|                        | パーツ名                         | Burger | Waffle | Waffle Pi |
| --------------------   | --------------------            | ----   | ----   | -------   |
| **シャーシ パーツ**      | Waffle プレート                   | 8      | 24     | 24        |
| .                      | プレート サポート M3x35mm          | 4      | 12     | 12        |
| .                      | プレート サポート M3x45mm          | 10     | 10     | 10        |
| .                      | PCB サポート                      | 12     | 12     | 12        |
| .                      | ホイール                          | 2      | 2      | 2         |
| .                      | タイヤ                            | 2      | 2      | 2         |
| .                      | ボールキャスタ                     | 1      | 2      | 2         |
| .                      | カメラブラケット                   | 0      | 0      | 1         |
| **モータ**              | DYNAMIXEL (XL430-W250-T)        | 2      | 0      | 0         |
| .                      | DYNAMIXEL (XM430-W210-T)        | 0      | 2      | 2         |
| **ボード**              | OpenCR1.0                       | 1      | 1      | 1         |
| .                      | Raspberry Pi 3                  | 1      | 0      | 1         |
| .                      | Intel® Joule™                   | 0      | 1      | 0         |
| .                      | USB2LDS                         | 1      | 1      | 1         |
| **リモート コントローラ** | BT-410 セット(Bluetooth 4, B LE) | 0      | 0      | 1         |
| .                      | RC-100B (リモートコントローラ)     | 0      | 0      | 1         |
| **センサ**              | LDS (HLS-LFCD2)                 | 1      | 1      | 1         |
| .                      | Intel® Realsense™ R200          | 0      | 1      | 0         |
| .                      | Raspberry Pi Camera Module v2.1 | 0      | 0      | 1         |
| **メモリ**              | MicroSD カード                   | 1      | 0      | 1         |
| **ケーブル**            | Raspberry Pi 3 電源ケーブル       | 1      | 0      | 1         |
| .                      | Intel® Joule™ 電源ケーブル        | 0      | 1      | 0         |
| .                      | Li-Po Battery 延長ケーブル        | 1      | 1      | 1         |
| .                      | DYNAMIXEL to OpenCR ケーブル     | 2      | 2      | 2         |
| .                      | USB ケーブル                     | 2      | 2      | 2         |
| .                      | カメラ ケーブル                   | 0      | 0      | 1         |
| **電源**               | SMPS 12V5A                      | 1      | 1      | 1         |
| .                      | A/C コード                       | 1      | 1      | 1         |
| .                      | LIPO バッテリ 11.1V 1,800mAh     | 1      | 1      | 1         |
| .                      | LIPO バッテリ チャージャ           | 1      | 1      | 1         |
| **ツール**              | ドライバ                         | 1      | 1      | 1         |
| .                      | リベットツール                    | 1      | 1      | 1         |
| .                      | USB3.0 ハブ                     | 0      | 1      | 0         |
| **その他**              | PH_M2x4mm_K                     | 8      | 8      | 8         |
| .                      | PH_T2x6mm_K                     | 4      | 8      | 8         |
| .                      | PH_M2x12mm_K                    | 0      | 4      | 4         |
| .                      | PH_M2.5x8mm_K                   | 16     | 12     | 16        |
| .                      | PH_M2.5x12mm_K                  | 0      | 18     | 20        |
| .                      | PH_T2.6x12mm_K                  | 16     | 0      | 0         |
| .                      | PH_M2.5x16mm_K                  | 4      | 4      | 4         |
| .                      | PH_M3x8mm_K                     | 44     | 140    | 140       |
| .                      | NUT_M2                          | 0      | 4      | 4         |
| .                      | NUT_M2.5                        | 20     | 18     | 24        |
| .                      | NUT_M3                          | 16     | 96     | 96        |
| .                      | Rivet_1                         | 14     | 20     | 22        |
| .                      | Rivet_2                         | 2      | 2      | 2         |
| .                      | スペーサ                         | 4      | 4      | 4         |
| .                      | シリコンスペーサ                   | 0      | 0      | 4         |
| .                      | ブラケット                        | 5      | 8      | 6         |
| .                      | アダプタプレート                   | 1      | 1      | 1         |

### [アセンブリ　マニュアル](#assembly-manual)

TurtleBots3は、組み立てキットとして提供されます。 指示に従ってTurtleBot3をアセンブルします。

- `PDF ダウンロード` [アセンブリマニュアル TurtleBot3 Burger](http://www.robotis.com/service/download.php?no=748)
- `PDF ダウンロード` [アセンブリマニュアル TurtleBot3 Waffle](http://www.robotis.com/service/download.php?no=749)
- `PDF ダウンロード` [アセンブリマニュアル TurtleBot3 Waffle Pi](http://www.robotis.com/service/download.php?no=750)

### [アセンブリ動画](#assembly-video)

アセンブリマニュアルでの組み立てが難しい場合は、下記のアセンブリ動画をご覧ください。

#### [TurtleBot3 Burger](#turtlebot3-burger)

<iframe width="640" height="360" src="https://www.youtube.com/embed/rvm-m2ogrLA" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/5D9S_tcenL4" frameborder="0" allowfullscreen></iframe>

#### [TurtleBot3 Waffle](#turtlebot3-waffle)

<iframe width="640" height="360" src="https://www.youtube.com/embed/1nTMyr4ybi0" frameborder="0" allowfullscreen></iframe>

### [オープンソースハードウェア](#open-source-hardware)

Turtlebot3の主なコンポーネントは、シャーシ、モーター、ホイール、OpenCR、SBC、センサ、バッテリーです。 シャーシは、他のコンポーネントを保持するワッフルプレートです。 ワッフルプレートは手のひらほどのサイズですが、シャーシとして重要な役割を果たします。 ワッフルプレートは、製造コストを下げるために射出成形法で製造されています。 ただし、3Dプリント用のワッフルプレートのCADデータは、[Onshape][waffle_plate_on_onshape]からも入手できます。 Turtlebot3 Burgerは、二輪差動駆動タイプのプラットフォームですが、Segway、Tank、Bike、Trailerなど、さまざまな方法で構造的および機械的にカスタマイズできます。

CADデータは、フルクラウドの3D CADエディタであるOnshapeでリリースされています。 PCまたはポータブルデバイスからWebブラウザーを介してアクセスします。 Onshapeを使用すると、仕事仲間と部品を作りや組み立てができます。

- [TurtleBot3 Burger 3Dモデル](http://www.robotis.com/service/download.php?no=676)
- [TurtleBot3 Waffle 3Dモデル](http://www.robotis.com/service/download.php?no=677)
- [TurtleBot3 Waffle Pi 3Dモデル](http://www.robotis.com/service/download.php?no=678)

[waffle_plate_on_onshape]: https://cad.onshape.com/documents/2586c4659ef3e7078e91168b/w/14abf4cb615429a14a2732cc/e/6c94f199b347f8785a67b6f8
[Open Robotics]: http://www.osrfoundation.org/
[ROBOTIS]: http://www.robotis.com
