
---
marp: true
---

# 実践プログラマー 境界付けられたコンテキスト

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

## 境界付けられたコンテキスト


> モデルが適用されるコンテキストを明示的に定義すること。明示的な境界は、チーム編成、そのアプリケーションに特有の部分が持つ用途、コードベースやデータベーススキーマなどの物理的な表現などの観点から設定すること。ただし、境界の外部の問題によって注意を逸らされたり、混乱させられたりするのを避けること。
>
> エリック・エバンスのドメイン駆動設計

> 別々のモデルの要素が組合わせると、２種類の問題が生じる。それが、重複した概念と偽同族語(false cognate)だ。
>
> エリック・エバンスのドメイン駆動設計

> bounded context
>
> A description of a boundary (typically a subsystem, or the work of a particular team) within which a particular model is defined and applicable.
> (特定のモデルが定義され、適用される境界（通常はサブシステムや特定のチームの作業）の説明。)
>
> Domain-Driven Design Reference

> 忘れてはいけない。境界づけられたコンテキストは明示的な境界であり、ドメインモデルがどこに属するかを表すものである。ドメインモデルは、ユビキタス言語をソフトウエアモデルとして表したものだ。境界を設ける理由は、各モデルの内部的な概念やプロパティ・操作がそれぞれ特別な意味をもつからだ。
>
> 実践ドメイン駆動設計

> それぞれ明確に異なる二つのモデルが、同じ（あるいはよく似た）名前のオブジェク違う意味で使っていることも多い。二つのモデルを明確に境界付けておけば、それぞれのコンテキストにおける意味合いがはっきりする。したがって、境界付けられたコンテキストは主として言語的な境界となる。これらの論点を試金石とすれば、あなたが境界付けられたコンテキストを正しく活用できているかどうかを判断できる。
>
> 実践ドメイン駆動設計


> 言葉の意味が一意に決まる範囲を明確にするための設計手法が境界付けられたコンテキストです。１つの言葉に２つの意味があるならば、コンテキストを分けて、２つのユビキタス言語を作ります。つまり、モデルが２つに分かれます。
>
> Software Design 2024年3月号 ドメイン駆動設計[実践]ガイド

>
> Bounded Context is a central pattern in Domain-Driven Design. It is the focus of DDD's strategic design section which is all about dealing with large models and teams. DDD deals with large models by dividing them into different Bounded Contexts and being explicit about their interrelationships.
> (Bounded Contextは、ドメイン駆動設計の中心的なパターンです。これは、大規模なモデルとチームを扱うためのDDDの戦略設計セクションの焦点です。DDDは、大規模なモデルを異なるBounded Contextに分割し、それらの相互関係を明示することで対処します。)
>
> martin fowler

```plantuml
@startmindmap

* 境界付けられたコンテキスト
** 明示的な境界
*** モデル
**** オブジェクト
**** ドメインモデル
***** ユビキタス言語
** 重複した概念
*** モデル
** 偽同族語
*** モデル

@endmindmap
```

```plantuml
@startuml

actor "ドメインエキスパート" as Biz
actor "開発者" as Dev

rectangle "問題領域" {
	component "小売ドメイン" as Biz_1 {
		component "販売" as Biz_1_1
		component "在庫" as Biz_1_2
		component "プロモーション" as Biz_1_3
		component "商品" as Biz_1_4

		Biz_1_1 -- Biz_1_4
		Biz_1_2 -- Biz_1_4
		Biz_1_3 - Biz_1_4
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

	component "プロモーションサブドメイン" as Dev_3 {
		component "販売促進" as Dev_3_1
		component "広告" as Dev_3_2
		component "パブリックリレーション" as Dev_3_3
		component "顧客" as Dev_3_4
		component "商品" as Dev_3_5

		Dev_3_1 -- Dev_3_5
		Dev_3_2 -- Dev_3_5
		Dev_3_3 -- Dev_3_5
		Dev_3_4 - Dev_3_5
	}
}

Biz -> (ユビキタス言語)
(ユビキタス言語) <- Dev

(ユビキタス言語) <.. (境界付けられたコンテキスト)  : <<分割>>

Dev --> Dev_1
Dev --> Dev_2
Dev --> Dev_3

@enduml
```

```plantuml
@startuml


rectangle "解決領域" {
	component "販売サブドメイン" as Dev_1 {

		component "受注サービス" as Dev_1_1 {
			component "API" as Dev_1_1_1
		}
		component "出荷サービス" as Dev_1_2 {
			component "API" as Dev_1_2_1
		}
		component "商品サービス" as Dev_1_3 {
			component "API" as Dev_1_3_1
		}

		component "UIコンポーネント" as Dev_1_4
		component "DB" as Dev_1_5

		Dev_1_4 --- Dev_1_1_1
		Dev_1_4 --- Dev_1_2_1
		Dev_1_4 --- Dev_1_3_1

		Dev_1_1_1 --- Dev_1_5
		Dev_1_2_1 --- Dev_1_5
		Dev_1_3_1 --- Dev_1_5
	}

@enduml
```

```plantuml
@startuml

rectangle "解決領域" {
	component "在庫サブドメイン" as Dev_2 {

		component "倉庫サービス" as Dev_2_1 {
			component "APP" as Dev_2_1_1
		}
		component "商品サービス" as Dev_2_2 {
			component "UIコンポーネント" as Dev_2_2_1
			component "API" as Dev_2_2_2

			Dev_2_2_1 --- Dev_2_2_2
		}

		component "DB" as Dev_2_5

		Dev_2_1_1 --- Dev_2_5
		Dev_2_2_2 --- Dev_2_5
	}
}

@enduml
```

```plantuml
@startuml

rectangle "解決領域" {
	component "プロモーションサブドメイン" as Dev_3 {

		component "販売促進サービス" as Dev_3_1 {
			component "API" as Dev_3_1_1
		}
		component "広告サービス" as Dev_3_2 {
			component "API" as Dev_3_2_1
		}
		component "パブリックリレーションサービス" as Dev_3_3 {
			component "API" as Dev_3_3_1
		}
		component "顧客サービス" as Dev_3_4 {
			component "UIコンポーネント" as Dev_3_4_1
			component "APP" as Dev_3_4_2
			component "DB" as Dev_3_4_3

			Dev_3_4_1 -- Dev_3_4_2
			Dev_3_4_2 -- Dev_3_4_3
		}
		component "商品サービス" as Dev_3_5 {
			component "UIコンポーネント" as Dev_3_5_1
			component "API" as Dev_3_5_2

			Dev_3_5_1 -- Dev_3_5_2
		}

		component "UIコンポーネント" as Dev_3_6
		component "DB" as Dev_3_7

		Dev_3_6 --- Dev_3_1_1
		Dev_3_6 --- Dev_3_2_1
		Dev_3_6 --- Dev_3_3_1

		Dev_3_1_1 --- Dev_3_7
		Dev_3_2_1 --- Dev_3_7
		Dev_3_3_1 --- Dev_3_7
		Dev_3_5_2 --- Dev_3_7
	}
}

@enduml
```

## まとめ

```plantuml
@startuml

object "結論" as A {
}
object "小前提" as B {
}
object "大前提" as C {
}
A <-- B
C -> B

object "個別論" as B_1 {
}
object "個別論" as B_2 {
}
object "個別論" as B_3 {
}
object "個別論" as B_4 {
}
object "個別論" as B_5 {
}

B <-- B_1
B <-- B_2
B <-- B_3
B <-- B_4
B <-- B_5

@enduml
```
