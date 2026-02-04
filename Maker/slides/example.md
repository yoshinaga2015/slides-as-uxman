---
marp: true
theme: default
paginate: true
style: |
  /* CSS変数定義 */
  :root {
    --color-background: #FFFFFF;
    --color-foreground: #1F2937;
    --color-heading: #374151;
    --color-subheading: #4B5563;
    --color-primary: #3E9BA4;
    --color-secondary: #1B4565;
    --color-hr: #3E9BA4;
    --font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    --font-size-base: 24px;
    --font-size-title: 64px;
    --font-size-heading: 42px;
    --font-size-subheading: 32px;
    --spacing-base: 8px;
    --spacing-small: 16px;
    --spacing-medium: 24px;
    --spacing-large: 32px;
    --spacing-xlarge: 48px;
    --slide-padding: 48px;
    --line-height-base: 1.7;
    --line-height-heading: 1.4;
  }

  /* section基本スタイル */
  section {
    background-color: var(--color-background);
    color: var(--color-foreground);
    font-family: var(--font-family);
    font-weight: 400;
    font-size: var(--font-size-base);
    line-height: var(--line-height-base);
    box-sizing: border-box;
    padding: var(--slide-padding);
    padding-bottom: 100px; /* フッター分の余白 */
    position: relative;
  }

  /* 見出しの基本スタイル */
  h1, h2, h3, h4, h5, h6 {
    font-weight: 700;
    margin: 0;
    padding: 0;
  }

  h1 {
    font-size: var(--font-size-title);
    line-height: var(--line-height-heading);
    font-weight: 700;
    color: var(--color-heading);
    margin-top: 0;
    margin-bottom: var(--spacing-large);
  }

  h2 {
    font-size: var(--font-size-heading);
    font-weight: 700;
    color: var(--color-heading);
    margin-top: 0;
    margin-bottom: var(--spacing-large);
  }

  h3 {
    font-size: var(--font-size-subheading);
    font-weight: 600;
    color: var(--color-subheading);
    margin-top: var(--spacing-large);
    margin-bottom: 20px;
  }

  /* 段落・要素間の余白 */
  p {
    margin-top: 0;
    margin-bottom: var(--spacing-medium);
  }

  p + p {
    margin-top: 0;
  }

  div {
    margin-bottom: var(--spacing-medium);
  }

  /* 見出し直後の要素は上マージンなし（見出しの下マージンで間隔を確保） */
  h1 + *,
  h2 + *,
  h3 + * {
    margin-top: 0;
  }

  /* リストのスタイル */
  ul, ol {
    padding-left: var(--spacing-large);
    margin: var(--spacing-small) 0;
  }

  li {
    margin-bottom: 10px;
    line-height: var(--line-height-base);
  }

  /* リスト内の段落のmarginを調整 */
  li > p,
  ol > li > p,
  ul > li > p {
    margin-top: 0;
    margin-bottom: 8px;
  }

  /* リスト内の最後の段落のmarginを削除 */
  li > p:last-child,
  ol > li > p:last-child,
  ul > li > p:last-child {
    margin-bottom: 0;
  }

  /* ヘッダー（ページタイトル）【オプション・優先度低】 */
  /* デフォルトでは非表示 */
  header {
    display: none;
  }

  /* .with-headerクラスで表示 */
  .with-header {
    padding-top: 100px; /* ヘッダー分の余白 */
  }

  .with-header header {
    display: flex;
    position: absolute;
    top: 0;
    left: var(--slide-padding);
    right: var(--slide-padding);
    min-height: 60px;
    align-items: center;
    border-bottom: 2px solid var(--color-hr);
    font-size: var(--font-size-heading);
    font-weight: 700;
    color: var(--color-heading);
    padding: var(--spacing-small) 0;
    line-height: 1.2;
  }

  /* フッター（ロゴとページ数） */
  footer {
    position: absolute;
    bottom: 0;
    left: var(--slide-padding);
    right: var(--slide-padding);
    min-height: 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-top: 2px solid var(--color-hr);
    font-size: var(--font-size-subheading);
    color: var(--color-subheading);
    padding: var(--spacing-small) 0;
    line-height: 1.2;
  }

  footer::before {
    content: '';
    width: 180px;
    height: 50px;
    background-image: url('logo.png');
    background-repeat: no-repeat;
    background-size: contain;
    background-position: left center;
  }

  footer::after {
    content: counter(page) ' / ' counter(pages);
    font-weight: 600;
  }

  /* タイトルスライド */
  .title-slide {
    background: linear-gradient(to right, var(--color-secondary), var(--color-primary));
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: var(--slide-padding);
    padding-bottom: var(--slide-padding);
  }

  .title-slide footer {
    display: none;
  }

  .title-slide h1,
  .title-slide h2,
  .title-slide h3 {
    color: white !important;
  }

  /* セクション開始 */
  .section-start {
    background: linear-gradient(to right, var(--color-secondary), var(--color-primary));
    color: white;
    padding-top: var(--slide-padding);
    padding-bottom: var(--slide-padding);
  }

  .section-start footer {
    display: none;
  }

  .section-start h1,
  .section-start h2,
  .section-start h3 {
    color: white !important;
  }

  /* パネル */
  .panel {
    background: #F9FAFB;
    padding: var(--spacing-medium);
    border-radius: 8px;
  }

  /* ユーティリティクラス */
  .accent {
    color: var(--color-primary);
  }

  .center {
    text-align: center;
  }

  /* オプション: 装飾付き見出し */
  .decorated-heading h2::after {
    content: '';
    display: block;
    width: 60px;
    height: 2px;
    background-color: var(--color-hr);
    margin-top: 8px;
  }

  /* オプション: フッターライン */
  .with-footer::after {
    content: '';
    position: absolute;
    left: var(--slide-padding);
    right: var(--slide-padding);
    bottom: 40px;
    height: 8px;
    background-color: var(--color-heading);
  }

  /* タイトルスライドではフッターを非表示 */
  .title-slide.with-footer::after,
  .section-start.with-footer::after {
    display: none;
  }

  /* オプション: ロゴ配置（右上） */
  .with-logo::before {
    content: '';
    position: absolute;
    top: 40px;
    right: var(--slide-padding);
    width: 180px;
    height: 50px;
    background-image: url('logo.png');
    background-repeat: no-repeat;
    background-size: contain;
    background-position: top right;
  }

  /* タイトルスライドではロゴを非表示 */
  .title-slide.with-logo::before,
  .section-start.with-logo::before {
    display: none;
  }

  /* レイアウトクラス: タイトルスライド専用スタイル */
  .lead {
    border-bottom: none;
    padding-top: var(--slide-padding);
    padding-bottom: var(--slide-padding);
  }

  .lead footer,
  .lead header,
  .lead.with-footer::after,
  .lead.with-logo::before {
    display: none;
  }

  .lead h1 {
    margin-bottom: var(--spacing-medium);
  }

  .lead p {
    font-size: 32px;
    color: var(--color-foreground);
  }

  /* フッターを明示的に非表示 */
  .no-footer {
    padding-bottom: var(--slide-padding);
  }

  .no-footer footer {
    display: none;
  }

  /* 全画面背景（インパクト重視） */
  .fullscreen-background {
    padding: 0 !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .fullscreen-background footer {
    display: none;
  }

  .fullscreen-background > * {
    padding: var(--slide-padding);
    max-width: 100%;
  }

  /* パネルの背景色を変数化（オプション） */
  .panel {
    background: #F9FAFB; /* gray-50 */
    margin: 0;
    border-radius: 8px;
  }

  /* border-leftがある時は左上と左下のradiusを削除 */
  .panel[style*="border-left"] {
    border-top-left-radius: 0;
    border-bottom-left-radius: 0;
  }

  /* チェックリストのスタイル */
  .checklist {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .checklist-item {
    display: flex;
    align-items: start;
    gap: 12px;
    margin: 0;
  }

  .checklist-checkbox {
    color: #10B981;
    font-size: 24px;
    margin: 0;
    flex-shrink: 0;
  }

  .checklist-text {
    font-size: 24px;
    color: var(--color-foreground);
    margin: 0;
    line-height: 1.5;
  }

  .checklist-item.unchecked .checklist-checkbox {
    color: #9CA3AF;
  }

  /* 表のレスポンシブスタイル */
  table {
    width: 100%;
    max-width: 100%;
    border-collapse: collapse;
    font-size: 20px;
    margin: 24px 0;
    table-layout: auto;
    word-break: break-word;
  }

  table th,
  table td {
    padding: 10px 12px;
    text-align: left;
    border-bottom: 1px solid #E5E7EB;
    word-wrap: break-word;
    overflow-wrap: break-word;
    hyphens: auto;
  }

  table th {
    font-weight: 600;
    color: var(--color-heading);
    background-color: #F9FAFB;
    white-space: nowrap;
  }

  table td {
    color: var(--color-foreground);
  }

  /* 最初の列（項目）を狭く、後ろの列を広く */
  table th:first-child,
  table td:first-child {
    width: 20%;
    min-width: 100px;
  }

  table th:nth-child(2),
  table td:nth-child(2),
  table th:nth-child(3),
  table td:nth-child(3) {
    width: 40%;
  }
---

<!-- _class: title-slide -->

# 生成AI時代に覚えたい
## ユースケース記述の書き方

Yuki Yoshinaga  
2025年12月29日

---

<!-- _class: section-start -->

# 目次

1. イントロダクション
2. ユースケース記述とは
3. 実例：Mediumのライブラリ機能
4. 生成AIとの相性
5. まとめ

---

<!-- _class: section-start -->

# セクション 1
## イントロダクション

---

# 生成AI時代の開発格差

生成AIが世の中に浸透して、今ではアプリケーションを誰でも開発できるようになったと言われていますよね。

**しかし、その開発速度や精度は、個々人によって大きな格差がある**のが現状です。

---

# セクション 2
## ユースケース記述とは

---

# ユースケース記述とは

**物事が起きる順番に並べた箇条書き形式の作文**

ユーザーとシステムとの対話を叙述的に書きます。

---

# 基本形態

```markdown
# ユースケース1のタイトル
- ユーザーは[XXX]する
- システムは[XXX]する
- ユーザーは[XXX]する
- システムは[XXX]する
```

必ず主語（「ユーザー」「システム」）を明記します。

---

# セクション 3
## 実例：Mediumのライブラリ機能

---


# 2カラム比較：Before/After

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 24px;">

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">Before</h2>
<div style="font-size: 24px; color: #1F2937; margin-bottom: 16px;">
曖昧な指示
</div>
<div style="font-size: 26px; color: #4B5563; font-style: italic;">
「記事をお気に入りできる機能を作って」
</div>

</div>

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">After</h2>
<div style="font-size: 24px; color: #1F2937; margin-bottom: 16px;">
ユースケース記述
</div>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ユーザーは記事を開く</li>
<li>システムは記事を表示する</li>
<li>ユーザーはお気に入りボタンを押す</li>
<li>システムはライブラリ一覧を表示する</li>
</ul>

</div>

</div>

---


# 2カラム対比：ユースケース記述の特徴

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 24px;">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">従来の仕様書</h2>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>技術的詳細が多い</li>
<li>実装方法が混在</li>
<li>読み手の解釈に依存</li>
</ul>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">ユースケース記述</h2>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>シンプルで直感的</li>
<li>順序が明確</li>
<li>主語が明示的</li>
</ul>

</div>

</div>

---


# 3カラムレイアウト：ユースケース記述の要素

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 24px;">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">主語</h2>
<div style="font-size: 26px; color: #1F2937;">
ユーザー  
システム
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">動詞</h2>
<div style="font-size: 26px; color: #1F2937;">
〜する  
〜表示する
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">順序</h2>
<div style="font-size: 26px; color: #1F2937;">
時系列に沿って  
箇条書きで
</div>

</div>

</div>

---


# 3カラム（アクセントカラー）

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 24px;">

<div style="background: #3E9BA4; color: white; padding: 24px; border-radius: 8px;">

<h2 style="color: white; margin: 0 0 24px 0; font-size: 24px; font-weight: 700;">シンプル</h2>
<div style="color: white;">
物事を順序どおりに述べる
</div>

</div>

<div style="background: #F3F4F6; padding: 24px; border-radius: 8px;">

<h2 style="margin: 0 0 24px 0; font-size: 24px; font-weight: 700; color: #374151;">明確</h2>
<div>
主語を必ず書く
</div>

</div>

<div style="background: #3E9BA4; color: white; padding: 24px; border-radius: 8px;">

<h2 style="color: white; margin: 0 0 24px 0; font-size: 24px; font-weight: 700;">実用的</h2>
<div style="color: white;">
AIに渡すだけで実装可能
</div>

</div>

</div>

---


# 4カラムレイアウト：ユースケース記述の利点

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 16px;">

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">シンプル</h3>
<div style="font-size: 24px; color: #4B5563;">
理解しやすい
</div>

</div>

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">明確</h3>
<div style="font-size: 24px; color: #4B5563;">
曖昧さがない
</div>

</div>

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">実用的</h3>
<div style="font-size: 24px; color: #4B5563;">
すぐ使える
</div>

</div>

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">拡張性</h3>
<div style="font-size: 24px; color: #4B5563;">
追加しやすい
</div>

</div>

</div>

---


# 5カラム：成熟度レベル

<div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 12px;">

<div style="background: #F3F4F6; padding: 16px; border-radius: 8px; text-align: center;">

<h3 style="margin: 0 0 4px 0; font-size: 24px; font-weight: 600; color: #374151;">Lv.1</h3>
<div style="font-size: 24px; color: #4B5563;">
基本形
</div>

</div>

<div style="background: #E5E7EB; padding: 16px; border-radius: 8px; text-align: center;">

<h3 style="margin: 0 0 4px 0; font-size: 24px; font-weight: 600; color: #374151;">Lv.2</h3>
<div style="font-size: 24px; color: #4B5563;">
拡張
</div>

</div>

<div style="background: #D1D5DB; padding: 16px; border-radius: 8px; text-align: center;">

<h3 style="margin: 0 0 4px 0; font-size: 24px; font-weight: 600; color: #374151;">Lv.3</h3>
<div style="font-size: 24px; color: #4B5563;">
応用
</div>

</div>

<div style="background: #9CA3AF; padding: 16px; border-radius: 8px; text-align: center; color: white;">

<h3 style="margin: 0 0 4px 0; font-size: 24px; font-weight: 600; color: white;">Lv.4</h3>
<div style="font-size: 24px; color: white;">
高度
</div>

</div>

<div style="background: #3E9BA4; padding: 16px; border-radius: 8px; text-align: center; color: white;">

<h3 style="margin: 0 0 4px 0; font-size: 24px; font-weight: 600; color: white;">Lv.5</h3>
<div style="font-size: 24px; color: white;">
マスター
</div>

</div>

</div>

---


# 2x2グリッド：ユースケース記述の活用場面

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 24px;">

<div class="panel">

<h2 style="margin: 0 0 16px 0; font-size: 24px; font-weight: 700; color: #374151;">開発前</h2>
<div style="font-size: 26px; color: #4B5563;">
要件定義  
仕様書作成
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 16px 0; font-size: 24px; font-weight: 700; color: #374151;">開発中</h2>
<div style="font-size: 26px; color: #4B5563;">
実装指示  
AIへの指示
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 16px 0; font-size: 24px; font-weight: 700; color: #374151;">開発後</h2>
<div style="font-size: 26px; color: #4B5563;">
ドキュメント  
引き継ぎ資料
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 16px 0; font-size: 24px; font-weight: 700; color: #374151;">教育</h2>
<div style="font-size: 26px; color: #4B5563;">
新人研修  
ベストプラクティス
</div>

</div>

</div>

---


# 2x3グリッド：ユースケース記述の実例

<div style="display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: repeat(3, 1fr); gap: 12px;">

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">記事を読む</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
ユーザーは記事を開く
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">お気に入り</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
ユーザーはお気に入りボタンを押す
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">ライブラリ表示</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
システムはライブラリ一覧を表示
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">ライブラリ選択</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
ユーザーはライブラリを選択
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">保存</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
システムは記事を保存
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">完了</h3>
<div style="font-size: 24px; color: #4B5563; margin: 0;">
ユーザーは完了を確認
</div>

</div>

</div>

---


# ステップリスト：記事をお気に入りする

1. **ユーザー**はアプリケーションを開く
2. **システム**は記事一覧を表示する
3. **ユーザー**はいずれかの記事を開く
4. **システム**は当該記事を表示する
5. **ユーザー**は当該記事をお気に入り(Save)する
6. **システム**はライブラリ一覧を表示してユーザーに尋ねる
7. **ユーザー**はライブラリを選択して完了する
8. **システム**は当該ライブラリに記事を追加する

---


# タイムライン：開発プロセス

<div style="display: flex; flex-direction: column; gap: 24px;">

<div style="display: flex; align-items: center; gap: 16px; margin: 0;">
<div style="width: 40px; height: 40px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0;">1</div>
<div style="margin: 0;">ユースケース記述を作成</div>
</div>

<div style="display: flex; align-items: center; gap: 16px; margin: 0;">
<div style="width: 40px; height: 40px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0;">2</div>
<div style="margin: 0;">AIに渡して実装</div>
</div>

<div style="display: flex; align-items: center; gap: 16px; margin: 0;">
<div style="width: 40px; height: 40px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0;">3</div>
<div style="margin: 0;">動作確認・修正</div>
</div>

<div style="display: flex; align-items: center; gap: 16px; margin: 0;">
<div style="width: 40px; height: 40px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0;">4</div>
<div style="margin: 0;">完成</div>
</div>

</div>

---


# アイコン付きリスト：ユースケース記述の特徴

<div style="display: flex; flex-direction: column; gap: 16px;">

<div style="display: flex; align-items: start; gap: 16px; margin: 0;">
<div style="font-size: 24px; margin: 0;">📝</div>
<div style="margin: 0;"><strong>シンプル</strong> - 箇条書き形式で理解しやすい</div>
</div>

<div style="display: flex; align-items: start; gap: 16px; margin: 0;">
<div style="font-size: 24px; margin: 0;">🎯</div>
<div style="margin: 0;"><strong>明確</strong> - 主語を必ず書くため曖昧さがない</div>
</div>

<div style="display: flex; align-items: start; gap: 16px; margin: 0;">
<div style="font-size: 24px; margin: 0;">⚡</div>
<div style="margin: 0;"><strong>実用的</strong> - AIに渡すだけで実装可能</div>
</div>

<div style="display: flex; align-items: start; gap: 16px; margin: 0;">
<div style="font-size: 24px; margin: 0;">🚀</div>
<div style="margin: 0;"><strong>効率的</strong> - 修正指示なしで完成することも</div>
</div>

</div>

---


# チェックリスト：ユースケース記述のチェックポイント

<div class="checklist">

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">主語（ユーザー/システム）が明記されている</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">時系列に沿って順序立てられている</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">箇条書き形式で書かれている</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">技術的詳細が含まれていない</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">読み手が理解しやすい表現になっている</div>
</div>

<div class="checklist-item unchecked">
<div class="checklist-checkbox">☐</div>
<div class="checklist-text">エラーケースが考慮されている（オプション）</div>
</div>

<div class="checklist-item unchecked">
<div class="checklist-checkbox">☐</div>
<div class="checklist-text">代替フローが記載されている（オプション）</div>
</div>

</div>

---


# 基本パネル

<div class="panel">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ユースケース記述の基本形</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
ユースケース記述は、物事が起きる順番に並べた箇条書き形式の作文です。

ユーザーとシステムとの対話を叙述的に書きます。

必ず主語を書くようにします。
</div>

</div>

---


# 強調パネル

<div style="background: linear-gradient(to right, #1B4565, #3E9BA4); color: white; padding: 32px; border-radius: 8px;">

<h2 style="color: white; margin: 0 0 24px 0; font-size: 32px; font-weight: 700;">生成AIとの相性</h2>

<div style="color: white;">
ユースケース記述自体は生成AI時代になって新しく登場したフレームワークではありません。

しかし、生成AIとの相性は**最高の部類**に入ります。
</div>

</div>

---


# ガラス風パネル

<div style="background: rgba(249, 250, 251, 0.8); backdrop-filter: blur(10px); padding: 32px; border-radius: 8px; border: 1px solid rgba(255, 255, 255, 0.5);">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ユースケース記述は「てこ」</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
生成AIを使った開発をより強力にしてくれる「てこ」は、これまでに培われた様々な技術やフレームワークであり、それを知り、用いることが良い生成AI開発につながります。
</div>

</div>

---


# グラデーションパネル

<div style="background: linear-gradient(135deg, #F9FAFB 0%, #E5E7EB 100%); padding: 32px; border-radius: 8px;">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">実例：TODOアプリ</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
以前、ユースケース記述について講義をした時に、ユースケース記述からシンプルなTODOアプリをライブでバイブコーディングしたことがあります。

**注目すべきは、修正指示なしでアプリケーションが出来上がったことです。**
</div>

</div>

---


# ボーダーパネル

<div style="background: #FFFFFF; padding: 32px; border-radius: 8px; border: 2px solid #3E9BA4;">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ユースケース記述の基本形態</h2>

```markdown
# ユースケース1のタイトル
- ユーザーは[XXX]する
- システムは[XXX]する
- ユーザーは[XXX]する
- システムは[XXX]する
```

<div style="font-size: 24px; color: #1F2937; margin-top: 16px;">
これで、あるケースにおける現実世界とシステム内の挙動を端的に表すことが出来ます。
</div>

</div>

---


<!-- _class: fullscreen-background -->
<style scoped>
section {
  background: linear-gradient(135deg, #1B4565 0%, #2A5F7A 50%, #3E9BA4 100%);
  color: white;
  padding: 56px !important;
}

section h1 {
  color: white;
  font-size: 72px;
  font-weight: 800;
  line-height: 1.2;
  margin: 0 0 48px 0;
  letter-spacing: -0.02em;
  text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  text-align: left;
}

section p {
  color: white;
  font-size: 32px;
  line-height: 1.6;
  margin: 0;
  opacity: 0.95;
  font-weight: 300;
  text-align: left;
}
</style>

# 生成AI時代の開発格差

開発速度や精度は、個々人によって大きな格差がある

経験から来る差によって、その差は広がり続けている

---


# 右側配置：実例

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 32px; align-items: center;">

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">記事を読む・お気に入りする</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li><strong>ユーザー</strong>はアプリケーションを開く</li>
<li><strong>システム</strong>は記事一覧を表示する</li>
<li><strong>ユーザー</strong>はいずれかの記事を開く</li>
<li><strong>システム</strong>は当該記事を表示する</li>
<li><strong>ユーザー</strong>は当該記事をお気に入り(Save)する</li>
</ul>

</div>

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 20px 0; font-size: 26px; font-weight: 600; color: #374151;">Mediumのライブラリ機能</h3>

<div style="font-size: 24px; color: #4B5563;">
実例として、Mediumのライブラリ機能をユースケース記述で表現しました。
</div>

</div>

</div>

---


# 左側配置：実装例

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 32px; align-items: center;">

<div class="panel" style="text-align: center;">

<h3 style="margin: 0 0 20px 0; font-size: 26px; font-weight: 600; color: #374151;">GitHubリポジトリ</h3>

<div style="font-size: 24px; color: #3E9BA4; margin-bottom: 16px;">
https://github.com/yoshinaga2015/TODO-App-Sample
</div>

<div style="font-size: 24px; color: #4B5563;">
ユースケース記述からワンショットで作成されたTODOアプリのコードが公開されています。
</div>

</div>

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">実装のポイント</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ユースケース記述をAIに渡す</li>
<li>修正指示なしで完成することも</li>
<li>ゼロから生成AIとアプリケーションを作る場合、必ずチャットで何往復も対話するものと思われていますが、このアプリは最初に1回「これを実装して下さい」と言っただけです。</li>
</ul>

</div>

</div>

---


# 引用スライド

<div style="border-left: 4px solid #3E9BA4; padding-left: 24px; margin: 32px 0;">

> 生成AIにも、上手な使い方とそうでない使い方があります。
>
> 生成AIを使った開発をより強力にしてくれる「てこ」は、これまでに培われた様々な技術やフレームワークであり、それを知り、用いることが良い生成AI開発につながります。
>
> ユースケース記述はそんな「てこ」の1つとして利用できるでしょう。

</div>

---


# 統計スライド

<div class="center" style="padding: 48px 0;">

<div style="font-size: 120px; font-weight: 700; color: #3E9BA4; line-height: 1;">1</div>

<div style="font-size: 48px; color: #374151; margin-top: 24px;">回の指示で完成</div>

<div style="font-size: 24px; color: #6B7280; margin-top: 16px;">修正指示なしでアプリケーションが出来上がった</div>

</div>

---


# 中央配置：シンプルなメッセージ

<div class="center" style="padding: 120px 0;">

# ユースケース記述は「てこ」

生成AI開発を強力にする技術の一つ

</div>

---


# Q&Aスライド

<div style="display: flex; flex-direction: column; gap: 32px;">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">Q. ユースケース記述は誰が書くべき？</h2>

<div style="font-size: 26px; color: #1F2937; line-height: 1.6;">
A. デザイナーやPM、PdMでも書けます。エンジニアでなくても、シンプルな形式なので誰でも作成可能です。
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">Q. 技術的詳細は含めるべき？</h2>

<div style="font-size: 26px; color: #1F2937; line-height: 1.6;">
A. 含めません。ユースケース記述は「何をするか」を記述し、「どう実装するか」は含めません。
</div>

</div>

</div>

---


# QRコード：参考資料

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 48px; align-items: center;">

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">参考資料</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>GitHub: TODO-App-Sample</li>
<li>デモ: https://yoshinaga2015.github.io/TODO-App-Sample/</li>
<li>記事: Medium記事へのリンク</li>
</ul>

</div>

<div class="panel" style="text-align: center; padding: 32px;">

<h3 style="margin: 0 0 24px 0; font-size: 26px; font-weight: 600; color: #374151;">QRコード</h3>

<div style="width: 200px; height: 200px; background: #F3F4F6; margin: 0 auto; display: flex; align-items: center; justify-content: center; border-radius: 8px;">

QR Code

</div>

</div>

</div>

---


<div class="center" style="padding: 80px 0;">

# では、この格差を一気に埋めることのできるフレームワークがあるとしたら？

デザイナーやPMがエンジニア並みに素早くアプリケーションを形にできるとしたら？

</div>

---


# まとめ：要点整理

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 24px;">

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">1. ユースケース記述とは</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
物事が起きる順番に並べた箇条書き形式の作文
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">2. 基本形態</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
主語（ユーザー/システム）を明記し、時系列で記述
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">3. 生成AIとの相性</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
最高の部類。修正指示なしで完成することも
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">4. 活用方法</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
「てこ」として、生成AI開発を強力にする
</div>

</div>

</div>

---


# 企業事例：実装例

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 24px;">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">ケース1：TODOアプリ</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ユースケース記述からワンショットで実装</li>
<li>修正指示なしで完成</li>
<li>GitHubで公開中</li>
</ul>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">ケース2：Mediumライブラリ</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>記事をお気に入りする機能</li>
<li>ライブラリから除外する機能</li>
<li>複数のユースケースで表現</li>
</ul>

</div>

</div>

---


# 比較表：従来手法との比較

| 項目 | 従来の仕様書 | ユースケース記述 |
|:-----|------------|----------------|
| 形式 | 長文・図表 | 箇条書き |
| 主語 | 曖昧 | 明示的 |
| 順序 | 不明確 | 時系列 |
| AIとの相性 | 低い | 高い |
| 作成難易度 | 高い | 低い |
| 理解しやすさ | 中程度 | 高い |

---


# プロセスフロー：開発フロー

<div style="display: flex; align-items: center; padding: 32px 0; gap: 16px;">

<div style="text-align: center; margin: 0; flex: 1; display: flex; flex-direction: column; align-items: center;">
<div style="width: 80px; height: 80px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0 auto 16px;">1</div>
<div style="margin: 0;">要件定義</div>
</div>

<div style="font-size: 32px; color: #3E9BA4; margin: 0; flex: 0 0 auto;">→</div>

<div style="text-align: center; margin: 0; flex: 1; display: flex; flex-direction: column; align-items: center;">
<div style="width: 80px; height: 80px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0 auto 16px;">2</div>
<div style="margin: 0;">ユースケース記述</div>
</div>

<div style="font-size: 32px; color: #3E9BA4; margin: 0; flex: 0 0 auto;">→</div>

<div style="text-align: center; margin: 0; flex: 1; display: flex; flex-direction: column; align-items: center;">
<div style="width: 80px; height: 80px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0 auto 16px;">3</div>
<div style="margin: 0;">AI実装</div>
</div>

<div style="font-size: 32px; color: #3E9BA4; margin: 0; flex: 0 0 auto;">→</div>

<div style="text-align: center; margin: 0; flex: 1; display: flex; flex-direction: column; align-items: center;">
<div style="width: 80px; height: 80px; background: #3E9BA4; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 0 auto 16px;">4</div>
<div style="margin: 0;">完成</div>
</div>

</div>

---


# メリット・デメリット

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 32px;">

<div class="panel" style="border-left: 4px solid #10B981;">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">メリット</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>シンプルで理解しやすい</li>
<li>AIとの相性が良い</li>
<li>誰でも書ける</li>
<li>修正指示が少ない</li>
</ul>

</div>

<div class="panel" style="border-left: 4px solid #EF4444;">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">デメリット</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>エラーケースの記述が弱い</li>
<li>技術的詳細は別途必要</li>
<li>複雑なロジックには不向き</li>
</ul>

</div>

</div>

---


# チェックポイント：ユースケース記述の確認

<div style="display: flex; flex-direction: column; gap: 16px;">

<div style="display: flex; align-items: start; gap: 12px; margin: 0;">
<div style="color: #10B981; font-size: 24px; margin: 0;">✓</div>
<div style="margin: 0;">主語（ユーザー/システム）がすべての項目に含まれている</div>
</div>

<div style="display: flex; align-items: start; gap: 12px; margin: 0;">
<div style="color: #10B981; font-size: 24px; margin: 0;">✓</div>
<div style="margin: 0;">時系列に沿って順序立てられている</div>
</div>

<div style="display: flex; align-items: start; gap: 12px; margin: 0;">
<div style="color: #10B981; font-size: 24px; margin: 0;">✓</div>
<div style="margin: 0;">技術的詳細が含まれていない</div>
</div>

<div style="display: flex; align-items: start; gap: 12px; margin: 0;">
<div style="color: #10B981; font-size: 24px; margin: 0;">✓</div>
<div style="margin: 0;">読み手が理解しやすい表現になっている</div>
</div>

</div>

---


# 参考資料

<div style="display: flex; flex-direction: column; gap: 16px; font-size: 24px;">

1. **ユースケース記述からワンショットでTODOアプリをバイブコーディングする様子**
   - 動画デモ（無音）

2. **GitHubリポジトリ**
   - https://github.com/yoshinaga2015/TODO-App-Sample

3. **デモアプリ**
   - https://yoshinaga2015.github.io/TODO-App-Sample/

4. **Medium記事**
   - 生成AI時代に覚えたい、ユースケース記述の書き方

</div>

---


# 次回予告

<div class="center" style="padding: 80px 0;">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">次回のテーマ</h2>

<h1 style="margin: 0 0 32px 0; font-size: 48px; font-weight: 700; color: #1F2937;">ユースケース記述の実践</h1>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px; text-align: left; display: inline-block;">
<li>より複雑なケースの記述方法</li>
<li>エラーケースの扱い方</li>
<li>チームでの活用方法</li>
</ul>

</div>

---

<!-- _class: section-start -->

# セクション終了
## まとめ

---


# まとめ：ユースケース記述の価値

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px; height: calc(100% - 80px); align-items: stretch;">

<div class="panel" style="display: flex; flex-direction: column;">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">シンプルで強力</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
物事が起きる順番に並べた箇条書き形式の作文
</div>

</div>

<div class="panel" style="display: flex; flex-direction: column;">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">生成AIとの相性</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
最高の部類。修正指示なしで完成することも
</div>

</div>

<div class="panel" style="display: flex; flex-direction: column;">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">誰でも使える</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
デザイナーやPM、PdMでも書ける「てこ」
</div>

</div>

</div>

---

<!-- _class: title-slide -->

# ありがとうございました

## ご質問・ご意見をお待ちしています

Yuki Yoshinaga  
@uxman
