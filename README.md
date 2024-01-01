# mypkg
mypkgは、2023年度千葉工業大学未来ロボティクス学科のロボットシステム学の講義内で作成したリポジトリである。

# コマンドtalker.pyとlistener.pyについて
[![test](https://github.com/reimakumamoto/mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/reimakumamoto/mypkg/actions/workflows/test.yml)

# トピックについて
トピックは、ROSで異なるノード間でデータをやり取りするための仕組みである。今回使用されているトピックは'countup'である。これは整数型のメッセージをやり取りするためのトピックである。

# 機能
## talker.py
* 'Talker'クラス内で整数を０から順にカウントし、それを整数型のメッセージとしてトピックに送信する。

## listener.py
* talker.pyで順にカウントされた整数を購読して、値を標準出力に表示する。

# 実行例１
## 端末１(talker側)
```
$ ros2 run mypkg talker
何も表示されない。
```

## 端末２(listener側)
```
$ ros2 run mypkg listener
[INFO] [1703688419.255160553] [listener]: Listen: 0
[INFO] [1703688419.727265156] [listener]: Listen: 1
[INFO] [1703688420.228365334] [listener]: Listen: 2
[INFO] [1703688420.727714189] [listener]: Listen: 3
[INFO] [1703688421.227552609] [listener]: Listen: 4
[INFO] [1703688421.727729059] [listener]: Listen: 5
[INFO] [1703688422.228736313] [listener]: Listen: 6
[INFO] [1703688422.728262223] [listener]: Listen: 7
[INFO] [1703688423.228273847] [listener]: Listen: 8
[INFO] [1703688423.728437164] [listener]: Listen: 9
・・・
```

# 実行例２
launchファイル(talk_listen.launch.py)を使用すれば、一つの端末で実行することができる。
```
$ ros2 launch mypkg talk_listen.launch.py
[listener-2] [INFO] [1703689717.297011111] [listener]: Listen: 0
[listener-2] [INFO] [1703689717.792163724] [listener]: Listen: 1
[listener-2] [INFO] [1703689718.292045252] [listener]: Listen: 2
[listener-2] [INFO] [1703689718.792893872] [listener]: Listen: 3
[listener-2] [INFO] [1703689719.291994319] [listener]: Listen: 4
[listener-2] [INFO] [1703689719.791933290] [listener]: Listen: 5
[listener-2] [INFO] [1703689720.291829242] [listener]: Listen: 6
[listener-2] [INFO] [1703689720.792092497] [listener]: Listen: 7
[listener-2] [INFO] [1703689721.292341236] [listener]: Listen: 8
[listener-2] [INFO] [1703689721.792121131] [listener]: Listen: 9
・・・
```
## 必要なソフトウェア
* ROS 2
* python

## テスト環境
* Ubuntu 20.04

## テスト内容
* 2023年度千葉工業大学未来ロボティクス学科の講義で使用した上田隆一先生のコンテナを活用しています。
* [上田 隆一先生のコンテナ](https://hub.docker.com/r/ryuichiueda/ubuntu22.04-ros2)

# ライセンス
* このソフトウェアパッケージは、３条項BSDライセンスの下、再頒布および使用が許可されます。
* このパッケージのコードは、下記のスライド (CC_BY_SA 4.0 by Ryuichi Ueda)のものを、本人の許可を得て自作の著作としたものです。
    * [ryuichiueda/my_slides/robosys2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* © 2023 Reima Kumamoto
