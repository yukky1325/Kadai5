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
| GET | HTMLファイルや画像といったデータを取得する場合に利用する。<br>　Webサイト閲覧時において使用頻度が高い。　|
| POST | フォームに入力したパスワードといったデータを転送する場合に利用する。　|
| PUT | データをアップロードする場合に利用する。<br>Webサーバー上のファイルを置き換えることが出来るため、利用を制限されている場合が多い。 |
| PATCH | Webサーバーに対してリソースの更新を指示するメソッド。 |
| DELETE | 指定したデータを削除する場合に利用する。<br>PUTメソッド同様に利用できないように制限されている場合が多い。 |

# リクエストヘッダーとは
Webサーバーに対してどのような処理をして欲しいかどうかという要求内容を記述したHTTPリクエストの構成する一部。<br>
下記にHTTPリクエストがどのように構成されリクエストヘッダはどこにあたるのか図にて表記致します。

![図1](https://github.com/yukky1325/Kadai5/assets/102965212/ce816552-9f9d-425d-a693-5ac0e92b036d)<br>

1. リクエスト行
- Webサーバーに対してどの様な依頼をするのか伝える情報が含まれている。
2. リクエストヘッダー
- Webブラウザの種類や、対応しているデータのタイプ、データの圧縮方法、言語などの情報を伝える。
3. 空白行
- １行を空けることでリクエストヘッダーの終わりを伝える。
4. メッセージボディ
- Webサーバーにデータを送る為に使用される。空白の場合もある。

## HTTPステータスコードとは
Webブラウザから要求されたHTMLファイルや画像といったデータをWebサーバーはHTTPレスポンスとして応答しますが<br>
HTTPレスポンスの中にはHTTPリクエストに対するWebサーバー内での処理結果が含まれる。それが「HTTPステータスコード」になります。<br>
ステータスコードについての詳細は表記致します。

| コード名 | 説明 | 
|:---:|:---:|
| ２００ | リクエストが正常に受理されたことを通知する。　|
| ２０１ | リクエストが成功してリソースの作成が完了。　|
| ４００ | リクエストが不正であることを通知する。 |
| ４０４ | リクエストされたコンテンツが未検出であることを通知する。 |
| ５００ | リクエスト処理中にサーバー内部でエラーが発生したことを通知する。 |

## レスポンスヘッダーとは
HTTPリクエストに対して応答するHTTPレスポンスの構成する一部。<br>
代表的なものでWebサーバーの固有情報や送信するデータのタイプや、圧縮方法の情報が記載されている。<br>


## レスポンスボディとは
HTTPリクエストに対して応答するHTTPレスポンスの構成する一部。<br>
HTMLや画像などのデータを格納したりする場所。

## JSONとは
JavaScript Object Notationの略で、元々JavaScriptの書き方を参考に制作されたデータ記述言語の一種。<br>
現在は、JavaScriptに限らずPythonなど多様な言語で使用されている。

### 主な使用用途
1. データ保存用の形式
2. 異なるプログラミング言語、環境下でのデータのやり取り

### 特徴
JSON以外の代表的なデータフォーマットとしては、CSVやXMLがあります。<br>
それらの中でJSONが優れている点は、CSVの様な**理解のしやすさ・容量の軽さ**、XMLの様な**扱いやすさ**が兼ね備えられており広く使用されている。

### JSONの記述形式及び例
JSONの記述形式は、`{"キー"："値"}`という様に、キーと値がセットになっている形式。<br>
例えば、NameというキーにTanakaという値が入っているとする。<br>
JSONで記述する場合、下記の様になる。<br>
`{"Name" : "Tanaka" }`　<br>
また、複数のキーと値を組み合わせたい場合は、キーと値の組み合わせの間に,(カンマ)で区切る様にする。  
`{"Name" : "Tanaka","Live" : "Hyogo" }`　<br>
上記注意点として行数が多くなると読みにくくなるので、その場合は改行とインデントを使用する。  

```JSON
{
 "Name" : "Tanaka",
 "Live" : "Hyogo", 
 "Age" : 19
}
```

### JSONが対応しているデータ型
JSONは下記データ型に対応しています。
- 文字列
- 数値
- null
- bool
- オブジェクト
- 配列

**1. 文字列**  
文字列はダブルクォーテーション("),バックスラッシュ（）以外の文字であれば日本語でも入力可能です。<br>
 例`{"name":"Tanaka"}`

**2. 数値**  
数値はダブルクォーテーション(")で囲みません。ダブルクォーテーションを囲むと文字列扱いになります。<br>
例`{"id":123}`

**3. null**  
nullは全て小文字で指定します。<br>
 例`{"id":null}`

 **5. bool値**  
（true or false)の指定も可能です。数値と同じくダブルクォーテーションの必要はありません。  
 例`{"A": true,"B": false}`  

**6. オブジェクト**  
オブジェクトの中にオブジェクトを入れることができます。  
例  　　
```JSON
{
 "id":123,
 "name":"tanaka",
 "detail":{
  "gender":"male",
  "birth":"1989/01/25"
 }
}
```

**7. 配置**  
[]で指定します。配列要素には、文字列、数値、null値、bool値、オブジェクト、配列を全て使用することができます。  
```JSON
{
  "color_list": [ "red", "green", "blue" ],
  "num_list": [ 123, 456, 789 ],
  "mix_list": [ "red", 456, null, true ],
  "array_list": [ [ 12, 23 ], [ 34, 45 ], [ 56, 67 ] ],
  "object_list": [
    { "name": "Tanaka", "age": 26 },
    { "name": "Suzuki", "age": 32 }
  ]
}
```

参照サイト：https://www.tohoho-web.com/ex/json.html  

## JSONを使用したデータ表現  
- 商品情報を例に下記にて表現いたします。
    

```JSON
{
    "fruits_List":[
        {
            "id":1,
            "name":"apple",
            "price":100,
            "stock":true
        },
        {
            "id":2,
            "name":"lemon",
            "price":80,
            "stock":false
        },
        {
            "id":3,
            "name":"strawberry",
            "price":150,
            "stock":true
        },
        {
            "id":4,
            "name":"orange",
            "price":50,
            "stock":false
        }
    ]
}
```
   























  




