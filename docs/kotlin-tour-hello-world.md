---
layout: reference
title: "Hello World"
---
# Hello World

- ![ステップ1]({{ site.baseurl }}/assets/images/icons/icon-1.svg){:width="20" style="display:inline"} **Hello world**
- ![ステップ2]({{ site.baseurl }}/assets/images/icons/icon-2-todo.svg){:width="20" style="display:inline"} [基本型](kotlin-tour-basic-types.md)
- ![ステップ3]({{ site.baseurl }}/assets/images/icons/icon-3-todo.svg){:width="20" style="display:inline"} [コレクション](kotlin-tour-collections.md)
- ![ステップ4]({{ site.baseurl }}/assets/images/icons/icon-4-todo.svg){:width="20" style="display:inline"} [制御フロー](kotlin-tour-control-flow.md)
- ![ステップ5]({{ site.baseurl }}/assets/images/icons/icon-5-todo.svg){:width="20" style="display:inline"} [関数](kotlin-tour-functions.md)
- ![ステップ6]({{ site.baseurl }}/assets/images/icons/icon-6-todo.svg){:width="20" style="display:inline"} [クラス](kotlin-tour-classes.md)
- ![ステップ7]({{ site.baseurl }}/assets/images/icons/icon-7-todo.svg){:width="20" style="display:inline"} [Nullセーフティ](kotlin-tour-null-safety.md)

"Hello, world!"と出力するプログラムは以下のようになります：

{% capture hello-world-kotlin %}
fun main() {
    println("Hello, world!")
    // Hello, world!
}
{% endcapture %}
{% include kotlin_quote.html body=hello-world-kotlin %}

Kotlinでは:
* 関数を定義するのに `fun` が使われる
* `main()` 関数からプログラムが開始する
* 関数のボディは中括弧の中に書かれる `{}`
* [`println()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.io/println.html) と [`print()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.io/print.html) 関数は引数を標準出力にプリントする

> 関数は続く章でより詳細に議論します。そこまでは、`main()` 関数しか出てきません
{: .note }

## 変数

プログラムというものは、基本的にはデータを保持する必要があるものです。そして変数というものは、まさにそれを行うだけのものです。Kotlinでは、変数を宣言するのに以下の二つのキーワードがあります：
* 読み取り専用（read-only）の変数： `val`
* 値を変更する（mutableな）変数： `var`

値を設定するには、`=` オペレータを使います。

例を見てみましょう：

{% capture kotlin-tour-variables %}
fun main() { 
//sampleStart
    val popcorn = 5    // ポップコーンが5箱あります
    val hotdog = 7     // ホットドッグが7つあります
    var customers = 10 // 列に10人の客が並んでいます
    
    // 何人かの客が列から去りました
    customers = 8
    println(customers)
    // 8
//sampleEnd
}
{% endcapture %}
{% include kotlin_quote.html body=kotlin-tour-variables %}

> 変数はプログラムの最初、`main()`関数の外にも定義出来ます。このように定義された変数は **トップレベル（top level）**と呼ばれます。
{: .note }

`customers` はmutableな変数なので、定義した後にも値の再設定が可能となっている。

> 基本的にはすべての変数を読み取り専用(つまり`val`)にするのがオススメです。
> 必要な時だけmutableな変数 (つまり`var`)にするようにしましょう。 
> 
{: .note}

## 文字列テンプレート

最初の段階で変数の中身を標準出力にプリントする方法を知っておくと便利です。
この目的のためには、**文字列テンプレート（string templates）** という機能が使えます。
テンプレート式を使って変数に格納されたデータややその他のオブジェクトにアクセスし、それを文字列に変換する事が出来ます。
文字列の値は文字の列をダブルクオート、つまり`"`でくくったものです。
テンプレート式はいつもドル記号、つまり`$`で始まります。

コード片をテンプレート式で実行したい場合は、ドル記号`$`の後ろに中括弧、つまり`{}`を置き、
この中括弧の中に実行したいコード片を置きます。

例をあげましょう。:

{% capture kotlin-tour-string-templates %}
fun main() { 
//sampleStart
    val customers = 10
    println("There are $customers customers")
    // There are 10 customers
    
    println("There are ${customers + 1} customers")
    // There are 11 customers
//sampleEnd
}
{% endcapture %}
{% include kotlin_quote.html body=kotlin-tour-string-templates %}

より詳しくは、[文字列テンプレート](strings.md#文字列テンプレート)を参照ください。

変数の定義に明示的な型の表記が無い事に気づいたかもしれません。
Kotlinは型を推論します：この場合は`Int`と。
このツアーではKotlinの様々な基本型を説明していきます。
また、それをどう宣言するかは[次の章](kotlin-tour-basic-types.md)で扱います。

## 練習問題

以下のコードを完成させて、`"Mary is 20 years old"`と標準出力にプリントせよ：

{% capture kotlin-tour-hello-world-exercise %}
fun main() {
    val name = "Mary"
    val age = 20
    // ここにコードを書いてね
}
{% endcapture %}
{% include kotlin_quote.html body=kotlin-tour-hello-world-exercise %}

{% capture kotlin-tour-hello-world-solution %}
```kotlin
fun main() {
    val name = "Mary"
    val age = 20
    println("$name is $age years old")
}
```
{% endcapture %}
{% include collapse_quote.html body=kotlin-tour-hello-world-solution title="解答例" %}

## 次回

[基本型](kotlin-tour-basic-types.md)