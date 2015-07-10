# 開発環境の構築

ノービスコースではUnix系のOSの利用を推奨しています。これはRuby on Railsで書かれたWebアプリケーションのほとんどがUnix系のOS上で動作するように設計されており、それに伴いUnix系OS上の方が開発時に予期せぬ問題にぶつかりにくいためです。Macを使われている方はそのままMac上に開発環境を構築してください。Windowsを利用されている方は仮想化ソフトウェアを利用し、Windows上でUnix系OSの一種であるLinuxの環境を構築します。

Macを利用されている方は[Rails GirlsのMac OS Xようセットアップガイド](http://railsgirls.jp/install/#setup_for_os_x)に従って進めてください。以下はWindowsを使われている方向けの説明になります。

## Linuxについて

Linuxとは正確にはLinuxカーネルと呼ばれるものです。これを元に様々なデスクトップ環境などのソフトウェアを付与し、一般利用者が使いやすくしたOSが無料で配布されています。こういったOSをLinuxディストリビューションと呼びます。今回はその中からUbuntuというOSを利用します。
Ubuntuは快適なデスクトップ環境を簡単に利用できるように設計されているOSです。ノートパソコンに直接Ubuntuをインストールして利用している方も多く、Linuxのディストリビューションの中では広く利用されているものです。

## 仮想化について

Windows上でUbuntuを動作させるためには仮想化という技術を利用します。これはすでに動作しているOS上に、ソフトウェアで仮想的にハードウェアを再現し、その上で別のOSを動作させるものです。今回はOracleが提供しているVirtual Boxという仮想化ソフトウェアを利用します。

さて、ここからは実際に環境を構築していきましょう。

## 1. Virtual Boxをインストールする

[ここ](http://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html?ssSourceSiteId=otnjp)からWindows用のVirtualBoxをダウンロードしてください。

ダウンロードしたファイルをダブルクリックしインストールを進めてください。

## 2. Ubuntuの仮想マシンを作成する

Ubuntuの仮想マシンの作成方法はISOイメージから通常のハードウェア上にインストールする手順で作成する方法と、Ubuntuがインストールされたハードディスクの仮想イメージを元に作成する方法があります。今回は仮想ハードディスクイメージを元に作成します。

[ここ](https://ubuntulinux.jp/download/ja-remix-vhd)から `Ubuntu 14.04 LTS` のイメージをダウンロードしてください。

ダウンロードしたら、VirtualBoxを起動し、[新規]をクリックします。仮想マシン作成ウィザードが開くので、画面の指示に従って入力していきます。

### OSタイプ
OSタイプは

- オペレーティングシステム: Linux
- バージョン: Ubuntu(64bit)

を選んでください。

### メモリーサイズ
メモリーサイズはご利用のノートパソコンのメモリサイズに合わせて調整してください。ひとまず1024MB程度にしておけば良いでしょう。余裕がある場合は2048MBなど多めにしておくと動作が速くなると思います。


### ハードドライブ
ハードドライブは

- すでにある仮想ハードドライブを使用する

を選び、先ほどダウンロードした仮想ハードドライブを選択してください。
ここまでで仮想マシンの構築は完了です。

## 3. Ubuntuを起動する

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm01.png" width="600" />  
そのまま[続ける]を押してください。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm02.png" width="600" />  
そのまま[続ける]を押してください。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm03.png" width="600" />  
自分のノートパソコンのキーボードレイアウトを選択して[続ける]を押してください。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm04.png" width="600" />  
ユーザ名とパスワードを設定します。好きなものを設定して大丈夫です。ただし、パスワードは忘れないように気をつけて下さい。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm05.png" width="600" />  
初期設定が実行されます。しばらく待ちましょう！

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm06.png" width="600" />  
初期設定が完了しました。ログインしてUbuntuを使い始めることができます！

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/setup_vm07.png" width="600" />
ログインするとこのようなデスクトップが表示されます！

### ターミナルの起動
これ以降の手順はUbuntu上のターミナルを使いながら進めます。ターミナルの起動手順を説明します。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/open_terminal01.png" width="600" />  
<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/open_terminal02.png" width="600" />  
<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/open_terminal03.png" width="600" />  
ジャン！起動しました。

### Ubuntuが遅い時の設定
ターミナルを起動しようと操作をするとUbuntuがすごく遅く感じられるかもしれません。そういう場合にはVirtualBoxの設定によりいくらか軽減できる可能性がありますので、下の設定を試してみてください。設定のためには一旦Ubuntuをシャットダウンして、VirtualBoxの設定を開いてください。

<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/vm_performance01.png" width="600" />
<img src="https://raw.githubusercontent.com/challecara/challecara/master/novice/images/vm_performance02.png" width="600" />  

## 4. ライブラリのインストール
始めからインストールされているパッケージの更新を行います。パッケージとはソフトウェアを配布、インストールしやすい形にしたものです。

```
$ sudo apt-get update -y
```

apt-getとはUbuntuでパッケージのインストールや更新などの管理を行うためのコマンドです。sudoは別のユーザ権限で続くコマンドを実行するためのコマンドです。ここではroot権限でapt-getを実行するために利用しています。実行するとパスワードを聞かれますので、Ubuntuの初回起動時に設定したパスワードを入力してください。

次に、今後の開発で利用する様々なパッケージをインストールします。個別のパッケージの説明は省きます。

```
$ sudo apt-get install build-essential bison openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-0 libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev nodejs -y
$ sudo apt-get install imagemagick --fix-missing -y
```

## 5. Rubyのインストール
ここからはRubyのインストールを行います。Rubyのインストールは幾つかの方法があります。上で紹介したapt-getでインストールする方法やRubyのソースコード（C言語で書かれている）をコンパイルしインストールする方法、Rubyのバージョンマネージメントツールを使いインストールする方法などがよくあるやり方です。

### 5-1. rbenvとruby-buildのインストール
今回はRubyのバージョンマネジメントツールであるrbenvとrubyのビルドツールであるruby-buildを組み合わせて使う方法でインストールを行います。
インストールの前にrbenvとruby-buildの役割について簡単に説明します。

rbenvを利用することで簡単にRubyのバージョンを切り替えることができます。Rubyを使い複数のアプリケーションの開発を行っていくと、それぞれのアプリケーションで別々のRubyのバージョンを使っている状況がよく起こります。その時に開発するアプリケーションによってRubyのバージョンを切り替える必要が出てきます。こういった場合にrbenvが役に立ちます。

ruby-buildはRubyをソースコードからビルドするためのrbenvのプラグインです。これにより簡単に新しいバージョンのRubyをインストールすることができます。それではインストールしていきましょう。

```
$ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
$ git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
$ source ~/.bashrc
```

簡単に説明していきます。 まず `git` ですが、これはソースコードの管理ツールです。これによりrbenvとruby-buildのソースコードを取得しています。詳しくは後々説明していきます。
`echo` は渡された文字列を標準出力に吐き出すコマンドです。それを `>>` で `.bashrc` というファイルの末尾に書き込んでいます。書き込んでいる内容はrbenvが操作するようにする設定です。 `.bashrc`はターミナルを起動した時(正確にはシェルの起動時）に読み込まれる設定ファイルです。
さいごに`source` でその設定ファイルを読み込み、設定をロードしています。ターミナル起動時には自動で読み込まれるのですが、設定を書き込んだ直後は自分で読み込まないと、設定が有効になりません。

### 5-2. Rubyのインストール
さて、やっとRubyのインストールです。とはいえrbenvとruby-buildが入っているので、やることは簡単です。以下を実行してください。

```
$ rbenv install 2.2.2
$ rbenv global 2.2.2
```

1行目で現在の最新であるバージョン2.2.2のインストールを行います。しばらく時間がかかりますので、待ちましょう。その後、バージョン2.2.2を標準で利用するRubyとするために `global` を使い設定しています。

インストールに成功していれば以下のように表示されるはずです。

```
$ ruby -v
ruby 2.2.2p95 (2015-04-13 revision 50295) [x86_64-linux]
```

## 6. Railsのインストール

### 6-1. RubyGemsについて
Rubyをインストールすると `gem` というコマンドが一緒にインストールされます。これはgem(ジェム)と呼ばれるRubyのライブラリを管理するためのコマンドです。このコマンドを使い、様々なRuby用のライブラリをインストールすることができます。

### 6-2. Bundlerのインストール
`Bundler` は上で説明したgemの一つです。`gem`コマンドを使いインストールします。Railsをインストールするために必要なわけではありませんが、先にインストールしておきます。
BundlerはRailsアプリケーションが利用する様々なgemのバージョンを管理するためのツールです。一般にRailsアプリケーションを開発する場合、様々なgem(Rubyで使えるライブラリ)を利用することになります。例えばファイルアップロードができるようにするgemやよくあるログイン処理などを行ってくれるgemなどがあります。これらを利用して開発を進めていった時に、利用しているgemのどのバージョンを使っているのか管理しなくてはいけません。そうしないと、自分の環境では動作しても他の共同開発者のパソコン上で環境を作った時により新しいバージョンがインストールされてしまい動きが変わってしまったり、最悪の場合、動作しなくなってしまいます。こういった時にBundlerを使っているとどのバージョンを使っているのかを管理できるため混乱がありません。
実際にどのようにしてgemのバージョンを管理しているかは後々解説していきます。

```
$ gem install bundler --no-rdoc --no-ri
```

`--no-rdoc --no-ri`はドキュメントファイルのインストールを省くためのオプションです。インストール時間を短縮するために入れています。

### 6-3. Railのインストール
さて、やっとRailsのインストールです。Railsもgemとして提供されていますので、`gem`コマンドを使いインストールできます。

```
$ gem install rails --no-rdoc --no-ri
```

以上でRailsのインストールが完了しました。
