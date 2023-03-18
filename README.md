## Zebra-Printer_How to View Data that Printer Recieved from Host
## プリンタがホストから受信したデータをキャプチャする方法

1. プリンタに対して下記コマンドを実行する。
<pre>
! U1 setvar "input.capture" "run"
</pre>
2. プリンタに対して、データを送信する。

3. 下記コマンドを実行し、"IN???.DMP"形式のファイルが作成されていることを確認する。
   ??? は0-999の数値。数値が大きいほど最新のデータ。
<pre>
! U1 do "file.dir" "E:"
</pre>
![image](https://user-images.githubusercontent.com/111269302/226099357-c37255d0-2bbd-4011-9f08-b2b3722a0122.png)

4. 下記コマンドを実施し、任意のDMPファイル内容を表示することができる。
<pre>
! U1 do "file.type" "E:IN???.DMP"
</pre>
![image](https://user-images.githubusercontent.com/111269302/226099381-5ca70d9e-5694-490e-8a46-821c9cedeb31.png)

</br>
DMPファイルはFTPを用いてダウンローすることも可能。(Default - User:zebra/ Pass:1234)  

![image](https://user-images.githubusercontent.com/111269302/226099829-ef3d3f45-c5e2-4dfb-924d-d339dd60829d.png)


5. キャプチャ作業が終了したら、ユーザ領域を圧迫しないようにDMPファイルの削除とキャプチャ機能をOFFにすること。
<pre>
Input Capture機能の無効化
! U1 setvar "input.capture" "off"

DMPファイルの削除
! U1 do "file.delete" "E:IN0*.DMP"
</pre>
</br>
</br>
詳細は本家ドキュメントを参照すること。  </br>
https://supportcommunity.zebra.com/s/article/Capturing-and-viewing-data-sent-to-a-Zebra-Link-OS-compatible-printer?language=en_US  


  
