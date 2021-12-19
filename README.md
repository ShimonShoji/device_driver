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
```
0 →　モーターを全て停止する。

1 →　前方へ進む。（右モーター, 左モーターの両者が回転。）

2 →　右方へ方向転換する。（左のモーターが回転。右のモーターが停止。）

3 →　左方へ方向転換する。（右のモーターが回転。左のモーターが停止。）

上記以外の値　→　モーターが三回交互にon/offを繰り返したのち、停止する。
```

例. 0という値を与えるとき。
```
$ echo 0 > /dev/myled0
```

# 回路図
![image666](https://user-images.githubusercontent.com/92902614/146665356-ca214bc6-dc02-4041-90fb-81e229bfae2e.jpeg)
![image444](https://user-images.githubusercontent.com/92902614/146210025-520e54f3-fea3-46bc-ab7c-86ba330e26cf.jpeg)
参考にした回路[[1]](https://github.com/ShimonShoji/device_driver/blob/main/README.md#%E5%8F%82%E8%80%83)に加えて、もう一つ同じ機構の回路を組み込んだ。

また、電流の逆流が怖かったためledを用い、LEDのon/offで、対応するGPIOからの出力の有無を判別できるようにした。

# ムカデロボ本体とその動作
[動画](https://youtu.be/00aMZ1T5Yws)


# ムカデロボ制作に用いたもの
* 髪ブラシ
* アクリル板
* モバイルバッテリー（品番：M4161P）
* モーター (品番：00-1741)
* トランジスタ (品番 : 2SD882L-P-T9N-K)
* 抵抗(1kΩ,10kΩ)
* 電池ボックス（単三x3直列）
* LED

# Update
* 0.0.2

説明文とインデントを修正しました。
0,1,2,3以外の値を送ったときの動作を追加しました。

# 製作者
* Shimon Shoji
* Chiba Institute of Technology

# 参考　
[1] 
[「Lチカ＋モータonラズパイ。より大きな電流の扱い方を知る」](https://deviceplus.jp/hobby/raspberrypi_i02/)
(accessed 2021/12/14)

# ライセンス
" ムカデロボ用デバイスドライバー " is under [GNU General Public License v3.0](https://github.com/ShimonShoji/device_driver/blob/main/COPYING)
