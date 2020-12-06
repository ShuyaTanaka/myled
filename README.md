# myled task1
授業で扱ったデバイスドライバのコードを改造して、２つのLEDが光ったり消えたりするものに改造する。

# 実験で使用するもの

LED(赤）×　２
抵抗（300Ω）×　２
ブレッドボード
ジャンパー線 ＊８
Raspberry Pi４

#実行内容詳細

echo 1 > /dev/myled0
　　↓
GPIO25,GPIO23につながっているLED2つが同時に点灯

echo 2 > /dev/myled0
    ↓
GPIO25につながっているLEDは光るが、GPIO23につながっているLEDは光らない

echo 3 > /dev/myled0
    ↓
GPIO25につながっているLEDは光らないが、GPIO23につながっているLEDは光る
    
echo 0 > /dev/myled0
    ↓
GPIO25,GPIO23につながっているLED2つは点灯しない
    
#　実行順
$ make
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0
$ echo 1 > /dev/myled0
$ echo 2 > /dev/myled0
$ echo 3 > /dev/myled0
$ echo 0 > /dev/myled0

#　結果
動画：https://youtu.be/0GkcRRgEYU0


