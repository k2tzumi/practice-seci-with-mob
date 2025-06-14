---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: モブワークによるSECIモデルの実践
info: |
  PHP Conference Japan 2025  
  https://phpcon.php.gr.jp/2025/

# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
addons:
  - '@katzumi/slidev-addon-qrcode'
  - slidev-addon-components
  - slidev-addon-rabbit
---

# モブワークによるSECIモデルの実践
PHP Conference Japan 2025 Jul 19, 2025.  
v0.0.1  
@katzumi(かつみ)

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/k2tzumi/decision-table-implementation-tips" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
layout: two-cols-header
---

# 自己紹介

katzumi（かつみ）と申します。

「障害のない社会をつくる」をビジョンとする「LITALIC（りたりこ）」に所属しています
<a href="https://litalico.co.jp/">
<img src="https://litalico.co.jp/ogp.png" class="w-40" />
</a>

以下のアカウントで活動しています。

::left::

<div class="float-left">
<img src="https://pbs.twimg.com/profile_images/1768978237210935296/idy9J4l6_400x400.jpg" class="rounded-full w-40 mr"/>  
<simple-icons-x /> <a href="https://twitter.com/katzchum">katzchum</a></div>  
<QRCode :width="180" :height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />

::right::

<img src="https://avatars.githubusercontent.com/u/1182787?v=4" class="rounded-full w-40 mr-12"/>

<logos-github-octocat /> [k2tzumi](https://github.com/k2tzumi)  
<simple-icons-zenn /> [katzumi](https://zenn.dev/katzumi)  

<br />

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: two-cols-header
transition: fade-out
---


# お願い 🙏

写真撮影、SNS での実況について

登壇者の励みになるので是非ともご意見やご感想など、フィードバック頂けると助かります mm  
あとでスライドを公開します

::left::

<Transform :scale="2.5">
　　　🙆‍♀📷<ph-projector-screen-chart-light /><br />
　　　🙅‍♂📹💸<br />
　　　🙅📸👨‍👦‍👦<br />
</Transform>

::right::

<br />
<Transform :scale="2">
<fa6-brands-square-x-twitter />
</Transform>
<br />
<a href="https://x.com/search?q=%23phpcon%20%23track5&f=live">#phpcon #track5</a>


<!-- 本セッションでは、撮影やSNS拡散を歓迎しています。ご自由に写真を撮影して、XなどのSNSでシェアしてください。 　　
ただし、以下の点にご注意ください。　　

著作権などの法的な問題を避けるために、スライドや登壇者の写真や動画を無断で商用利用しないでください。　　
他の参加者のプライバシーや迷惑にならないように、撮影や投稿する際には配慮してください。　　
SNSでシェアする際には、ハッシュタグ「#phpcon_nagoya #s」をつけてください。　　
これにより、本セッションの関連情報を簡単に検索できるようになります。 -->

---
layout: default
transition: slide-up
---

# はじめに
セッションの概要と目的。お断りとか

* **🙇PHPの直接的な技術トピックは出てきません**  
* **対象となる聴衆**  
モブワークに興味がある（実践している）方・複雑なドメインを扱っている方
* **本セッションの位置づけ**  
技術内容ではなく、チーム開発と知識共有のプロセスに焦点  
5 年間のモブワークの実践を通じて得られた知見に基づきます。
* **本セッションの主な狙い**  
プロジェクトへのモブワーク導入を検討するきっかけの提供

<!--
今日は、PHPのコードの話は出てきません。技術そのものではなく、チームでどう知識を育てていくか、という話です。  
このセッションは、モブワークに興味がある方や、複雑な問題をチームでどう解決するかに悩んでいる方に向けています。
-->

---
layout: statement
transition: fade
---

# モブワーク(Mob Work)
# とは？<v-click>の前に</v-click>

---
layout: statement
---

# モブプログラミング
# (Mob Programming)


---
layout: two-cols-header
---

# モブプログラミングとは
ソフトウェア・チーミングのスタイルの一種

::left::

## 定義
- 2011 年 **Woody Zuill氏** により提唱
  <blockquote>
  <p>「すべての優秀な人材が、同じ時に同じ場所で、同じコンピュータで協力して一つのことに取り組む」</p>
  </blockquote>
- **ペアプログラミング**を拡張
- チームメンバー全員を含めるようにスケールアップ
- 「進化的なステップ」と定義

<br />
<br />
<br />
<br />
<br />

::right::

## 基本的な考え方
チームメンバー全員が  
  **同じコンピュータと画面**を共有し  
  **同じ時間**に  
  **同じ問題**に取り組む
**一つのタスク**に取り組む際は、集中して作業する。

<!--
まずはモブプログラミングから説明します。これは、チーム全員が1つの画面、1つのキーボードで一緒に開発するやり方です。
-->

---
layout: two-cols-header
---

# モブプログラミングにおけるチームの役割分担
ペアプログラミングとほぼ同じ役割分担

::left::

## ドライバー 👨‍💻
<v-clicks>

- **コードを書く**機械的なタイピング作業を担当
- **一人のメンバー**が担当
- **定期的にローテーション**される  
通常 15-30 分で交代
- 指示を受けて実装に集中

</v-clicks>

<br />
<br />
<br />
<br />
<br />
<br />


::right::

## ナビゲーター 🧭
<v-clicks>

- **問題解決を共同で行う**
- **ドライバーに指示**を出す
- **残りのメンバー全員**が担当  
次のドライバーをナビゲーター(1 名)として残りのメンバーをモブと呼ぶ場合もあります
- 戦略的思考と方向性を提供

</v-clicks>

---
layout: center
class: text-center
---

# モブプログラミングの目的

<v-click>

## チームが共同で作業し、共有し、学ぶことを通じて  
## **チーム全体のパフォーマンスを向上させる**

</v-click>

<!--
目的は、全員で学び、共有しながら、チーム全体の力を底上げすることです。
-->

---
layout: default
---

# モブプログラミングの主な利点

<div class="grid grid-cols-2 gap-6 pt-4 -mb-6">

<v-clicks>

- 🤝 **チーム内の知識共有の促進**  
個人の暗黙知をリアルタイムでチーム全体に共有
- ✨ **コード品質の向上**  
コードレビューをリアルタイムで行い、品質向上
- 📚 **メンバーの学習機会の促進**  
チーム全体での学習と成長を促進
- 💡 **問題解決能力の向上**  
熟練者の思考プロセスや判断基準に触れる
</v-clicks>

<v-clicks>

- 🔄 **属人性の解決**  
チーム全体として理解を深める
- ⚡ **コードレビューコストの低減**  
実装が完了したらマージ Ready な状態となる
- 🚀 **新規メンバーのオンボーディングのスムーズ化**  
リアルタイムでの実践的な学習、即時フィードバック・密な対話を通じたチームへの自然な参加
- 🛡️ **開発中のハマり防止**  
問題を一人で抱え込まない。多様な視点と専門知識を結集して問題を解消する
</v-clicks>

</div>

<v-click>

<div class="pt-8">
  <div class="bg-blue-50 border-l-4 border-blue-400 p-4 rounded">
    <p class="text-blue-700 font-semibold">
      これらの利点により、チーム全体のパフォーマンスが向上します
    </p>
  </div>
</div>

</v-click>

<!--
例えば、知識の共有、コード品質の向上、新メンバーのスムーズな参加など、モブの利点はたくさんあります。
-->

---
layout: statement
transition: fade
---

# モブワーク(Mob Work)
話を戻します

---

# モブプログラミングとモブワークの違い
チームの集合知を活用し、知識共有とコラボレーションを促進する点では共通

* **モブワークの適用範囲**  
  * 工程: 要件定義、設計、製造、テスト、運用保守
  * 業務: 文書作成、設計、企画、分析など、プログラミングも含む様々な業務
* **モブワークの成果物**  
コードも含む多様な成果物 （企画書、設計図、プレゼンテーション資料、ログ調査結果など）
* **モブワークのメンバー**  
開発者に限定されない。プロダクトオーナー、テスター、UI/UX スタッフも参加可能
* **モブワークが扱う問題**  
問題自体が曖昧で、解決方法も複数存在  
逆にモブプログラミングは、問題設定、制約条件、解決手順が明確


<br />

<v-clicks>

<div class="fusen">
プログラミングに限った話ではないので、以降はモブワークとしてお話します
</div>

</v-clicks>

<!--
モブ“ワーク”は、プログラミングに限らず、設計や企画、分析にも使えるアプローチです。
-->

---
layout: two-cols-header
---

# モブワークにおける効率に対する考え方
大勢で1つの仕事に取り組む場合、非効率と考えられがちである。

::left::

<v-click>

## ❌ リソース効率
- **個人の稼働率を最大化**  
「忙しく働いているか？」
- 個別最適化に焦点
- 従来の考え方

</v-click>

<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />

::right::

<v-click>

## ✅ フロー効率
- **価値提供までの時間を最小化**  
「価値を早く届けられるか？」
- 全体最適化に焦点
- **モブプログラミングが重視**  
  - 手戻りの削減
  - 待ち時間の解消
  - 品質問題の早期発見

</v-click>

<!--
個人の稼働率を重視する“リソース効率”より、価値を早く届ける“フロー効率”が大切です。
-->

---
layout: two-cols-header
---

# モブワークが解決する「隠れた非効率」
中長期的な視点（バグ修正、仕様変更、ナレッジ共有に係るコスト）が重要


**🐛 品質問題のコスト**  
- バグ修正：発見が遅れるほど修正コストが指数的に増加
- リファクタリング：品質ばらつきによる技術的負債の蓄積のスピード増加
- 障害対応：知識のサイロ化。初動遅れによる復旧コスト増加

::left::

**🔄 コミュニケーションコスト**  
- コードレビュー：非同期レビューの往復時間
- 質問・相談：「今、時間ありますか？」の積み重ね
- 引き継ぎ：担当者変更時の学習コスト

::right::

**🎯 意思決定コスト**  
- 設計の迷い：一人で悩む時間
- 技術選定：情報収集と検証の重複
- 方針変更：個人判断による手戻り

<!--
モブは、バグ修正やコミュニケーションコスト、意思決定の迷いなど、見えづらいコストを減らすのにも効果的です。
-->

---
layout: center
class: text-center
---

# モブワークまとめ

<v-click>

<div class="text-3xl font-bold mb-8 text-gradient">
「個人 vs タスク」から<br>
「チーム vs 問題」への意識変化
</div>

</v-click>

<v-clicks>

## モブワークが促すもの

🤝 **複数の視点と知識を組み合わせた問題解決**  
📖 **個人の暗黙知をリアルタイムでチーム全体に共有**  
🧠 **知識の偏りを減らし、「部族の記憶」を形成**  
🔄 **属人性のないコード・タスク**  
🌱 **チーム全体での学習と成長を促進**  

</v-clicks>

<style>
.text-gradient {
  background: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<!--
複数の視点を活かして問題を解決し、暗黙知をリアルタイムでチームに共有できます。
-->

---
layout: section
---

# SECIモデル

---

# SECIモデルの概要
4 つのプロセスの頭文字

* **SECI（セキ）モデルとは？**  
個人の知識や経験を組織全体で共有・活用し、新たな知識を創造するサイクル
  - 野中郁次郎（のなか・いくじろう）氏らが提唱した知識創造の理論
  - 暗黙知と形式知の相互変換を通じて知識を創造・発展させる
  - 4つのプロセスを繰り返し螺旋状に発展する「知識スパイラル」

<!--
ここからが本題です。SECIモデルは、知識の流れを“暗黙知”と“形式知”で表した理論です。
-->

---

# 知識創造の4つのプロセス
「暗黙知を形式知に」「形式知を暗黙知に」という変換・移転を繰り返すスパイラル構造

<Transform :scale="0.7">

<img src="/seci-model-diagram.svg" />

</Transform>

<!--
4つのプロセスがあり、螺旋状に知識が発展します。では1つずつ見ていきましょう。
-->

---
layout: two-cols-header
---

# 1. 共同化(Socialization) - 暗黙知の直接共有
共通の体験を通じて暗黙知を移転させるプロセス

- **暗黙知 → 暗黙知への変換プロセス**
  - 言葉だけではなく共通の体験や経験を通じて暗黙知を移転
  - 「見て覚える」「一緒に実践する」による学習

::left::

- **共同化の特徴**  
  - 言語化困難な知識の共有  
  「勘」「感覚」「コツ」といった言葉にできない知識  
  熟練者の思考プロセスや判断基準
  - 体験を通じた学習  
  同じ環境で同じ体験を共有  
  リアルタイムでの相互作用

::right::

- **共同化の具体例**  
  - 伝統的な職人の世界  
  師匠と弟子が一緒に作業  
  技術の「見て盗む」文化
  - ビジネス現場  
  OJT（On-the-Job Training）  
  先輩社員との同行営業

<!--
まずは“共同化”。言葉にできない知識を、一緒に手を動かすことで共有していきます。
-->

---

# モブワークにおける共同化

- **観察と体験の同時進行**  
  - **全員が同じコード・ドキュメントを見ながら作業**
  - ドライバーの思考プロセスをリアルタイムで共有
  - 「なぜこのキーボードショートカットを使うのか」等の微細な技術
- **暗黙知の自然な流出**  
  - **実況（つぶやき）プログラミング**：考えながら声に出すことで暗黙知が表出  
  - 「あ、ここは気をつけないと...」といった無意識の注意点
  - コードを書く際の判断基準や優先順位

<v-clicks>

<div class="box-text-memo">
<b>💡共同化を促進するポイント</b><br />
<li><b>心理的安全性の確保</b>：質問しやすい雰囲気</li>
<li><b>同じ目線</b>での作業：全員が画面を見える環境</li>
<li><b>時間的余裕</b>：急がず観察・体験する時間</li>
<li><b>積極的な参加</b>：受け身ではなく能動的な関与</li>
</div>

</v-clicks>

---

# 2. 表出化(Externalization) - 暗黙知の言語化
個人の暗黙知を言語化し、メンバーと共有するプロセス

- **暗黙知 → 形式知への変換プロセス**  
  - 個人の暗黙知を **言語化・図解化** して他者と共有
  - 「なんとなく分かっている」ことを **明確に説明できる状態** にする
  - 対話や議論を通じて暗黙知を引き出し、形式知として表現
  - 第三者が理解・再現できる状態を作り出す

---
layout: two-cols-header
---

# 2. 表出化(Externalization) - 暗黙知の言語化
個人の暗黙知を言語化し、メンバーと共有するプロセス

::left::

- **表出化の特徴**  
  - **暗黙知の顕在化**  
  無意識に行っていることの意識化  
  「当たり前」と思っていることの明文化  
  個人の経験や判断基準の言語化
  - **共有可能な知識への変換**  
  属人的な知識をチーム資産に変換  
  再現可能な手順やガイドラインの作成  
  知識の標準化と体系化

::right::

- **表出化の具体例**  
  - **ドキュメント化**  
  業務マニュアルの作成  
  設計思想やアーキテクチャの文書化  
  ベストプラクティスの整理  
  FAQ・ナレッジベースの構築
  - **会議・ディスカッション**  
  経験の共有セッション  
  設計レビューでの判断根拠の説明  
  振り返り会議での学びの言語化  
  メンタリングでの知識伝授

<!--
次に“表出化”。考えていることを言葉や図にして共有するプロセスです。“なぜそれを選んだのか”を話すことが大切です。
-->

---
layout: two-cols-header
---

# モブワークにおける表出化

::left::

* **リアルタイム言語化**  
  - **思考の可視化**：「今、こう考えている」の声出し
  - **判断基準の明示**：「この実装を選ぶ理由は...」  
  - **経験談の共有**：「俺みたいになるな！」
* **議論を通じた知識の引き出し**  
  - **Why**：「なぜその方法を選んだのか」
  - **How**：「どう判断をしたのか」
  - **What if**：「もし〜だったらどうするか」
- **その場でのドキュメント作成**  
  - **コードコメント**の充実：実装意図の明記
  - **ADR(Architecture Decision Record)** の作成  
  - README や API ドキュメントの更新
  - 設計図や図解の作成

::right::

<v-clicks>

<div class="box-text-memo">
<b>💡表出化を促進するポイント</b><br />
<li><b>心理的安全性の確保</b>：間違いを恐れずに発言できる</li>
<li><b>適切な質問技法</b>：オープンエンドな質問で深い思考を引き出す</li>
<li><b>言語化しやすい環境</b>：ツールの活用</li>
<li><b>継続的な振り返り</b>：定期的な振り返りセッション</li>
</div>

</v-clicks>


---
layout: two-cols-header
---

# 3. 連結化(Combination) - 形式知の統合と新知識創出
異なる形式知を組み合わせて新たな知を創出するプロセス

::left::

<Transform :scale="0.9">

- **形式知 → 形式知への変換プロセス**  
  - 異なる **形式知を組み合わせ** て新たな知識体系を構築
  - 既存の知識やデータを **統合・再編成** して新しい価値を創出
  - 複数の情報源から **より網羅性・汎用性の高い知識** を生み出す
- **連結化の特徴**  
  - **知識の統合と組み合わせ**  
  異なる分野・専門領域の知識のクロスオーバー  
  複数の解決策やアプローチの比較検討  
  部分的な知識を組み合わせた全体像の構築
  - **新たな知識体系の創出**  
  既存知識の再構成による新しい視点  
  パターンやフレームワークの発見・構築  
  より効率的・効果的な方法論の開発

</Transform>

::right::

- **連結化の具体例**  
  - **データ分析・情報統合**  
  複数のデータソースの分析結果の統合  
  市場調査レポートとユーザーフィードバックの組み合わせ  
  - **知識の体系化**  
  ベストプラクティス集の編集・整理  
  複数のプロジェクト経験の統合
  - **システム・プロセス設計**  
  異なる技術スタックの組み合わせ  
  複数の開発手法のハイブリッド化

<!--
3つ目は“連結化”。すでにある知識や情報を組み合わせて、新しい知を生み出す段階です。
-->

---
layout: two-cols-header
---

# モブワークにおける連結化

::left::

* **多様な知識の即座な統合**  
  - 異なる専門性を持つメンバーの知識の組み合わせ
  - 仮説・根拠の組み合わせから、新しい仮説を立てる
* **リアルタイム知識マッシュアップ**  
  - 異なる意見の組み合わせの検討
  - 設計パターンの組み合わせによる最適解の探索
* **集合知による問題解決**  
  - ブレインストーミング：多角的アイデアの統合
* **振り返りによる新しい気付き**  
  - 「学び」や「反省」を共有して、新しい知識を得る

::right::

<v-clicks>

<div class="box-text-memo">
<b>💡連結化を促進するポイント</b><br />
<li><b>多様性の確保</b>：異なる専門性、経験・背景からの視点の取り入れ</li>
<li><b>リアルタイム情報共有</b>：画面共有、共同編集</li>
<li><b>外部リソース</b>の即座な参照：ドキュメント、リファレンス</li>
<li><b>実験的姿勢</b>失敗を恐れない試行錯誤</li>
</div>

</v-clicks>

---
layout: two-cols-header
---

# 4. 内面化（Internalization）- 形式知の体得と新たな暗黙知の形成
新たに得た形式知を学習により体得するプロセス

::left::

- **形式知 → 暗黙知への変換プロセス**  
  - 形式知を **実践を通じて体得** し、個人の暗黙知として習得
  - マニュアルや手順書を **反復練習** により自然に実行できる状態にする
  - 学習した知識を **自分なりの工夫** と組み合わせて新たな暗黙知を創出
  - 知識の個人化と創意工夫による暗黙知の進化

<br />
<br />
<br />
<br />

::right::

- **内面化の特徴**  
  - **実践による知識の定着**  
  頭で理解し、体で覚えるへの変化。意識的実行から無意識的実行への移行。手順の暗記から直感的な判断への発展。
  - **個人独自の暗黙知の創出**  
  個人の経験と学んだ知識の融合。状況に応じた応用とカスタマイズ。新たな気づきや改善アイデアの発見

<!--
最後に“内面化”。学んだことを実際に手を動かして、自分のスキルとして落とし込むプロセスです。
-->


---
layout: two-cols-header
---

# モブワークにおける内面化

::left::

- **共通した実践体験**  
  - **全員が同じ実践** を通じて同時に内面化
  - **異なる学習速度** を相互にサポート
  - **共通の体験基盤** による暗黙知の共有
- **ローテーションによる深い学習**  
  - **ドライバー交代** により全員が実践を体験
  - **異なる役割** での学習により多角的な理解
  - **教える・教わる** の循環による知識の定着
- **リアルタイムフィードバック**
  - **即座の修正** と **改善提案**
  - **個人の癖** や **思考パターン** の気づき
  - **ベストプラクティス** の自然な習得

<br />

::right::

<v-clicks>

<div class="box-text-memo">
<b>💡内面化を促進するポイント</b><br />
<li><b>観察 → 補助 → 主導</b>の段階的な実践</li>
<li><b>簡単なタスク → 複雑なタスク</b>へのステップアップ</li>
<li><b>振り返りによる意識化</b>: 実践後の振り返りで学びを言語化</li>
<li><b>個人の特性を活かした学習</b>: 個々の学習スタイル及びアプローチ</li>
</div>

</v-clicks>


---
layout: section
---

# SECIモデル4つの場における実践テクニック

---

# SECIモデル4つの場の概要
SECI モデルを支える「場」の重要性

* **🏗️「場」とは何か**
  - 知識創造の各プロセスが効果的に起こる環境である
  - 物理的な場所だけでなく、関係性や文脈も含む
  - 適切な場の設計が知識創造を促進する

<!--
SECIモデルをチームで回すには、それぞれに適した“場”の設計が必要です。
-->

---

# 4つの場の全体像
各 SECI プロセスには、それを最も効果的に実行できる場が存在

| 場 | 対応プロセス | 知識変換 | 主な目的 | 環境特性 |
|---|---|---|---|---|
| **創発場** | 共同化（Socialization） | 暗黙知→暗黙知 | 体験共有・自然な交流 | インフォーマル・リラックス |
| **対話場** | 表出化（Externalization） | 暗黙知→形式知 | 議論・言語化・明文化 | 構造化・目的志向 |
| **システム場** | 連結化（Combination） | 形式知→形式知 | 統合・組み合わせ・創出 | 情報統合・リアルタイム |
| **実践場** | 内面化（Internalization） | 形式知→暗黙知 | 個人実践・体得・習得 | 個人中心・反復練習 |

---
layout: section
---

# モブワークによる効果的なSECIモデル4つの場の設計
場に合わせてモードを切り替える

---
layout: two-cols-header
---

# 1. 創発場 - 「共同化」を促進するモブモード
🌱 自然な暗黙知交換を促すモード

::left::

## 雑談・交流促進モード

- ✅ 信頼関係構築と心理的安全性の醸成
  - 朝会では発声練習も兼ねての雑談
  - 取り扱い説明書
  - フォロワーシップ

## ローテーション・体験共有モード

- ✅ モブタイマーで定期的なロール交代＆休憩  
  - 15-30 分の短サイクルでドライバー交代
  - 全員が同じ体験を共有
  - モブチーム自体の構成もローテーションする

::right::

## 世代交代・継承モード

- ✅ オンボーディング担当の世代交代  
  - 新人指導役を定期的に変更
  - 教える側の学習効果も狙う
  - 多様な視点での知識伝承

<!--
- 特徴: 暗黙知を共有する場、経験の直接共有
- モブワークでの実践:
  - 観察モード: ベテランがドライバーとなり、チームが作業プロセスを観察
  - 体験共有モード: 「このコードを書くときはこう考えている」という思考プロセスの声出し
  - ペアモード: 経験者と未経験者がペアになりながらもチーム全体で共有

-->

---
layout: two-cols-header
---

# 2. 対話場 - 「表出化」を促進するモブモード
💬 暗黙知の言語化を促すモード

::left::

### 振り返り・言語化モード

- ✅ 新しいタスクなど節目での振り返り  
  - 「なぜその判断をしたか」の明確化
  - 学びや気づきの言語化
  - 次に活かせる知識への変換

- ✅ 定期的な振り返り共有  
  - 週次・月次での知識共有セッション
  - 個人の経験をチーム知識に昇華
  - パターンや原則の発見

::right::

### リアルタイム言語化モード

- ✅ その場でのドキュメント作成  
  - コードコメントの充実
  - ADR（Architecture Decision Record）の作成
  - 設計思想の即座文書化

- ✅ 学びの言語化を習慣化  
  - 「今、こう考えている」の声出し
  - 判断根拠の明確化
  - 疑問や不安の言語化

### エキスパート活用モード

- ✅「エキスパート × ビギナー」のコラボ  
  - 初心者の素朴な質問を活用
  - 専門家の暗黙知を引き出す
  - 知識レベルの差を学習機会に


<!--
- 特徴: 暗黙知を言語化し形式知に変換する場
- モブワークでの実践:  
  - 議論モード: チームで設計や実装方針について議論、暗黙知を引き出す質問
  - ドキュメンテーションモード: コードを書きながら同時にコメントやドキュメントを作成
  - 振り返りモード: 「なぜこの実装にしたのか」の理由を言語化する時間を設ける
-->

---
layout: two-cols-header
---

# 3. システム場 - 「連結化」を促進するモブモード
🔄 形式知統合・新知識創出モード

::left::

### 並行チーム・知識統合モード

- ✅ 複数モブワークスチーム運用
  - 同系統タスクを複数チームで並行実施
  - 異なるアプローチの試行
  - 解決策のバリエーション創出

- ✅ 定期的なチームのシャッフル
  - メンバー入れ替えによる知識交差
  - 異なるチームの知見を統合
  - 知識の蒸留効果を促進

::right::

### リアルタイム統合・コラボレーションモード

- ✅ 慣れたらリアルタイム共同編集ツール、リアルタイムコラボレーションツールを活用
  - 複数の情報源を同時参照
  - 異なる形式知の組み合わせ検討
  - 動的な知識統合の実現

<!--
- 特徴: 異なる形式知を組み合わせて新たな知識を創出する場
- モブワークでの実践:  
  - 統合モード: 異なるチームメンバーの知識や経験を組み合わせた実装
  - リファクタリングモード: 既存コードの知識と新しい設計パターンの知識を組み合わせる
  - ワークショップモード: 複数の技術やアプローチを組み合わせる実験的セッション
-->

---

# 4. 実践場 - 「内面化」を促進するモブモード
🏃‍♂️ 個人実践・体得促進モード

### ソロワーク移行モード

- ✅ 積極的にソロワークへの移行を促す
  - モブワーク体験後の個人実践
  - 学んだ知識の個人での咀嚼
  - 自分なりの工夫や改善の発見
  - 個人のペースでの深い学習

### コーチングモード

- ✅　学んだことを自分の言葉で他者に教える機会を設ける
  - 自分の言葉で説明することで、理解が深化する。
  - 既存資料の内容をより分かりやすく見直す。
  - 質問に対する回答力を高める。

<!--
- 特徴: 形式知を暗黙知として体得する場
- モブワークでの実践:  
  - ローテーションモード: 全員がドライバー役を交代し、実践を通じて学びを内面化
  - チャレンジモード: 新しく学んだ技術や知識を実際に適用してみる
  - コーチングモード: 学んだことを自分の言葉で他者に教える機会を設ける
-->

---

# モブワークでSECIモデルを意識的に回す利点

- 各フェーズに合わせてモブワークのモードを切り替えることで、知識創造のサイクルが加速
- チーム全体が同じ経験を共有しながらも、異なる視点や知識を持ち寄ることができる
- 個人の暗黙知をチーム全体の財産に変換するプロセスが自然に組み込まれる
- 新メンバーの受け入れ時にも、知識共有と創造のサイクルに自然に参加できる

---

# 🔄 サイクル全体を通じた工夫

### 段階的モード切替

```
1. 創発場：リラックスした雑談から開始
   ↓
2. 対話場：構造化された振り返りと言語化
   ↓
3. システム場：他チームとの知識統合
   ↓
4. 実践場：個人でのソロワーク実践
   ↓
1. 創発場：個人の体験を持ち寄り（新しいサイクル）
```

### 適応的モード選択  

タスクの性質に応じた場の選択  
チームの状態に応じたモード調整  
学習段階に応じて重点を変更する。

---

# 実践テクニックの効果的な運用

### 📊 各場での成功指標

| 場 | 重視する指標 | 実践テクニック効果 |
|---|---|---|
| 創発場 | 心理的安全性、自然な交流 | 雑談・ローテーションが信頼関係構築| 
| 対話場 | 言語化率、知識の明文化 | 振り返り・ドキュメント化が知識蓄積 |
| システム場 | 知識統合度、新発見 | チーム連携・ツール活用が創発促進 |
| 実践場 | 個人成長、スキル定着 | ソロワーク移行が深い内面化実現 |

### 🎯 統合的な価値創造  
各場での実践テクニックが相互に作用し、  
継続的な知識創造スパイラルを形成

---
layout: section
---

# まとめ

---
layout: two-cols-header
---

# モブワークによるSECIモデルの実践
本セッションの振り返り

::left::

### 🚀 モブワークの価値

- フロー効率重視による全体最適
- 共同作業での集合知活用
- 暗黙知の共有によるリアルタイム学習
- 高品質なアウトプットの実現
- 属人性の排除と知識の民主化

<br />
<br />
<br />
<br />
<br />
<br />

::right::

### 🔄 SECIモデルとの融合

- 暗黙知→形式知→暗黙知への変換スパイラル
- モブワークは4つの「場」に自然に組み込まれる
- タスクの性質やチームの状態に応じたモード切り替え
- 知識創造のスパイラルの継続的な回転

<!--
モブワークをやると、自然とこの4つの“場”が回り始めます。意識せずにSECIが実践できている状態になります。
-->

---
layout: section
---

# 未知への挑戦

---
layout: section
---

# Q. チームで取り組むタスクに対して暗黙知がない状態でもモブワークで取り組むべきか？

---
layout: section
---

# A. 取り組むべき！
ゼロショットでの未知の課題にモブワークで取り組むことは大きなメリットがある

<!--
最初から暗黙知がない、という状況でも大丈夫です。むしろ、モブはそういうときに強いです。
-->

---

# 未知への挑戦でのモブワークの威力
💡 未知の課題に対する集合知

### 🌟 できたてホヤホヤな暗黙知の共有

- 一般的にはプロジェクト初期や試行錯誤段階での未体系化知識の共有は困難
- モブなら：リアルタイムで生まれる知識を即座に共有

### 🧠 学習の加速効果

- 他者との対話が学習を加速する
- **モブがZPD（最近接発達領域）** となる
- 一人では到達できない理解レベルにチーム全体で到達


### ⚡ 知識創造の瞬間を捉える

- ドキュメントでは捉えきれない　**「知識が創造される瞬間」** の共有
- チームが共に考え、発見する機会の創出
- 一緒に知識を獲得していくプロセスの実現

<!--
他の人と一緒にやることで、自分ひとりでは到達できなかったレベルに届ける。これが“ZPD”です。
-->

---

# 未知への挑戦こそSECIモデルの真価

### 🔄 未知の課題でのSECIサイクル

```
創発場：みんなで「分からない」を共有
    ↓
対話場：仮説や気づきをリアルタイムで言語化
    ↓
システム場：仮説ループから得られる断片的な知識を組み合わせる
    ↓
実践場：チームで得た知識を個人で深く理解
```

### 🎯 集合知の力  

多様な視点による死角の解消  
リアルタイム仮説検証による効率的な学習  
共同発見を通じて、深い理解と記憶定着が得られる。

---

# 最後に

### 💫 発展的なモブワーク
**「知っていることを共有する場」** だけでなく  
**「知らないことを一緒に発見する場」** へシフトしていく

### 🌟 SECIモデルが示す道

未知への挑戦こそが  
最も価値ある知識創造の機会

### 🚀 最終メッセージ

「分からない」を恐れず  
チーム全体で新しい挑戦に  
モブワークで立ち向かおう

<!--
分からないことを恐れずに、みんなで一緒に考える。モブワークは、そんな“学びの場”を作るためのツールです。
-->
---

# 参考資料

* [Mob Programming and its impact on the developer's well-being and individual performance](https://www.diva-portal.org/smash/get/diva2:1442517/FULLTEXT01.pdf)
* [Remote Mob Programming](https://www.remotemobprogramming.org/)
* [モブプログラミング入門📖](https://zenn.dev/mossan_hoshi/articles/20230613_mob_programming)
* [組織に“できたてホヤホヤの暗黙知”をシェアする仕組みをどうつくるか？子どもの「逆上がり」習得過程を見て気づいたこと](https://note.com/yuki_anzai/n/nae13ca51dc3e)

<!--
もっと深く知りたい方は、こちらの資料もぜひ見てみてください。
-->