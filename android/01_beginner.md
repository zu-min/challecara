# Androidアプリ開発の基本

 - 公式ページは[ここ](http://developer.android.com/index.html)です。
 - Androidアプリ開発環境構築からはじめてのアプリ(Hello, World!)を実行するところまでを中心にまとめています。
 - 次へ踏み出す人のためのリンクもいくつか紹介しています。
 - 先人たちが作られた資料へのリンクを紹介させていただいております。この場をお借りして感謝申し上げます。
 - これの通りにやってもできない場合はググッてください。
 - 世界を驚かせるアプリを作りましょう！


## 0. Java Development Kit(JDK)のインストール

[Java SE Downloads](http://www.oracle.com/technetwork/java/javase/downloads/index.html)からお使いのパソコンに適するファイルを選んでインストールしてください。

たいていの方は以下のいずれかではないかとおもいます。

 - jdk-8u60-windows-x64.exe (Windows 64bit)
 - jdk-8u60-windows-i586.exe (Windows 32bit)
 - jdk-8u60-macosx-x64.dmg (Mac)

上記はJava SE Development Kit 8u60でのファイル名となります。適宜読み替えてください。8u60のところが変わります。

公式ページにはJDK7と書いてありますがJDK8でかまいません。

#### 参考
 - [Java(JDK)ダウンロードとインストール](http://www.javadrive.jp/install/)

## 1. Android Studioのインストール

Androidアプリの開発にはAndroid Studioと呼ばれるIDE(Integrated Development Environment) を使います。

[ここ](http://developer.android.com/sdk/index.html)からダウンロードできます。

画面の一番上のほうにある緑色のDOWNLOAD ANDROID STUDIO FOR [WINDOWS|MAC]ボタンを押せばダウンロードできます。

### 注意
 - Windowsをお使いの方でユーザ名に日本語や空白(スペース)を使っている方は、半角英数字だけで構成されたユーザアカウント（管理者権限）を作って、そのユーザでログインした状態でインストールしてください。
 - 日本語ユーザ名でインストールすると、あとでなぞのエラーに悩まされることになります。

#### 参考
 - [AndroidStudio インストール](http://qiita.com/hiromiyamamoto/items/ed7535361e51d103b74d)

## 2. Hello, World!アプリ作成 -> 実行

Android StudioのインストールができたらまずはHello, World!を表示するandroidアプリケーションを作ってみましょう。これにより、以下のようなことを確認します。
 - 開発環境が正しくインストールできているか
 - 作ったアプリケーションの実行方法

#### 参考
 - [[Android] Hello world アプリをAndroid Studioで作成](https://akira-watson.com/android/helloworld.html)

## 3. 作ったアプリを動かしてみましょう!

androidスマートフォンをお使いの方は実機で動作確認をすることをオススメします。

### 3-1. 端末の設定
 - 「設定」->「端末情報」->「ビルド番号」を７回ほどタップします
 - 「設定に」戻ると「{ }開発者向けオプション」が表示されています
 - 開発者むけオプションの中に入りUSBデバッグに有効にします（ＯＮにする）
  - 機種によってはメニュー名が微妙に違ったりするので適宜読み替えてください。

#### 参考
 - [[Android] USB ドライバーの設定（Nexus7 2013）](https://akira-watson.com/android/nexus7-usb-driver.html)

### 3-2. ADBドライバのインストール
 - Windows PCで開発される方のみ必要な手順です。MacではADBドライバのインストールは不要です。
 - USBケーブルで実機とパソコンをつなぎます。買ったときについていたUSBケーブルを使ってください。たまに充電しかできないケーブルがあるのでその際は「データ転送」対応のものを買ってください。500円から1500円くらいです。

#### 参考
 - [[Android] USB ドライバーの設定（Nexus7 2013）](https://akira-watson.com/android/nexus7-usb-driver.html)

### 3-3. 実機で動かす
 - USBケーブルで実機とパソコンをつなぎ、メニュー下の三角のアイコンをクリックして実行させます
 - どうでしょう？ Hello, World!は表示できましたか？　Developer登録($25)やいくつかの手続きを経るとGoogle Playに公開できます！

#### 参考
 - [[Android] Hello world アプリをAndroid Studioで作成](https://akira-watson.com/android/helloworld.html)

### 3-4. エミュレータで動かす
 - 実機をもっていない人向けです。パソコンの性能がよいと問題なく動きます。

#### 参考
 - [Android再入門 - エミュレータの作成](http://qiita.com/gabu/items/8bc1a11f1382409f1d2a)
 - [Run on the Emulator](http://developer.android.com/training/basics/firstapp/running-app.html#Emulator)

## 4. デバッグ方法
#### 参考
 - [Androidの便利なデバッグ手法](http://qiita.com/kazy/items/252bfc2d88d8899a95d5)
  - まずは「男は黙ってprintf」です。
  - デバッガの使用方法も書いてあります。ブレークポイントを指定して実行中のプログラムを中断してそのときの変数の値なんかをのぞき見ることができます。
 - [Debugging with Android Studio](http://developer.android.com/tools/debugging/debugging-studio.html)

## 5. 次は何を？
 - [Building Your First App](http://developer.android.com/training/basics/firstapp/index.html)
  - 公式のHello, World!相当の説明です。自動的に作られるディレクトリやファイルの説明です。
  - まずはapp/src/main/の下のものを主に触ることになります。
 - [ボタン(Button)を使用するには](http://www.adakoda.com/android/000065.html)
  - [Activity#findViewById(int)][findViewById], [View#setOnClickListener(View.OnClickListener)][setOnClickListener]がポイントです。
  [findViewById]: https://developer.android.com/reference/android/app/Activity.html#findViewById(int)
  [setOnClickListener]: http://developer.android.com/reference/android/view/View.html#setOnClickListener(android.view.View.OnClickListener)
 - 小さな吹き出しを表示するには? Toastを使いましょう。
  - [トースト(Toast)を使用するには](http://www.adakoda.com/android/000086.html)
 - [Starting Another Activity](http://developer.android.com/training/basics/firstapp/starting-activity.html)
  - ボタンを押したときに他のActivityを起動する手順の説明です。
 - [Activities](http://developer.android.com/guide/components/activities.html)
  - onCreate, onResume, onPause, onDestroyてなに？　などなどの説明です。

<img src="http://developer.android.com/images/activity_lifecycle.png" />
 - データを保存したいときは? SharedPreferencesやSQLiteOpenHelperを調べてみましょう。
  - [Saving Data](http://developer.android.com/training/basics/data-storage/index.html)
 - カメラを使いたい人は
  - [Camera](http://developer.android.com/guide/topics/media/camera.html)
  - [Capturing Photos](http://developer.android.com/training/camera/index.html)
 - 音楽を再生したい人は
  - [Media Playback](http://developer.android.com/guide/topics/media/mediaplayer.html)
 - HTTP通信をしたい人は
  - [Performing Network Operations](https://developer.android.com/training/basics/network-ops/index.html)
  - [Transmitting Network Data Using Volley](https://developer.android.com/training/volley/index.html)
 - ログを出力したいときは[android.util.Log](https://developer.android.com/reference/android/util/Log.html)のクラスメソッドを使いましょう。
 - お役立ちページ
  - [TechBooster](http://techbooster.jpn.org/category/andriod/)
  - [逆引きAndroid入門](http://www.adakoda.com/android/)
  - [Y.A.M の雑記帳](http://y-anz-m.blogspot.jp/)
 - 上に挙げたこと以外をやりたい人は下記から探すか、ググりましょう
  - [Traning](https://developer.android.com/training/index.html)
  - [API Guides](https://developer.android.com/guide/index.html)
 - サンプルは無いですか?
  - [Samples](http://developer.android.com/samples/index.html)
 - 結局最後は、[公式ページ](http://developer.android.com/index.html)を隅から隅まで確認してください。すべてここに書いてあります。
 - Windowsパソコンの電源OFFしたあと後日Android Studioを立ち上げると前回作ったはずのプロジェクトが表示されない場合があります。その際はあせらずに左上のほうに「1:Project」と縦書きで書いてあるものを押してみましょう。Project Viewはお好きなものを選択していただいてかまいません。個人的にはエクスプローラ(Windows)やFinder(Mac)でみたときに同じようにみえるProjectをオススメします。

<img src="https://developer.android.com/images/tools/projectview01.png" />
