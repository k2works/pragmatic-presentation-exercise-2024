# Business Model Canvas

<link href="https://fonts.googleapis.com/css2?family=Material+Icons" rel="stylesheet"></link>

<style>
  body {
  display: flex;
  flex-direction: column;
  font-family: sans-serif;
}

.wrapper {
  margin: auto;
  max-width: 960px;
  width: 100%;
}

.bmc {
  display: grid;
  grid: repeat(3, 200px) / repeat(10, 1fr);
}

.bmc,
.bmc > div {
  border: 1px solid;
  background: #fff;
}

.bmc > div {
  display: grid;
  position: relative;
  gap: 10px;
  grid-template-rows: 30px;
  grid-auto-rows: 65px;
  padding: 8px;
}

.bmc > div:nth-child(8),
.bmc > div:nth-child(9) {
  grid: 30px / repeat(5, 1fr);
}
.bmc > div:nth-child(8) h3,
.bmc > div:nth-child(9) h3 {
  grid-column: 1 / -1;
}


.bmc > div:nth-child(8) .note,
.bmc > div:nth-child(9) .note {
  grid-column: span 2;
}

.bmc h3 {
  margin: 0;
  font-size: 14px;
  color: #5b5b5b;
}

.desc {
  font-size: 9px;
  display: flex;
}

.note {
  padding: 15px;
  background: #F33C61;
  color: #fff;
  font-size: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 6px 1px rgba(0,0,0,.2);
}

.note.green {
  background: #79D12A;
}

.bmc > div:nth-child(1),
.bmc > div:nth-child(4),
.bmc > div:nth-child(7) {
  grid-area: span 2 / span 2;
}

.bmc > div:nth-child(2),
.bmc > div:nth-child(5) {
  grid-column: span 2;
}

.bmc > div:nth-child(3) {
  grid-column: 3 / span 2;
  grid-row: 2;
}

.bmc > div:nth-child(6) {
  grid-column: 7 / span 2;
  grid-row: 2;
}

.bmc > div:nth-child(8),
.bmc > div:nth-child(9) {
  grid-area: -2 / span 5;
}
</style>

## HTML

<table>
  <tr>
    <td rowspan="2">
      <i class="material-icons">domain</i>
      <b><a href="Key_Partners.md">主要パートナー</a></b>
      <p>私たちの主要パートナーは誰ですか？<br>
      主要な供給者は誰ですか？<br>
      パートナーが実行する主要な活動は何ですか？</p>
    </td>
    <td>
      <i class="material-icons">work</i>
      <b><a href="Key_Activities.md">主要活動</a></b>
      <p>私たちの価値提案にはどのような主要な活動が必要ですか？<br>
      私たちの流通チャネルは？<br>
      顧客との関係は？<br>
      収益源は？</p>
    </td>
    <td rowspan="2" colspan="2">
      <i class="material-icons">diamond</i>
      <b><a href="Value_Propositions.md">価値提案</a></b>
      <p>私たちは顧客にどのような価値を提供していますか？<br>
      顧客のどの問題を解決していますか？<br>
      各顧客セグメントに対して、どのような製品やサービスのバンドルを提供していますか？<br>
      どの部分が他とは異なり、<br>
      注意を払う価値があるのですか？</p>
      <br><br><br><br><br>
    </td>
    <td>
      <i class="material-icons">handshake</i>
      <b><a href="Customer_Relationships.md">顧客関係</a></b>
      <p>各顧客セグメントが私たちと確立し、維持してほしいと期待する関係のタイプは何ですか？<br>
      どのような関係を確立しましたか？</p>
    </td>
    <td rowspan="2">
      <i class="material-icons">group</i>
      <b><a href="Customer_Segments.md">顧客セグメント</a></b>
      <p>私たちは誰のために価値を創造していますか？<br>
      最も重要な顧客は誰ですか？</p>
    </td>
  </tr>
  <tr>
    <td>
      <i class="material-icons">home</i>
      <b><a href="Key_Resources.md">主要リソース</a></b>
      <p>私たちの価値提案にはどのような主要なリソースが必要ですか？<br>
      私たちの流通チャネルは？<br>
      顧客との関係は？<br>
      収益源は？</p>
    </td>
    <td>
      <i class="material-icons">share</i>
      <b><a href="Channels.md">チャネル</a></b>
      <p>顧客セグメントはどのチャネルを通じて接触を望んでいますか？<br>
      私たちのチャネルはどのように統合されていますか？
      顧客のルーチンとどのように統合されていますか？</p>
    </td>
  </tr>
  <tr>
    <td colspan="3">
      <i class="material-icons">attach_money</i>
      <b><a href="Financial_Plan.md">コスト構造</a></b>
      <p>私たちのビジネスにとって最も重要なコストは何ですか？<br>
      最も高価な主要リソースは何ですか？<br>
      最も高価な主要活動は何ですか？<br>
      ビジネスを設立し、運営するためのコストはどのように発生しますか？</p>
    </td>
    <td colspan="3">
      <i class="material-icons">attach_money</i>
      <b><a href="Financial_Plan.md">収益源</a></b>
      <p>顧客は何の価値に対して支払いをするのですか？ <br>
      彼らはどのように支払いをしたいと考えていますか？ <br>
      収益構造は何ですか？</p>
    </td>
  </tr>
</table>

## CSS

<div class="wrapper">
  <h1>Business Model Canvas</h1>
  <div class="bmc">
    <div>
      <h3>主要パートナー</h3>
      <i class="material-icons">domain</i>
      <div class="desc">
        私たちの主要パートナーは誰ですか？</br>
        主要な供給者は誰ですか？</br>
        パートナーが実行する主要な活動は何ですか？
      </div>
    </div>
    <div>
      <h3>主要活動</h3>
      <i class="material-icons">work</i>
      <div class="desc">
        私たちの価値提案にはどのような主要な活動が必要ですか？</br>
        私たちの流通チャネルは？</br>
        顧客との関係は？</br>
        収益源は？
      </div>
    </div>
    <div>
      <h3>主要リソース</h3>
      <i class="material-icons">home</i>
      <div class="desc">
        私たちの価値提案にはどのような主要なリソースが必要ですか？</br>
        私たちの流通チャネルは？</br>
        顧客との関係は？</br>
        収益源は？
      </div>
    </div>
    <div>
      <h3>価値提案</h3>
      <i class="material-icons">diamond</i>
      <div class="desc">
        私たちは顧客にどのような価値を提供していますか？</br>
        顧客のどの問題を解決していますか？</br>
        各顧客セグメントに対して、どのような製品やサービスのバンドルを提供していますか？</br>
        どの部分が他とは異なり、</br>
        注意を払う価値があるのですか？
      </div>
    </div>
    <div>
      <h3>顧客関係</h3>
      <i class="material-icons">handshake</i>
      <div class="desc">
       各顧客セグメントが私たちと確立し、維持してほしいと期待する関係のタイプは何ですか？</br>
       どのような関係を確立しましたか？
      </div>
    </div>
    <div>
      <h3>チャネル</h3>
      <i class="material-icons">share</i>
      <div class="desc">
        顧客セグメントはどのチャネルを通じて接触を望んでいますか？</br>
        私たちのチャネルはどのように統合されていますか？</br>
        顧客のルーチンとどのように統合されていますか？
      </div>
    </div>
    <div>
      <h3>顧客セグメント</h3>
      <i class="material-icons">group</i>
      <div class="desc">
        私たちは誰のために価値を創造していますか？</br>
        最も重要な顧客は誰ですか？
      </div>
    </div>
    <div>
      <h3>コスト構造</h3>
      <i class="material-icons">attach_money</i>
      <div class="desc">
        私たちのビジネスにとって最も重要なコストは何ですか？</br>
        最も高価な主要リソースは何ですか？</br>
        最も高価な主要活動は何ですか？</br>
        ビジネスを設立し、運営するためのコストはどのように発生しますか？
      </div>
    </div>
    <div>
      <h3>収益源</h3>
      <i class="material-icons">attach_money</i>
      <div class="desc">
        顧客は何の価値に対して支払いをするのですか？ </br>
        彼らはどのように支払いをしたいと考えていますか？ </br>
        収益構造は何ですか？
      </div>
    </div>
  </div>
</div>

```plantuml
@startmindmap
* Business Model Canvas
-- 外部環境
--- 競争
--- 政治・社会・技術
--- マクロ経済
--- 市場
** 内部環境
*** 顧客
**** 顧客セグメント
**** 顧客関係
*** 価値
**** 価値提案
**** チャネル
*** インフラ
**** 主要活動
**** 主要リソース
**** 主要パートナー
*** 資金
**** 収益源
**** コスト構造
@endmindmap
```

[Google Fonts](https://fonts.google.com/icons?selected=Material+Symbols+Outlined:attach_money:FILL@0;wght@400;GRAD@0;opsz@23)
[CodePen Home Business Model Canvas – CSS Grid](https://codepen.io/radioative/pen/NeqdKj)
