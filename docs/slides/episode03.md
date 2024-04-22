---
marp: true
---

# 実践プログラマー コンテキス

すごい広島 IT初心者の会

---

## 構成

- 自己紹介
- コンテキス
- まとめ

---

## 自己紹介

カキギカツユキ

ネット通販の会社で業務システムの開発運用してます
あと、売掛金・買掛金管理業務してます
ぼっち情シスです
クソザコトレーダーです

---

## コンテキス

```plantuml
@startmindmap

* コンテキス
-- 種類
-- 構成要素
--- 文脈
--- 状況
** 言語学
*** コミュニケーション状況
** IT
*** コンピューティング
*** プログラミング
** ビジネス

@endmindmap
```

> コンテキストはこれらの原則の中で最もわかりにくいものだが、実は最も根本的なものである。
>
> エリック・エバンスのドメイン駆動設計


> コンテキストこそが重要
> コンテキストは王様である。DDDを実践する際には、特にそれがいえる。
>
> 実践ドメイン駆動設計

---

### 種類

```plantuml
@startmindmap

* コンテキス
** 種類
*** ハイコンテキスト・ローコンテキスト
*** 社会的コンテキスト
*** コンテキストマーケティング
*** ビジネスコンテキスト
*** コンテキストメニュー
*** 境界付けられたコンテキスト

@endmindmap
```

- ハイコンテキストとは互いに大きな共通理解を持っている状態。
- ローコンテキストとは互いに共通理解が少なく、全ての物事を明確に表現する必要がある状態。
- 社会的コンテキストは他の人の言動や思考を理解し、自分の考えや意図を相手に理解してもらえる環境。
- コンテキストマーケティングとは、マーケティングに取り入れられる１つの考えで、費者の目線から背景事情、思考を読み取ってマーケティング活動を行うこと。
- コンテキストメニューはソフトウェアの操作メニューを表示させる方法で、選択している操作対象に合わせてメニュー項目が変化するプログラムです。

---

### 構成要素

```plantuml
@startmindmap

* コンテキス
** 構成要素
*** 文脈
**** 前提条件
*** 状況
**** 短期的な結果
**** 長期的な結果

@endmindmap
```

---

#### 文脈

```plantuml
@startmindmap

* コンテキス
** 文脈
*** 前提条件
**** assumption

@endmindmap
```

- コンテキストは、明示的または暗黙の前提を指す。
- コンテキストは、言葉では伝わりにくいまたは言語化が難しい概念を指す。

> このような「当然正しい」と考えられている事柄をー明言されていようといまいとー英語ではアサンプション(assumption)と言います。
>
> — 論理的に考える方法 小野田博一（著）日本実業出版社

---

##### プログラマのコンテキスト

XP(エクストリームプログラミング)

JTC(ジャパニーズトラディショナルカンパニー)

```plantuml
@startuml

component アジャイル {

	component XP {
		object "顧客" as z
		object "プログラマ" as a
		object "分析" as a_1
		object "設計" as a_2
		object "実装" as a_3
		object "テスト" as a_4
		object "運用" as a_5

    z -- a
		a_1 - a
		a - a_2
		a -- a_3
		a -- a_4
		a -- a_5
	}

	component スクラム {
		object "顧客" as z_1
		object "プログラマ" as d_1
		object "スクラムマスター" as d_2
		object "分析" as d_1_1
		object "設計" as d_1_2
		object "実装" as d_1_3
		object "テスト" as d_1_4
		object "運用" as d_1_5

		z_1 -- d_1
    z_1 -- d_2
		d_1_1 - d_1
		d_1 - d_1_2
		d_1 -- d_1_3
		d_1 -- d_1_4
		d_1 -- d_1_5
	}

}


@enduml
```

```plantuml
@startuml

component ウォーターフォール {

	component JTC_A {
		object "顧客" as z_1
		object "プログラマ(PG)" as b_1
		object "システムエンジニア(SE)" as b_2
		object "システムコンサルタント" as b_3
		object "インフラ" as b_4
		object "プロジェクトマネージャー(PM)" as b_5
		object "分析" as b_3_1
		object "設計" as b_2_1
		object "実装" as b_1_1
		object "テスト" as b_1_2
		object "運用" as b_4_1

		z_1 - b_3
		z_1 -- b_5
 
		b_3 -- b_2
		b_2 -- b_1
		b_2 -- b_4

		b_3 - b_3_1
		b_2_1 - b_2
		b_1 -- b_1_1
		b_1 -- b_1_2
		b_4 -- b_4_1

	}

	component JTC_B {
		object "顧客" as z_2
		object "システムエンジニア(SE/PG)" as c_2
		object "システムコンサルタント" as c_3
		object "インフラ" as c_4
		object "プロジェクトマネージャー(PM)" as c_5
		object "分析" as c_3_1
		object "設計" as c_2_1
		object "実装" as c_1_1
		object "テスト" as c_1_2
		object "運用" as c_4_1

		z_2 - c_3
		z_2 -- c_5

		c_3 -- c_2
		c_2 - c_4

		c_3_1 - c_3
		c_2_1 - c_2
		c_2 -- c_1_1
		c_2 -- c_1_2
		c_4 -- c_4_1

	}

}


@enduml
```

---

##### 設計のコンテキスト


```plantuml
@startuml
component 機械工学 {
	object "設計" as b 
	object "CAD" as b_1
	object "CAE" as b_2
	object "CAM" as b_3

  b - b_1
	b -- b_2
	b -- b_3
}

component  ソフトウェア工学 {
	object "設計" as a
	object "デザインパターン" as a_1
	object "アーキテクチャ" as a_2
	object "ドメイン駆動" as a_3

	a - a_1
	a -- a_2
	a -- a_3
}

component UI/UX {
	object "設計" as c
	object "アクセシビリティー" as c_1
	object "ユーザー体験" as c_2

	c - c_1
	c -- c_2
}
@enduml
```

---

#### 状況

```plantuml
@startmindmap

* コンテキス
** 文脈
*** 前提条件
**** ロジカルシンキング
***** 演繹
****** 前提を疑ってかかる
******  仮説をおいて考える
***** 帰納
****** 同質のものを帰納して共通項を見いだす
****** 異質のものを組合わせて帰納する
****** モレな重複なく全てを網羅する
** 状況
*** 短期的な結果
*** 長期的な結果

@endmindmap
```

> コンテキストは何か?
> あらゆるものごとは特定のコンテキスト内で発生します。このため「万能の解決策」などというものは存在ません。「ベストプラクティス」と銘打たれた記事や書籍を考えてみてください。ここで考えるべき質問は「誰にとってベストなのか？」です。前提条件は何で、短期的な結果と長期的な結果は何でしょうか？
>
> 達人プログラマー

---

- 「要はバランス」-> 「コンテキストに依存する」
- 「コンテキストに依存する」-> 暗黙・明示的前提に依存する -> ロジカルシンキング・クリティカルシンキングの適用

##### 演繹

```plantuml
@startuml

title 前提を疑ってかかる

interface "コンテキスト" as A

class "一般論" as B

class "個別論" as C

interface "前提" as D {
}

class "真理" as E

class "取り決め" as F

class "その他" as G


D <- A
D <|-- E
D <|-- F
D <|-- G
A <|-- B
A <|-- C
B -> C : 演繹

@enduml
```


```plantuml
@startuml

title 仮説をおいて考える


interface "コンテキスト" as A 

class "一般論" as B

class "個別論" as C

interface "前提" as D 

interface "仮説" as E

class "仮説A" as F

class "仮説B" as G

class "仮説C" as H

D <- A
E <- D
E <|-- F
E <|-- G
E <|-- H
A <|-- B
A <|-- C
B -> C : 演繹

@enduml
```

---

##### 帰納

```plantuml
@startuml

title 同質のものを帰納して共通項を見いだす

interface "コンテキスト" as A 

class "一般論" as B

class "個別論" as C {
  共通項を見出して帰納する()
}

class "事象" as D

class "事実" as E

A <|-- B
A <|-- C
C -> B : 帰納

C "1" *-- "*" D 

C "1" *-- "*" E 

@enduml
```

```plantuml
@startuml

title 異質のものを組合わせて帰納する

interface "コンテキスト" as A 

class "一般論" as B

class "個別論" as C {
  異質ものを組み合わせて帰納する()
}

class "事象" as D

class "事実" as E

A <|-- B
A <|-- C
C -> B : 帰納

C "1" *-- "*" D 

C "1" *-- "*" E 

@enduml
```

```plantuml
@startuml

title モレなく重複なく全てを網羅する


interface "コンテキスト" as A 

class "一般論" as B

class "個別論" as C {
  + 足し算・引き算で考える()
  + 掛け算で考える()
  + 軸で考える()
  + 枠組みを工夫する()
}

class "事象" as D

class "事実" as E

class "その他" as F

A <|-- B
A <|-- C
C -> B : 帰納

C "1" *-- "*" D 
C "1" *-- "*" E 
C "0..1" o-- "*" F

@enduml
```

---

- 「コンテキストに依存する」-> 言語化が難しい概念に依存する -> ドメイン駆動設計の適用

```plantuml
@startuml

interface "コンテキスト" as A 

class "解決領域" as B

class "問題領域" as C {
}

class "コアドメイン" as D

class "サポートサブドメイン" as E

class "汎用サブドメイン" as F

class "境界付けられたコンテキスト" as G

A <|-- B
A <|-- C
C <-> B : ドメイン駆動設計

C -- D 
C -- E 
C -- F
B -- G

@enduml
```

---

### 具体例

```plantuml
@startmindmap

* コンテキス
** 言語学
*** コミュニケーション状況
**** ハイコンテキスト
**** ローコンテキスト
**** 社会的コンテキスト
** IT
*** コンピューティング
**** 計算資源の使用状況
**** 処理過程
**** 状況によって異なる内容が表示されるメニュー
***** コンテキストメニュー
*** プログラミング
**** 設計
***** 境界付けられたコンテキスト
**** 実装
***** Strategy Pattern
***** Dependency Injection
****** ApplicationContext
** ビジネス
*** 関連データ
**** ビジネスコンテキスト
*** 周辺情報
**** コンテキストマーケティング

@endmindmap
```

> コンテクストあるいはコンテキスト（英: context）は、一般的に「文脈」や「状況」といった意味を持つ英語[1]であり、専門分野では次のような用語や修飾語として使われることがある。
>
>言語学
>コンテキスト (言語使用) - 言語使用、言語変種、談話要約に影響を与えるコミュニケーション状況の関連する制約。
>
> コンピューティング
> コンテキスト (計算機科学) - 計算機科学（情報工学）におけるコンテキストは、何らかのタスクによって使用されるデータの最小セットである。タスクによる計算資源の使用状況などを意味する。
コンテキストスイッチ - プロセスやスレッドの状態を保存したり、後の時点で保存した状態を復元して実行を再開したりすることを可能にするための処理過程。
コンテキストメニュー - グラフィカルユーザーインターフェイス（GUI）において、クリックなどのユーザー操作が実行された状況（位置やタイミングなど）によって異なる内容が表示されうるメニュー。
コンテキストアウェアネス - 世の中の情況を捉える技術や、それらに関する概念。
>
> [Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%B3%E3%83%B3%E3%83%86%E3%82%AF%E3%82%B9%E3%83%88)

> コンテキスト（context）とは、文脈、前後関係、事情、背景、状況などの意味を持つ英単語。ITの分野では、利用者の意図や状況、環境などの総体を表したり、同じ処理や記述でも状況に応じて動作などが異なる場合に、その選択基準となる判断材料や条件などを指す場合が多い。
>
> [IT用語辞典 e-Words](https://e-words.jp/w/%E3%82%B3%E3%83%B3%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88.html)

> context
>
> The setting in which a word or statement appears that determines its meaning. Statements about a model can only be understood in a context.
> (単語や文が現れる設定は、その意味を決定します。モデルについての発言は、コンテキスト内でのみ理解することができます。)
>
> Domain-Driven Design Reference

---

#### プログラミング

##### Strategy Pattern

```plantuml
@startuml

class Context{
    strategy : Strategy
    
    ContextMethod()
}

class Strategy{
    StrategyMethod()
}

class ConcreteStrategy1{
    StrategyMethod()
}

class ConcreteStrategy2{
    StrategyMethod()
}

Context o-right-> Strategy
ConcreteStrategy1 --|> Strategy
ConcreteStrategy2 --|> Strategy

@enduml
```

##### Dependency Injection

Spring Framework

```java
public static void main(final String[] args) {
	MessageSource resources = new ClassPathXmlApplicationContext("beans.xml");
	String message = resources.getMessage("argument.required",
		new Object [] {"userDao"}, "Required", Locale.UK);
	System.out.println(message);
}
```

##### 境界付けられたコンテキスト

> 言葉の意味が一意に決まる範囲を明確にするための設計手法が境界付けられたコンテキストです。１つの言葉に２つの意味があるならば、コンテキストを分けて、２つのユビキタス言語を作ります。つまり、モデルが２つに分かれます。
>
> Software Design 2024年3月号 ドメイン駆動設計[実践]ガイド


```plantuml
@startuml

actor "ドメインエキスパート" as Biz
actor "開発者" as Dev

rectangle "問題領域" {
	component "小売ドメイン" as Biz_1 {
		component "販売" as Biz_1_1
		component "在庫" as Biz_1_2
		component "商品" as Biz_1_4

		Biz_1_1 -- Biz_1_4
		Biz_1_2 -- Biz_1_4
	}
}

Biz --> Biz_1

rectangle "解決領域" {
	component "販売サブドメイン" as Dev_1 {
		component "受注" as Dev_1_1
		component "出荷" as Dev_1_2
		component "商品" as Dev_1_3

		Dev_1_1 -- Dev_1_3
		Dev_1_2 - Dev_1_3
	}
	component "在庫サブドメイン" as Dev_2 {
		component "倉庫" as Dev_2_1
		component "商品" as Dev_2_2

		Dev_2_1 -- Dev_2_2
	}
}

Biz -> (ユビキタス言語)
(ユビキタス言語) <- Dev

(ユビキタス言語) <.. (境界付けられたコンテキスト)  : <<分割>>

Dev --> Dev_1
Dev --> Dev_2

@enduml
```

---

#### ビジネス

> ビジネスコンテキストとは
>
> 「ビジネスコンテキスト」とは、ビジネスの世界における関連データや周辺情報のことである。物事を判断・決定する際の根拠となる主な情報に関連する、言葉では伝わりにくい背景やデータのことをいう。クライアントが明確に発しない言葉の背景や意図、これまでの経緯も「ビジネスコンテキスト」と呼ばれる。
> [weblio](https://www.weblio.jp/content/%E3%82%B3%E3%83%B3%E3%83%86%E3%82%AF%E3%82%B9%E3%83%88)


```plantuml
@startuml

actor "経営者" as Biz
actor "開発者" as Dev

rectangle "問題領域" {
Biz --> (成長戦略・競争戦略・機能戦略)
}
Biz -> (ドメイン)

rectangle "解決領域" {
Dev --> (分析・設計・実装)
}
(ドメイン) <- Dev

(ドメイン) <.. (コンテキスト)  : <<明示・暗黙>>

@enduml
```

---

## まとめ

```plantuml
@startuml

object "結論" as A {
	実践プログラマーにとってコンテキストという概念は
	分析・設計・実装において強力なツールとなる。
}
object "小前提" as B {
	ソフトウェアエンジニアリング
	においてコンテキストは重要である。
	ソフトウェアエンジニアリングを適用する際には
	ビジネスコンテキストを理解することが重要である。
}
object "大前提" as C {
  コンテキストは、
	明示的または暗黙の前提を指す。
  コンテキストは、
	言葉では伝わりにくいまたは言語化が難しい概念を指す。
}
A <-- B
C -> B

object "個別論" as B_1 {
	デザインパターン
}
object "個別論" as B_2 {
	境界付けられたコンテキスト
}
object "個別論" as B_3 {
	ビジネスコンテキスト
}

B <-- B_1
B <-- B_2
B <-- B_3

@enduml
```

---

## 参考文献

- [達人プログラマー(第2版): 熟達に向けたあなたの旅](https://www.amazon.co.jp/%E9%81%94%E4%BA%BA%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%83%BC-%E7%AC%AC2%E7%89%88-%E7%86%9F%E9%81%94%E3%81%AB%E5%90%91%E3%81%91%E3%81%9F%E3%81%82%E3%81%AA%E3%81%9F%E3%81%AE%E6%97%85-David-Thomas/dp/4274226298/ref=pd_sbs_1?pd_rd_w=dGuvs&pf_rd_p=e0138d67-9e5b-487b-a2c3-be9ff3010069&pf_rd_r=FQTQBJZRDASV3DCJPQJB&pd_rd_r=400067c3-dc6c-4e86-966e-79474f3ab44f&pd_rd_wg=oB0uI&pd_rd_i=4274226298&psc=1)

- [エリック・エヴァンスのドメイン駆動設計: ソフトウェアの核心にある複雑さに立ち向かう](https://www.amazon.co.jp/%E3%82%A8%E3%83%AA%E3%83%83%E3%82%AF%E3%83%BB%E3%82%A8%E3%83%B4%E3%82%A1%E3%83%B3%E3%82%B9%E3%81%AE%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E9%A7%86%E5%8B%95%E8%A8%AD%E8%A8%88-Architects%E2%80%99Archive-%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E5%AE%9F%E8%B7%B5-%E3%82%A8%E3%83%AA%E3%83%83%E3%82%AF%E3%83%BB%E3%82%A8%E3%83%B4%E3%82%A1%E3%83%B3%E3%82%B9/dp/4798121967/ref=pd_sbs_d_sccl_3_1/356-2306096-5319855?pd_rd_w=L5FmH&content-id=amzn1.sym.2e3b388a-4d35-4ac5-b8d6-fcf3da7dd6b4&pf_rd_p=2e3b388a-4d35-4ac5-b8d6-fcf3da7dd6b4&pf_rd_r=1NKHNP8T44XBXG9PDCSS&pd_rd_wg=jnTGw&pd_rd_r=a2b4fe7c-4a86-4951-9671-c1d187bbbd44&pd_rd_i=4798121967&psc=1)

- [実践ドメイン駆動設計](https://www.amazon.co.jp/%E5%AE%9F%E8%B7%B5%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E9%A7%86%E5%8B%95%E8%A8%AD%E8%A8%88-%E3%83%B4%E3%82%A1%E3%83%BC%E3%83%B3%E3%83%BB%E3%83%B4%E3%82%A1%E3%83%BC%E3%83%8E%E3%83%B3-ebook/dp/B00UX9VJGW/ref=sr_1_5?__mk_ja_JP=%E3%82%AB%E3%82%BF%E3%82%AB%E3%83%8A&crid=1T53TNE006CFM&dib=eyJ2IjoiMSJ9.dQZNgmi1PxWGA58xomliOWakWkdl5tkC6dv8PiuW7vgD91AlcpaPQpDTJGUzR5gq0h2DqLHLUT8dY21yCmYO2SEcBrhW8OW9IIFg1FjrN8jDfKJ3vQa2QyC-LFsLYzXghNPmM3tEiOhPeRha35MSx6SPph5NBydJPU0I1dYOR3Ww3-KF0m5i-HvLPZzuc06RDYlPAOFxOavhEc41pRXNLQx1Fmy_Z0041KzlFB0sM26pC8948Bq2hSmUQk8uG2cW7Zi-fjNr-YAVkEnHCfHffDOJRUM2tLIrrZGBWZvYQx4.JnxcYwYUIAGuR4_bows39c1A4KsIE4B3LOfTaqeYN84&dib_tag=se&keywords=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E9%A7%86%E5%8B%95&qid=1713153002&sprefix=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E9%A7%86%E5%8B%95%2Caps%2C163&sr=8-5)

- [Domain-Driven Design Reference](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf)

- [Bounded Context](https://martinfowler.com/bliki/BoundedContext.html)

- [Software Design 2024年3月号](https://gihyo.jp/magazine/SD/archive/2024/202403)