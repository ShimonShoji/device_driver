# ムカデロボ用デバイスドライバー

２つのモーターのon/offを操作をするデバイスドライバーです。

# 環境

* Raspberry Pi 3B+
* Ubuntu 18.04 LTS

# コードの使用方法

* インストール方法

```
$ git clone git@github.com:ShimonShoji/device_driver.git
$ cd device_driver
$ make
$ sudo insmod centi.ko
$ sudo chmod 666 /dev/myled0
$ echo [動作を指定する整数] > /dev/myled0
```

* アンインストール方法
```
$ sudo rmmod centi
$ make clean
```

# 動作を指定する整数

上記 Usage の[動作を指定する整数]には次の整数を入力します。

0 →　モーターを全て停止する。

1 →　前方へ進む。（右モーター, 左モーターの両者が回転。）

2 →　右方へ方向転換する。（左のモーターが回転。右のモーターが停止。）

3 →　左方へ方向転換する。（右のモーターが回転。左のモーターが停止。）


例. 0という値を与えるとき。
```
$ echo 0 > /dev/myled0
```

# 回路図
![image444](https://user-images.githubusercontent.com/92902614/146210025-520e54f3-fea3-46bc-ab7c-86ba330e26cf.jpeg)

# ムカデロボ制作に用いたもの
* 髪ブラシ
* アクリル板
* モバイルバッテリー（品番：M4161P）
* モーター (品番：00-1741)
* 抵抗(1kΩ,10kΩ)
* 電池ボックス
* LED

# 製作者

* Shimon Shoji
* Chiba Institute of Technology

# 参考
[「Lチカ＋モータonラズパイ。より大きな電流の扱い方を知る」](https://deviceplus.jp/hobby/raspberrypi_i02/)
(accessed 2021/12/14)


# ライセンス
" ムカデロボ用デバイスドライバー " is under [GNU General Public License v3.0](https://github.com/ShimonShoji/device_driver/blob/main/COPYING)
