# 第5回課題製作
下記にて課題の製作を致します。

## URLとは
URLとは「Uniform Resource Locator」の略になります。<br>
意味としてはインターネット上のホームページやファイルの位置や情報を示す情報。<br>
インターネット上の住所だと考えるとわかりやすい。<br>
例えば、インターネットのブラウザ上でホームページを閲覧しているときに<br>
上部のアドレスバーに記載されている。半角英数字の下記のような文字列がURLに該当する。

例
<img width="1657" alt="スクリーンショット 2024-03-03 7 43 19" src="https://github.com/yukky1325/Kadai5/assets/102965212/471f8720-c722-4144-b1c9-beaf51f3b2b3">

<br>

## クエリ文字列とは
サーバーにデータを送信する為にURLの末尾に付加される文字列のことです。<br>
表記の仕方及び役割を下記にて表記します。<br>

### 表記方法
下記の様なURLがあるとする。<br>
URLの内の？以降の▢＝△がクエリ文字列です。別名クエリパラメータとも呼ばれます。<br>

例<br>
`http://〇〇.jp/?▢＝△`
 <br>

また基本的な記号と位置については下記のようになります。<br>

| 記号 | 位置 | 目的 | 例 |
|:---:|:---:|:---:|:---:|
| ? |	?以前にある文字列 | クエリパラメータを付与する |	http://〇〇.jp/?▢=△ |
| = |パラメータの名前と値の間 |	名前と値を付与する | http://〇〇.jp/?▢=△ |
| & |	クエリパラメータ同士の間 | 複数のクエリパラメータを付与する | http://〇〇.jp/?▢=△&■=▲ |
| #	| クエリパラメータの後ろ | ページ内リンクを挿入する | http://〇〇.jp/?▢=△#◇◇ |

### 役割
クエリ文字列の役割は２種類あり目的や付与後の変化によってかわります。
- パッシブパラメータ
  パッシブパラメータの目的はWebページに固有のパラメータを付与し、アクセス経路やユーザーの属性を把握・分析することです。
  パラメータの有無に関わらず、表示ページは同じです。

- アクティブパラメータ
  アクティブパラメータの目的は、付与するパラメータによって表示するページを変えることです。
  主にECサイトなどで活用されております。

## パス変数（パスパラメーター）とは
URLパスの一部に埋め込まれる変数をパラメータといいます。<br>
表記の仕方及び特徴を記載します。

### 表記の仕方
パスパラメータの表記方法は基本的には下記の様になります。<br>
`/(リソース名)/{パラメータ名}`<br>
例えばユーザー情報を取得したい場合URLのcomの後の/users/1234がパスパラメータにあたるものです。<br>
例<br>
`http://〇〇.com/users/1234`

### 特徴
- URLパスに直接埋め込むので、読み取りが簡単。
- GETリクエストに主に利用される、
- データの取得や特定のリソースの操作に利用される。
- 変更が稀なので、キャッシュしやすい。

## クエリ文字列とパス変数の違いとは？
1. 見た目が違う
- パス変数 `http://・・・.com/group`
- クエリ文字列　`http:/・・・.com/group?id=2`<br>
上記の様にパス変数は`group`にあたるのに対し、クエリ文字列は`id=2`にあたる。<br>

2. 　役割の違い
- パス変数は、特定のリソースを識別する為に必要。
- クエリ文字列は特定のリソースを操作して条件を追加するのに必要。

## HTTPメソッドとは何か
HTTPリクエストを用いてWebサーバーに具体的な要求内容を伝えるために必要なメソッド。<br>
HTTPメソッドの種類と役割を下記にて表記いたします。

| メソッド名 | 役割 | 
|:---:|:---:|
| GET | HTMLファイルや画像といったデータを取得する場合に利用する。Webサイト閲覧時において使用頻度が高い。 |
| POST | 
| PUT |
| PATCH |
| DELETE |














  




