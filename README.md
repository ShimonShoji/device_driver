# ムカデロボ用デバイスドライバー

Centipedeは振動によって、前方,右方,左方に進むことのできるおもちゃです。

ソースコードはCentipedeに使用するデバイスドライバーです。

# 環境

* Raspberry Pi 3B+
* Ubuntu 18.04 LTS

# 使用方法

* インストール方法

```
$ git clone https://github.com/ShimonShoji/devadra.git
$ cd devadra
$ make
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0
$ echo [動作を指定する整数] > /dev/myled0
```

* アンインストール方法
```
$ sudo rmmod myled
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

# 製作者

* Shimon Shoji
* Chiba Institute of Technology
* shimon.shoji@gmal.com


# 参考
「Lチカ＋モータonラズパイ。より大きな電流の扱い方を知る」　

https://deviceplus.jp/hobby/raspberrypi_i02/　

(accessed 2021/12/14)


# License
" ムカデロボ用デバイスドライバー " is under [GNU General Public License v2.0](https://github.com/ShimonShoji/devadra/blob/main/COPYING)
