# Webアプリケーションの概要

tiscon7のアプリケーションについて、おおまかな処理の流れを説明します。<br>
どこにどのようなプログラムファイル（ソースコード）があるのかについて、最も重要な範囲を説明します。<br>
実際にプログラムを参照したり、変更していくためにイメージを掴んでおきましょう。<br>

## 全体像

以下はWebアプリケーションの概念図です。<br>

ソースコードを参照するにあたって、各プログラムの役割を知っておきましょう。<br>

![全体像](../image/web_overview.png)


## Webアプリケーションの処理フロー

シンプルな例として、赤点線内で完結する処理の流れを追ってみましょう。<br>

![説明範囲](../image/web_flow-scope.png)


### ① リクエスト

ボタンのクリックなど、Webブラウザを操作することでサーバへ要求が送られます。<br>
この要求をリクエストと呼びます。<br>

![リクエスト](../image/web_flow1.png)


### ② Controllerの呼び出し

Frameworkはルールに従って、そのリクエストを処理するControllerを呼び出します。<br>

![Controllerの呼び出し](../image/web_flow2.png)


### ③ Viewを呼び出し、HTMLを作る

Controller（Actionクラス）は、ModelやViewなどの必要な処理の呼び出しを制御します。<br>
今回の例では画面表示を担うViewの呼び出しのみを行います。（必要があれば、Viewを呼ぶ前にModelを呼び出します。）<br>

![Viewの呼び出し](../image/web_flow3.png)

<br>
ViewはHTMLを作成します。<br>
画面はユーザ操作によって内容が変わるのが普通なので、受け取った値を使ってHTMLを作成します。<br>

![HTMLの生成](../image/web_flow4.png)


### ④ レスポンス

HTMLができたらFrameworkが受け取り、ユーザへ結果を返します。<br>

![レスポンス](../image/web_flow5.png)


<br>

以上がWebアプリケーションのベースとなる処理の流れです。<br>

どのようなプログラムファイルが登場したか、流れとあわせてイメージできればＯＫです。<br>
※簡略化して説明しているため、厳密に理解している必要はありません。<br>



## プログラム構成

当日の環境構築で動作確認の手順まで終えると、以下のようなプログラムが確認できます。<br>
これまでの説明と照らし合わせて、それぞれの役割と呼び出される流れを確認してみましょう。<br><br>

![プロジェクト構成](../image/tiscon_sourcecode.png)



