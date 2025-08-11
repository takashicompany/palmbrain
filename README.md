# Palmbrain

Palmbrain(パームブレイン)は17mm(0.9u)の狭ピッチを採用した、34キーの分割型キーボードです。

[miniDivide](https://github.com/takashicompany/minidivide)や[Palmslave](https://github.com/takashicompany/palmslave)のような0.8uと通常の1uサイズのキーボードのちょうど中間にあたるサイズ感の機種となります。　

これまでの0.8u機種と同様、小さく薄いため持ち運びやすく、スマートフォンやタブレットとの相性も抜群です。　

デスクの占有スペースも比較的小さくて済むので、普段遣いにも適しています。　

また、これまでの0.8u機種と比べるとキーの間隔が少しだけ広がっているため、miniDivideやPalmslaveでは手のサイズが合わなかった方でも狭ピッチの良さを感じられることができるかもしれません。　

<img src = "./images/0-0.png" width = "600px" />

キースイッチはChoc v1とChoc v2に対応しています。

オプションでBLE Micro Proとコイン電池を搭載可能なため、PC・スマートフォン・タブレットへBluetoothでの接続が可能です。


# 部品

## キットに含まれているもの

|部品|個数|備考|
|:--|:--|:--|
|PCB|2||
|~~[ダイオード(表面実装型)](https://shop.yushakobo.jp/collections/all-keyboard-parts/products/a0800di-02-100)~~|~~32~~|Palmbrainはダイオード不要です。|
|[タクトスイッチ](https://shop.yushakobo.jp/products/a0800ts-01-1)|2|miniDivideやPalmslaveと型が異なります。
|[TRRSソケット](https://shop.yushakobo.jp/products/a0800tr-01-1?_pos=1&_sid=6aacd8367&_ss=r)|2||
|ゴム足シール|8||
|ネジ(M2 8mm)|22||

### 3Dプリントケース

データは[こちら](./case/3d-print)です。

|部品|個数|備考|
|:--|:--|:--|
|スイッチプレート(トッププレート)|2||
|ボトムプレート|2||
|MCUカバー(Pro Microプレート)|2||

## ご自身で用意いただくもの

### 部品

|部品|個数|備考|
|:--|:--|:--|
|[キースイッチ](https://shop.yushakobo.jp/collections/all-switches/products/)|34|Choc v1、v2に対応しています。Lofreeのキースイッチにも対応しています。|
|0.9uキーキャップ(17mm)|34|※[下記](#キーキャップ)参照|
|[Pro Micro](https://shop.yushakobo.jp/products/3905)|2|動作確認済みのものは[こちら](https://shop.yushakobo.jp/products/3905)です。高さがあるPro Micro(USB-C採用をしたものなど)はPro Microカバーと干渉してしまうことがあります。背の低いPro Microを選択するかスペーサーを長いものに取り替えるなどで対応できます。また、USB-B採用のものはモゲ防止にエポキシ接着剤で補強等の対策を推奨します（[こちら](https://1-4nomiya.hatenablog.com/entry/2019/01/27/164414)を参考ください）。|
|[コンスルー](https://shop.yushakobo.jp/products/31)|4|12ピンのものを購入しておけばPro Micro、BLE Micro Proの両方に用いることができます。|
|[TRRSケーブル](https://shop.yushakobo.jp/products/8023)|1|有線接続の際に左右のキーボードを接続します。**ケーブルが太いものはケースと干渉してしまうことがありますので、左右接続を有線で行う場合は[細身のケーブル](https://shop.yushakobo.jp/products/8023)をご利用ください。**|

### キーキャップ

キーキャップは0.9uピッチ(17mm未満)に対応したものをご利用ください。

[こちらの記事](https://e3w2q.github.io/10/)を参考にするとより良いかと思います。

### 無線化をする場合

|部品|個数|備考|
|:--|:--|:--|
|[BLE Micro Pro](https://shop.yushakobo.jp/products/ble-micro-pro)|2|Pro Microの代わりに取り付けることでBluetooth接続が可能。|
|[チップ積層セラミックコンデンサー](https://akizukidenshi.com/catalog/g/g106041/)|2|BLE Micro Proでの無線化の際に使用。|
|[電源スイッチ(MK12C02)](https://ja.aliexpress.com/item/32798526843.html)|2|BLE Micro Proでの無線化の際に使用。|
|[HU1632](https://www.monotaro.com/p/8835/2765/)|2|BLE Micro Proでの無線化の際に使用。|


## 組み立て方

**組み立てる前に、全ての工程に一度目を通し、頭の中で組み立てるイメージをすると失敗が少なくスムーズに作業が進められます。**

**また、封入されている基盤はリバーシブルのため、左右・裏表がわからなくなってしまうことがありえます。片方ずつ作成すると比較的失敗を回避して組み立て作業ができます。以降の説明は基本的に左手側の組み立て写真を用いて説明しています。**


### 1. PCB裏表と左右を確認する。

キット外観

<img src = "./images/1-0.png" width = "600px" />

基板はリバーシブル構造となっており、左手側の表は右手側の裏面となります。はじめに、プレートを取り外して基板を取り出したあとに、左右を混同しないようにマスキングテープなどで表面に目印を付けておくことを推奨します。

<img src = "./images/1-1.png" width = "600px" />

また、片手ずつ組み立てていくとミスを減らすことができます。


左手キット外観と分解後

<img src = "./images/1-2.png" width = "295px" /> <img src = "./images/1-3.png" width = "295px" />

**以降の説明は基本的に左手側の組み立てを説明します。基板の裏表が逆以外は、後述のMCUの裏表の向きが逆である他は全て同じ手順になります。**


### 2. リセットスイッチの取り付け

リセットスイッチとして、タクトスイッチを基板に取り付けます。リセットスイッチはMCUにファームウェアを書き込む際に利用します。

もしもリセットスイッチをつけなくとも、ピンセット等で導通させることで動作させられます。

<img src = "./images/2-0.png" width = "600px" />

リセットスイッチの取り付け箇所は基板の**表側**になります。

**miniDivideやPalmbrainは裏面取り付けだったので、取り付ける向きは特に注意！**

タクトスイッチを基板の**表側**に載せます。

<img src = "./images/2-1.png" width = "600px" />

基板を裏返してタクトスイッチの足が基板裏面から出ていることを確認します。

<img src = "./images/2-2.png" width = "600px" />

基板とタクトスイッチの足をハンダ付けします。

<img src = "./images/2-3.png" width = "600px" />


### 3. Pro Microの取り付け

MCU(Micro Controller Unit)として、Pro Microを取り付けます。MCUは主にキーボードの入力をPCなどの外部デバイスに伝達します。

PalmbrainはBLE Micro Proを用いた無線化に対応していますが、動作が正しくない場合のトラブルシューティングの観点から、最初はPro Microによる有線接続で組み立てることを推奨します。

<img src = "./images/3-0.png" width = "600px" />

Pro Micro(BLE Micro Pro)を基板に取り付ける際は[コンスルー](https://shop.yushakobo.jp/products/31)を使用することを強く推奨します。コンスルーを用いることでMCUが故障した際の交換が容易になります。また、Pro Microを用いて組み立てた後にBLE Micro Proへ移行する際の移行も容易になります。

<img src = "./images/3-1.png" width = "600px" />

コンスルーを基板の**表側**に挿します。この際にハンダ付けはしないでください。Pro Microを挿す場合は基板の端側のBATとGNDのピン穴は空けておきます。

<img src = "./images/3-2.png" width = "600px" />

また、コンスルーには向きがあります。コンスルーをよく見ると穴が空いていますが、穴は中心ではなく、片側に寄っています。穴が空いている側にMCU、穴が空いていない側にPalmbrainの基板が来るように差し込んでください。

（[こちら](https://note.com/akasha_min/n/nad98cc2758c0)を参考にするとより良いかと思います）

<img src = "./images/3-3.png" width = "600px" />

コンスルーにPro Microを載せます。コンスルーを載せる際には基板のピンの印字と、Pro Microのピンの印字が合致することを確認してください。

<img src = "./images/3-4.png" width = "600px" />

**左手側と右手側でPro Microの裏表が異なります。** [こちらのPro Micro](https://shop.yushakobo.jp/products/pro-micro)では**左手側の場合はPro Microの部品がPalmbrainの基板側に来るように配置します。**

<img src = "./images/3-5.png" width = "600px" />

**右手側の場合はPro Microの部品が表側になるように配置します。**

<img src = "./images/3-6.png" width = "600px" />

コンスルーとPro Microをハンダ付けします。Pro Microによってはハンダ付けをせずに導通できるものもあります。BLE Micro Proの場合も同様です。

<img src = "./images/3-7.png" width = "600px" />

右手側も同様の手順で取り付けます。先述した通り右手側はPro Microの裏表が逆になります。

<img src = "./images/3-8.png" width = "600px" />

左右にPro Microを載せると下記のようになります。

<img src = "./images/3-9.png" width = "600px" />

### 4. TRRSソケットの取り付け

左右のキーボードをTRRSケーブルで接続する際のTRRSソケットを取り付けます。

<img src = "./images/4-0.png" width = "600px" />

TRRSソケットを基板の表側に載せます。

<img src = "./images/4-1.png" width = "600px" />

基板を裏返してTRRSソケットの足が基板裏面から出ていることを確認します。4つの足が出ている状態が正しいです。

<img src = "./images/4-2.png" width = "600px" />

基板とTRRSソケットの足をハンダ付けします。

<img src = "./images/4-3.png" width = "600px" />

### 5. 無線化用の部品の取り付け

#### チップ積層セラミックコンデンサー

BLE Micro Proを用いた無線化は、**Pro Microでの有線接続で左右のキーボード全てのキーの入力が確認できた後に実施することを推奨**します。

無線化自体は組み立てが終わった後でも実施可能ですので、後回しにしてもOKです。

後回しでもOKですが、基板とスイッチプレートを取り付けてからのハンダ付けはスイッチプレートが邪魔になって難易度が上がってしまうため、将来的に無線化したい場合は6の前に実施することを推奨します。

チップ積層セラミックコンデンサーを取り出します。

<img src = "./images/5-0.png" width = "600px" />

取り付け箇所は、**基板裏面**のコイン電池ホルダー部になります。

<img src = "./images/5-1.png" width = "600px" />

チップ積層セラミックコンデンサーはタクトスイッチやTRRSソケットとは異なり足が無いので、取り付け箇所の片側に予備ハンダを行います。

<img src = "./images/5-2.png" width = "600px" />

ピンセットでコンデンサーを掴みながら予備ハンダを溶かしつつ片側をハンダ付けします。

<img src = "./images/5-3.png" width = "600px" />

<img src = "./images/5-4.png" width = "600px" />

コンデンサーのもう片側もハンダ付けを行います。

<img src = "./images/5-5.png" width = "600px" />

予備ハンダ側はハンダに含まれる松やにが揮発していることが多いので、フラックスを塗って再度ハンダこてで加熱することで、基板とコンデンサーの密着性が向上します。

<img src = "./images/5-6.png" width = "600px" />

<img src = "./images/5-7.png" width = "600px" />

#### 電源スイッチ

電源スイッチを取り出します。取り付け箇所は取り付け箇所は**基板裏面**のコイン電池ホルダー部、チップ積層セラミックコンデンサーの近くになります。

<img src = "./images/5-8.png" width = "600px" />

電源スイッチの足と基板のハンダ付け箇所が合うように載せ、電源スイッチの足と基板をハンダ付けします。

<img src = "./images/5-9.png" width = "600px" />

#### コイン電池ホルダー

コイン電池ホルダーを取り付けます。取り付け箇所は**基板の表側**、Pro Microとリセットスイッチの隣です。

<img src = "./images/5-10.png" width = "600px" />

コイン電池ホルダーの足が基板に通るように穴を確認しながら挿します。基板を裏返した際にホルダーが抜け落ちてしまう場合はマスキングテープなどで固定すると作業がスムーズに進められます。

<img src = "./images/5-11.png" width = "600px" />

<img src = "./images/5-12.png" width = "600px" />

基板の裏面からホルダーの足が出ていることを確認します。

<img src = "./images/5-13.png" width = "600px" />

赤丸の位置からホルダーの足が出ていることが確認できたら足と基板をハンダ付けします。

<img src = "./images/5-14.png" width = "600px" />

コイン電池ホルダーにCR1632を入れます。また、Pro Microと同様にBLE Micro Proを取り付けます。

Pro Microは片側12ピンですが、BLE Micro Proは13ピンとなります。12ピンのコンスルーのみお持ちの方はBATの穴にコンスルーのピンが来るように挿してください。

12ピンのコンスルーのみのお持ちの方はBATの穴にコンスルーのピンが来るように挿してください(取り付け例は[こちら](https://x.com/takashicompany/status/1906256170035408966))。

また、[13ピンのコンスルー](https://shop.yushakobo.jp/products/31?variant=37665714438305)も取り扱いがありますので、こちらを利用することを推奨します。

BLE Micro Proの設定手順は[こちら](https://sekigon-gonnoc.github.io/BLE-Micro-Pro/#/getting_started?id=ble-micro-pro-web-configurator%e3%82%92%e4%bd%bf%e3%81%a3%e3%81%a6%e3%83%95%e3%82%a1%e3%83%bc%e3%83%a0%e3%82%a6%e3%82%a7%e3%82%a2%e3%82%92%e6%9b%b8%e3%81%8d%e8%be%bc%e3%82%80)を参考に進めてください。

### 6. ケースとキースイッチの取り付け

以降は左手側での組み立て説明です。右手側も手順は同様です。

2025/8/1現在、アクリルプレートの取り扱いがないため、3Dプリントケースの組み方の説明のみとなります。

#### 3Dプリントケース

スイッチプレートを用意します。

<img src = "./images/6-0.png" width = "295px" /> <img src = "./images/6-1.png" width = "295px" />

<img src = "./images/6-2.png" width = "600px" />

スイッチプレートと基板をキースイッチで固定します。

<img src = "./images/6-3.png" width = "600px" />

キースイッチを4-5個程度スイッチプレートに挿します。パチンと音がするまでしっかり挿し込みます。

また、右下の2キーはキースイッチの向きが他と上下逆になっているので挿し間違えないよう確認します。

<img src = "./images/6-4.png" width = "600px" />

表側

<img src = "./images/6-5.png" width = "600px" />

裏側

<img src = "./images/6-6.png" width = "600px" />

スイッチプレートを裏向きにして基板を載せて、先ほど挿したキースイッチの足が基板の裏側から出るように挿し込みます。
基板の裏側から全てのキースイッチの足が出ていることを確認します。

<img src = "./images/6-7.png" width = "600px" />

キースイッチの足と基板をハンダ付けします。キースイッチと基板をハンダ付けすることで、キースイッチと基板でスイッチプレートを固定します。

<img src = "./images/6-8.png" width = "295px" /> <img src = "./images/6-9.png" width = "295px" />

残り全てのキースイッチ(片手側で17個、両手合わせて34個)を取り付けてハンダ付けします。

<img src = "./images/6-10.png" width = "600px" />

<img src = "./images/6-11.png" width = "600px" />

Pro Microカバーを取り出します。

<img src = "./images/6-12.png" width = "600px" />

スイッチプレートとPro Microカバーを重ね合わせます。

<img src = "./images/6-13.png" width = "600px" />

ネジをスイッチプレートの裏面から3箇所挿し込み、ネジを留めます。

<img src = "./images/6-14.png" width = "600px" />

TRRSソケットカバーを取り出します。

<img src = "./images/6-15.png" width = "600px" />

スイッチプレートとTRRSソケットカバーを重ね合わせます。

<img src = "./images/6-16.png" width = "600px" />

ネジをスイッチプレートの裏面から2箇所挿し込み、ネジを留めます。

<img src = "./images/6-17.png" width = "600px" />

ボトムプレートを取り出します。

<img src = "./images/6-18.png" width = "600px" />

スイッチプレート(と基板)にボトムプレートをはめ込みます。

<img src = "./images/6-19.png" width = "600px" />

ネジをボトムプレートの裏面からネジ穴に挿します。

<img src = "./images/6-20.png" width = "600px" />

### 7. ゴム足シールの取付け

ケースの底面に滑り止めとしてゴム足シールを貼り付けます。

<img src = "./images/7-0.png" width = "600px" />

打鍵スタイルにあわせてお好みの位置に貼り付けてください。

<img src = "./images/7-1.png" width = "600px" />

### 8. キーキャップの取り付け

キースイッチにキーキャップを取付けて完成です。

<img src = "./images/8-0.png" width = "600px" />

### 9. ファームウェアの書き込み

2025/08/1時点では[Github内のPalmbrainのファームウェア](./firmwares)をご利用ください。

.hexファイルをダウンロードした後、[Pro Micro Web Updater](https://sekigon-gonnoc.github.io/promicro-web-updater/index.html)から書き込みが可能です。

詳しい書き込み方法は[こちら](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox)をご参考ください。

また、Remap上から書き込む準備が整い次第、Remapからの書き込みも可能となります。

<img src = "./images/9-0.png" width = "600px" />

ファームウェアは[Remapから書き込む](https://remap-keys.app/catalog/kS0copgeHBGwqGWnSK9o/firmware)ことができます。また、Remapのトップページから「キーボードを探す」→キーボード名を選択し、『Palmbrain』と検索し、Palmbrainのページに移動した後にファームウェアのタブを選択することで該当のページに遷移することが可能です。

<img src = "./images/9-1.png" width = "295px" /> <img src = "./images/9-2.png" width = "295px" />

Remapでのファームウェア書き込みは[こちら](https://docs.dailycraft.jp/buildguides/firmware/remap.html)を参照すると手順が分かりやすいかと思います。

Remapの使い方は[こちら](https://salicylic-acid3.hatenablog.com/entry/remap-manual)を参照するのが分かりやすいかと思います。

RemapでMCU(Pro Micro)が正しく動作するかを確認できます。USBでPCに接続しRemapを開いた後に、右下の3点リーダからTest Matrix modeを選択してください。

<img src = "./images/9-3.png" width = "600px" />

全てのキースイッチが点灯するかを確認します。なお、ファームウェアは左手側をUSBとして接続することを前提としているので、片手側のみを接続した場合は左手側が点灯します。

もし点灯しないキーがあった場合はキースイッチのハンダ付けを再度行うと改善することがあるかと思います。

### 10. 完成した後の楽しみ方

完成しましたら、ぜひSNSなどに写真を投稿頂ければと思います。

Twitterのハッシュタグは [`#Palmbrain #自作キーボード`](https://twitter.com/search?q=%23%E8%87%AA%E4%BD%9C%E3%82%AD%E3%83%BC%E3%83%9C%E3%83%BC%E3%83%89%20%23Palmbrain&src=typed_query) を付けていただけると幸いです。

キットを組み立てた感想や、キーボードを使った所感などをお待ちしております！
