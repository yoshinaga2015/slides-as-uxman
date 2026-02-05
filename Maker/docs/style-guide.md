# スライドスタイルガイド

## デザイン哲学
- 美麗でシンプル：情報過多を避け、視覚的にクリーン
- 色数制限：グレースケール基調に限定的なアクセントカラー
- 可読性重視：フォントサイズと余白を適切に
- 一貫性：パターンの繰り返しで理解しやすく

## カラーパレット

### 重要なルール

1スライドあたりアクセントカラーは1-2色まで

### プライマリグラデーション
```css
background: linear-gradient(to right, #0536AF, #3163E3);
```
- タイトルスライド、セクション開始、強調スライドに使用

**実装メモ**:
- 引用スライドのボーダーなど、アクセント色は `var(--color-primary)` を優先（色の一貫性のため）

### グレースケール
- `gray-50`: #F9FAFB - パネル背景（淡い）
- `gray-100`: #F3F4F6 - パネル背景（やや濃い）
- `gray-600`: #4B5563 - サブテキスト
- `gray-700`: #374151 - 見出しテキスト
- `gray-800`: #1F2937 - メインテキスト

### アクセントカラー
- ブランド（面・アクセント）: #F4F754（低コントラスト。**極めて大きい要素／極太文字かつ2文字まで**に限定。グラデーションにも使用可）
- ブランド（テキスト用）: #AFAD05（ブランド色をテキストで使いたい場合）
- リンク/強調（明）: #3163E3
- リンク/強調（濃）: #0536AF
- アラート: #FA0715

## タイポグラフィ

### フォントサイズ（スライド用・後列視認性重視）
- タイトル（h1）: 128px（より強い“私らしさ”のため大きく）
- 見出し: 42-52px
- 本文: 24-32px
- サブテキスト: 18-22px

**運用ルール（重要）**:
- 通常スライドのタイトルは **h2（`##`）** を基本とする
- **h1（`#`）は“インパクトを与えたいパターン”のみ**で使用する（例: タイトルスライド / セクション開始 / 全画面背景 / 問いかけ / 中央メッセージ）

**注意**: スライドはWEBページよりも大きなフォントサイズが必要です。後列の聴衆にも見えるよう、十分なサイズを確保してください。

### フォントウェイト
- タイトル（h1）: 900 (Black)
- 見出し（h2）: 700 (Bold)
- 本文: 400 (Regular)
- 強調: 600 (SemiBold)

### ページ数（フッター）
- 等幅フォントを使用（`--font-family-mono`、Noto Sans Mono）
- 数字の幅を揃えるため `font-variant-numeric: tabular-nums;` を併用

### 日本語本文フォント（Google Fonts）
- 日本語には **Zen Kaku Gothic New** を使用する（`--font-family`）
- Marpでは `@import` が効かない/効きにくいケースがあるため、**`@font-face` を `style:` に埋め込む**方式を推奨

### 英数字フォント（Google Fonts）
- 英数字には **Lato** を使用する（`--font-family` の先頭に置き、Zenへフォールバック）

## アクセシビリティ規則

### コントラスト比（WCAG 2.1 AA基準）
- **通常のテキスト**: 4.5:1以上（18px未満、または14pt未満）
- **大きなテキスト**: 3:1以上（18px以上、または14pt以上の太字）
- **UIコンポーネント**: 3:1以上（ボタン、フォーム要素など）

### カラーコントラストの推奨値
- **背景色が濃い場合（#3163E3 / #0536AFなど）**:
  - テキスト色: `#FFFFFF`（white）を明示的に指定
  - h1, h2, h3などの見出しも同様に`color: white`を指定
- **ブランドイエロー（#F4F754）を背景に使う場合**:
  - 原則、**文字を載せない**（載せるなら「極太・2文字まで」を厳守し、`#1F2937` など濃色を使用）
- **背景色が薄い場合（#F9FAFB, #F3F4F6など）**:
  - テキスト色: `#1F2937`（gray-800）以上
  - 見出し: `#374151`（gray-700）以上

### アクセシビリティチェックリスト
- [ ] すべてのテキストが十分なコントラスト比を満たしている
- [ ] 色だけで情報を伝えていない（アイコンやテキストも併用）
- [ ] フォントサイズが適切（最小14px以上推奨）
- [ ] インタラクティブ要素にフォーカス表示がある
- [ ] 画像に代替テキストがある

### リンク（URL）の可読性ルール
HTMLでは **生URLが自動的にリンク（`<a>`）** になるため、既定のスタイルに任せず明示的にコントラストを確保する。

```css
a {
  color: var(--color-link); /* 薄すぎないリンク色 */
  text-decoration: underline;
  text-decoration-thickness: 2px;
  text-underline-offset: 4px;
}
a:visited { color: var(--color-link-strong); }
a:hover { color: var(--color-link-strong); }

/* 暗い背景では白リンクに切り替え */
:where(.panel-strong, .section-start, .title-slide, .fullscreen-background) a {
  color: #FFFFFF;
  text-decoration-color: rgba(255, 255, 255, 0.75);
}
```

### カラーコントラスト計算ツール
- オンラインツール: WebAIM Contrast Checker
- 推奨コントラスト比計算式: (L1 + 0.05) / (L2 + 0.05)
  - L1: 明るい色の相対輝度
  - L2: 暗い色の相対輝度

## 余白・スペーシング

### 基本単位
- 基本単位: 8px
- 小余白: 16px
- 中余白: 24px
- 大余白: 32px
- 特大余白: 48px

### パネル内余白
- パディング: 24-32px
- 要素間隔: 24-32px（スライド用に大きめに設定）

### 見出しとコンテンツ間の余白（重要）
スライドでは、見出しと本文の間に十分な余白が必要です。

- **h1の下**: 32px（本文との間隔）
- **h2の下**: 32px（本文との間隔）
- **h3の下**: 20px（本文との間隔）
- **段落間**: 24px（読みやすさを確保）
- **スライド直下のブロック**: 24px（要素間の適切な間隔。`section > div` のみ）

**注意**: 見出し直後の要素（p, divなど）の上マージンは0に設定し、見出しの下マージンで間隔を確保します。これにより、一貫性のある余白が保たれます。

### リスト内の段落の余白
リスト内の段落（`<p>`要素）のmarginは、通常の段落よりも小さく設定します。

- **リスト内の段落**: `margin-bottom: 8px`
- **リスト内の最後の段落**: `margin-bottom: 0`

これにより、リストの0インデントのテキストの下のmarginが適切に調整され、セーフエリア内に収まります。

### セーフエリア（重要）
スライドの要素がページをはみ出さないよう、セーフエリアを定義します。

#### セーフエリアの定義
- **上部**: タイトルは上部20%以内に配置
- **本文エリア**: 画面の80%以内に収める（上部20% + 本文60%）
- **下部**: 下部10%は空けておく（フッターや装飾用）
- **左右**: 左右5%ずつ余白を確保（合計10%の左右余白）

#### 実装方法
```css
/* セーフエリアの実装例 */
.safe-area {
  max-width: 90%; /* 左右5%ずつ余白 */
  max-height: 80vh; /* 上部20% + 本文60% */
  margin: 0 auto;
  padding: 0 5%;
}
```

#### 画像のサイズ指定
画像がスライドを破壊しないよう、必ずサイズを明示的に指定してください。

```markdown
<!-- ❌ ダメな例 -->
![](huge-image.png)
<!-- 巨大画像がスライドを破壊 -->

<!-- ✅ 良い例 -->
![width:600px](huge-image.png)
<!-- サイズを明示的に指定 -->
```

#### 表のレスポンシブ対応
表は自動的に幅調整されますが、内容が多い場合は改行を入れるか、列数を減らしてください。

```markdown
| 項目 | Before | After |
|:-----|-------:|------:|
| 作成時間 | 30分 | 5分 |
| 見切れ修正 | 15分 | 0分 |
| 合計 | 45分 | 5分 |
```

**注意**: 表の内容が多すぎる場合は、複数のスライドに分割することを検討してください。

#### 表のスタイル定義
表がスライドをはみ出さないよう、以下のスタイルを適用します。

```css
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
```

**実装のポイント**:
- `width: 100%`で表の幅をスライド幅に合わせる
- `max-width: 100%`で最大幅を制限
- `table-layout: fixed`で列幅を均等に分配
- フォントサイズは22px程度（スライド用に大きめ）

## スライドパターン分類

### A. タイトル・セクション系（5種）
1. タイトルスライド - グラデーション背景、中央配置
2. セクション開始 - 章の区切り（インパクト／短文）
3. セクション終了 - 章の締め（見た目を変えて「区切り」を強調）
4. 目次スライド - ナビゲーション用（セクション開始とは見た目・役割を分離）
5. クロージングスライド - 連絡先・QRコード

### B. カラムレイアウト系（8種）
6. 2カラム比較（Before/After）
7. 2カラム対比
8. 3カラムレイアウト（等幅）
9. 3カラム（アクセントカラー）
10. 4カラムレイアウト
11. 5カラム（成熟度レベル）
12. 2x2グリッド
13. 2x3グリッド

### C. 縦並びリスト系（4種）
14. ステップリスト - 番号付き、順序性を強調
15. タイムライン - 時系列の流れ
16. アイコン付きリスト - 視覚的区別
17. チェックリスト - 完了状態の表示

#### アイコン付きリスト（カード型）の実装
アイコン＋短い説明を「カード」として縦に並べるパターンです。**左に円形アイコン、右にタイトル＋本文を縦積み**にします。

```css
.icon-card-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.icon-card {
  display: flex;
  align-items: center;
  gap: 16px;
  margin: 0;
  padding: 20px 24px;
  background: #F9FAFB;
  border: 1px solid #E5E7EB;
  border-radius: 12px;
}
.icon-badge {
  width: 44px;
  height: 44px;
  border-radius: 999px;
  background: rgba(62, 155, 164, 0.14);
  border: 1px solid rgba(62, 155, 164, 0.22);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  line-height: 1;
  flex-shrink: 0;
}
.icon-card-content {
  display: flex;
  flex-direction: column;
  gap: 6px;
}
.icon-card-title {
  font-size: 28px;
  font-weight: 700;
  color: var(--color-heading);
  line-height: 1.25;
}
.icon-card-body {
  font-size: 24px;
  color: var(--color-subheading);
  line-height: 1.5;
}
```

**注意（高さ）**:
- **1スライドに入るのは最大3カードまで**（タイトル込みで高さが足りなくなるため）
- 4枚以上必要なら、**スライド分割**するか、`grid-2col` 等で**2カラム**にする

**実装例**:
```html
<ul class="icon-card-list">
  <li class="icon-card">
    <span class="icon-badge">📝</span>
    <div class="icon-card-content">
      <div class="icon-card-title">シンプル</div>
      <div class="icon-card-body">箇条書き形式で理解しやすい</div>
    </div>
  </li>
</ul>
```

#### チェックリストの実装
チェックリストは完了状態を視覚的に表示するパターンです。HTML形式で実装し、チェックマークとテキストを適切にスタイリングします。

```css
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
```

**実装例**:
```html
<div class="checklist">
  <div class="checklist-item">
    <div class="checklist-checkbox">☑</div>
    <div class="checklist-text">主語（ユーザー/システム）が明記されている</div>
  </div>
  <div class="checklist-item unchecked">
    <div class="checklist-checkbox">☐</div>
    <div class="checklist-text">エラーケースが考慮されている（オプション）</div>
  </div>
</div>
```

**チェックマークの使い分け**:
- **完了項目**: `☑`（四角の中にチェックマーク、緑色）
- **未完了項目**: `☐`（空の四角、グレー）

### D. パネルデザイン系（5種）
18. 基本パネル - グレー背景、シンプル
19. 強調パネル - アクセントカラー使用
20. ガラス風パネル - 半透明、ぼかし効果
21. グラデーションパネル - グラデーション背景
22. ボーダーパネル - 枠線で区別

#### 基本パネルの実装
パネルは情報を視覚的に区別するためのコンテナです。`.panel`クラスを使用します。

```css
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
```

**注意**: 
- パネル要素にはデフォルトで`margin: 0`が設定されています。親要素の`gap`プロパティで間隔を制御してください。
- `border-left`が設定されている場合、左上と左下の`border-radius`は自動的に0になります。これは、左側にボーダーがある場合、角が丸いと見た目が悪くなるためです。

### E. 背景・画像系（4種）
23. 全画面背景 - 全画面に背景色・グラデーション・画像を適用（インパクト重視）
24. 右側配置 - 画像を右側に配置
25. 左側配置 - 画像を左側に配置
26. 引用スライド - 引用文を強調

#### 右側配置 / 左側配置（画像は必須）
- **ルール**: 右側配置 / 左側配置は、必ず片側に**画像（スクリーンショット / 図 / 説明用イメージ）**を配置する  
  - 「画像がない」場合は、このパターンを使わず **パネル（`.panel`）/ カード / リスト**等で情報を組み直す
- **推奨**: 画像は内容理解を助ける説明にする（単なる装飾目的にしない）
- **推奨**: 画像はカラム幅にフィットさせ、角丸・枠線などで「パネル相当のまとまり」を作る（例: `.explain-img` のような共通クラスで統一）

#### 全画面背景の実装
全画面背景はインパクトが必要なパターンです。section要素自体に背景を設定し、余白を最小限にします。

```css
.fullscreen-background {
  padding: 0 !important;
  background: linear-gradient(to right, #0536AF, #3163E3);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.fullscreen-background > * {
  padding: var(--slide-padding);
  max-width: 100%;
}
```
- **padding**: 0（section要素の余白を削除）
- **背景**: section要素に直接設定
- **コンテンツ**: 中央配置で表示
- **コンテンツ内のパディング**: 必要に応じてコンテンツ要素に設定

### F. 強調・特殊系（3種）
27. 統計スライド - 数値を大きく表示
28. 中央配置 - シンプルな中央配置
29. Q&Aスライド - 質問と回答

### G. 応用パターン（10種）
30. QRコード - リンク共有用
31. 問いかけ - 質問で思考を促す
32. まとめ - 要点を整理
33. 企業事例 - ケーススタディ
34. 比較表 - 複数項目の比較
35. プロセスフロー - プロセスの可視化
36. メリット・デメリット - 両面の提示
37. チェックポイント - 確認項目
38. 参考資料 - 参考文献リスト
39. 次回予告 - 続きの案内

## スライド基本スタイル

### section要素の基本設定
```css
section {
  background-color: #FFFFFF;
  color: #1F2937;
  font-family: "Lato", "Zen Kaku Gothic New", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  font-weight: 400;
  font-size: 24px;
  line-height: 1.7;
  box-sizing: border-box;
  padding: 48px;
  position: relative;
}
```
- **パディング**: 48px（基本単位の6倍）で一貫性を保つ
- **行間**: 1.7で可読性を確保
- **フォントサイズ**: 24px（スライド用本文推奨サイズ、後列視認性を考慮）

### 見出しの基本スタイル
```css
h1, h2, h3, h4, h5, h6 {
  font-weight: 700;
  margin: 0;
  padding: 0;
  color: #374151; /* gray-700 */
}
```

#### h1（タイトルスライド用）
```css
h1 {
  font-size: 64px;
  line-height: 1.4;
  font-weight: 700;
  margin-bottom: 32px;
}
```
- タイトルスライドや重要なメッセージに使用
- 必要に応じて80pxまで拡大可能
- スライド用に十分なサイズを確保
- **下マージン**: 32px（本文との適切な間隔）

#### h2（セクション見出し）
```css
h2 {
  font-size: 42px;
  font-weight: 700;
  color: #374151;
  margin-top: 0;
  margin-bottom: 32px;
}
```
- 通常スライドのメイン見出し
- 必要に応じて52pxまで拡大可能
- スライド用に十分なサイズを確保
- **下マージン**: 32px（本文との適切な間隔）

#### h3（サブ見出し）
```css
h3 {
  font-size: 32px;
  font-weight: 600;
  color: #4B5563;
  margin-top: 32px;
  margin-bottom: 20px;
}
```
- スライド用に十分なサイズを確保
- **上マージン**: 32px（前の要素との間隔）
- **下マージン**: 20px（本文との適切な間隔）

### 段落・要素間の余白
```css
p {
  margin-top: 0;
  margin-bottom: 24px;
}

p + p {
  margin-top: 0;
}

/*
  divにグローバルで余白を持たせると、グリッド/フレックス内の「素のdiv」まで
  下方向に膨らみ、フッター衝突や意図しない間延びの原因になる。
  余白は「スライド直下のブロック」だけに限定し、ネストしたレイアウトは gap/padding で制御する。
*/
section > div {
  margin-bottom: 24px;
}
section > div:last-child {
  margin-bottom: 0;
}

/* card/panel内は「余白あり」が基本（ただし直下要素に限定してネスト汚染を防ぐ） */
:where(.panel, .panel-strong, .panel-glass, .panel-gradient, .accent-card, .accent-card-secondary, .card-muted) > div {
  margin-bottom: 24px;
}
:where(.panel, .panel-strong, .panel-glass, .panel-gradient, .accent-card, .accent-card-secondary, .card-muted) > div:last-child {
  margin-bottom: 0;
}

h1 + *,
h2 + *,
h3 + * {
  margin-top: 0;
}
```
- **段落間**: 24px（読みやすさを確保）
- **見出し直後の要素**: マージンなし（見出しの下マージンで間隔を確保）
- **スライド直下のブロック（`section > div`）**: 24pxの下マージン（要素間の適切な間隔）
- **panel/card直下の`div`**: 24pxの下マージン（テキストブロック同士の間隔。ネストしたレイアウトに影響させないため直下に限定。`.accent-card-brand` も対象に含める）

**例外（テキストだけのブロック）**  
短文の説明・ラベル・注釈など、**単独のテキストだけを置く div / p** は余白が不要なため `.text-block` を使用する。  
**ただしパネル内（`.panel` / `.accent-card` / `.card-muted`）では余白が必要**なので、`.text-block` は使わない。
連続する `.text-block` は最小限の間隔（8px）を入れる。

### リストのスタイル
```css
ul, ol {
  padding-left: 32px;
  margin: 16px 0;
}
li {
  margin-bottom: 10px;
  line-height: 1.7;
}
```

## ヘッダー・フッター

### 基本方針
- **フッター**: デフォルトで表示（ロゴとページ数は有用な情報）
- **ヘッダー**: オプション（優先度低）- デフォルトでは非表示、必要に応じて`.with-header`クラスで表示
- **例外**: タイトルスライド、セクション開始スライドなど、特定のクラスではフッターも非表示

### ヘッダー（ページタイトル）【オプション・優先度低】
```css
/* デフォルトでは非表示 */
header {
  display: none;
}

/* .with-headerクラスで表示 */
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
```
- **デフォルト**: 非表示（優先度低のオプション要素）
- **表示方法**: `.with-header`クラスを追加することで表示
- **位置**: スライド上部
- **内容**: ページタイトル（`<header>`要素として明示的に指定）
- **スタイル**: 見出しと同じフォントサイズ、下線で区切り
- **パディング**: 上下均等（16px）でバランスを確保
- **行間**: 1.2でテキストの垂直位置を調整

**推奨**: ヘッダーは通常不要です。スライドの見出し（h1, h2）で十分に情報が伝わります。特別な理由がある場合のみ使用してください。

### フッター（ページ数）
```css
footer {
  position: absolute;
  bottom: 0;
  left: var(--slide-padding);
  right: var(--slide-padding);
  min-height: 60px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  gap: 12px;
  border-top: 2px solid var(--color-hr);
  font-size: var(--font-size-subheading);
  color: var(--color-subheading);
  padding: var(--spacing-small) 0;
  line-height: 1.2;
  isolation: isolate;
}
```
- **パディング**: 上下均等（16px）でバランスを確保
- **行間**: 1.2でテキストの垂直位置を調整

footer::after {
  content: counter(page) ' / ' counter(pages);
  font-weight: 600;
}
```
- **位置**: スライド下部
- **内容**: ページ数（Marpのカウンターを使用）
- **スタイル**: 上線で区切り、サブ見出しサイズのフォント

### コンテンツエリアの調整
```css
section {
  padding-top: var(--slide-padding); /* デフォルト */
  padding-bottom: 100px; /* フッター分の余白 */
}

/* ヘッダーを表示する場合のみ上部パディングを増やす */
.with-header {
  padding-top: 100px;
}
```
- フッターの高さ分、コンテンツエリアの下部パディングを調整
- ヘッダーを表示する場合のみ、上部パディングを追加

### フッターを非表示にするクラス
```css
/* タイトルスライド */
.title-slide footer {
  display: none;
}
.title-slide {
  padding-top: var(--slide-padding);
  padding-bottom: var(--slide-padding);
}

/* セクション開始スライド */
.section-start footer {
  display: none;
}
.section-start {
  /* 章の区切りとして使うため、レイアウトを縦中央寄せにする */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  text-align: left;
  padding-top: var(--slide-padding);
  padding-bottom: var(--slide-padding);
}

/* 目次（ナビゲーション用） */
.toc-slide {
  background: var(--color-background);
  color: var(--color-foreground);
}

/* セクション終了（締め） */
.section-end footer {
  display: none;
}
.section-end {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding-top: var(--slide-padding);
  padding-bottom: var(--slide-padding);
}

/* 明示的にフッターを非表示にするクラス */
.no-footer {
  padding-bottom: var(--slide-padding);
}
.no-footer footer {
  display: none;
}
```

### 使用例

#### 通常のスライド（フッターのみ表示・推奨）
```markdown
## スライドタイトル

コンテンツ...
```
- フッターにロゴとページ数が自動表示
- ヘッダーは表示されない（通常は不要）

#### ヘッダーを表示する場合（オプション）
```markdown
<!-- _class: with-header -->

<header>スライドタイトル</header>

## スライドタイトル

コンテンツ...
```
- `.with-header`クラスを追加することでヘッダーを表示
- ヘッダーの内容は`<header>`要素として明示的に指定
- **推奨**: 通常は不要。特別な理由がある場合のみ使用

#### タイトルスライド（フッター非表示）
```markdown
<!-- _class: title-slide -->

# メインタイトル

サブタイトル
```
- フッターは非表示（ヘッダーはデフォルトで非表示）

#### セクション開始（フッター非表示）
```markdown
<!-- _class: section-start -->

# セクション 1

イントロダクション
```
- フッターは非表示（ヘッダーはデフォルトで非表示）

#### フッターを明示的に非表示
```markdown
<!-- _class: no-footer -->

## フルスクリーンコンテンツ

全画面を使いたい場合
```
- フッターを明示的に非表示（ヘッダーはデフォルトで非表示）

## Marpテーマ設定

### CSS変数定義
```css
@theme default {
  /* Noto Sans Mono（数字用途中心・latin / latin-ext） */
  @font-face {
    font-family: 'Noto Sans Mono';
    font-style: normal;
    font-weight: 400;
    font-stretch: 100%;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/notosansmono/v37/BngcUXNETWXI6LwhGYvaxZikqZqK6fBq6kPvUce2oAZ2evCj.woff2) format('woff2');
    unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  @font-face {
    font-family: 'Noto Sans Mono';
    font-style: normal;
    font-weight: 400;
    font-stretch: 100%;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/notosansmono/v37/BngcUXNETWXI6LwhGYvaxZikqZqK6fBq6kPvUce2oAZ2dPCj7dc.woff2) format('woff2');
    unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }
  @font-face {
    font-family: 'Noto Sans Mono';
    font-style: normal;
    font-weight: 600;
    font-stretch: 100%;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/notosansmono/v37/BngcUXNETWXI6LwhGYvaxZikqZqK6fBq6kPvUce2oAZ2evCj.woff2) format('woff2');
    unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  @font-face {
    font-family: 'Noto Sans Mono';
    font-style: normal;
    font-weight: 600;
    font-stretch: 100%;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/notosansmono/v37/BngcUXNETWXI6LwhGYvaxZikqZqK6fBq6kPvUce2oAZ2dPCj7dc.woff2) format('woff2');
    unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }

  /* カラー */
  --color-background: #FFFFFF;
  --color-foreground: #1F2937;
  --color-heading: #374151;
  --color-subheading: #4B5563;
  --color-brand: #F4F754;
  --color-brand-text: #AFAD05;
  --color-link: #3163E3;
  --color-link-strong: #0536AF;
  --color-alert: #FA0715;
  --color-primary: var(--color-link);
  --color-secondary: var(--color-link-strong);
  --color-hr: var(--color-link-strong); /* 区切り線用 */
  
  /* タイポグラフィ（スライド用・後列視認性重視） */
  --font-family: "Lato", "Zen Kaku Gothic New", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  --font-family-mono: "Noto Sans Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
  --font-size-base: 24px;
  --font-size-title: 128px;
  --font-size-heading: 42px;
  --font-size-subheading: 32px;
  
  /* スペーシング */
  --spacing-base: 8px;
  --spacing-small: 16px;
  --spacing-medium: 24px;
  --spacing-large: 32px;
  --spacing-xlarge: 48px;
  
  /* レイアウト */
  --slide-padding: 48px;
  --line-height-base: 1.7;
  --line-height-heading: 1.4;
}
```

### カスタムクラス

#### 基本クラス
- `.title-slide` - タイトルスライド用（グラデーション背景、中央配置）
- `.section-start` - セクション開始用（グラデーション背景）
- `.section-end` - セクション終了用（締め／セクション開始と見た目を分離）
- `.toc-slide` - 目次用（ナビゲーション／セクション開始と見た目を分離）
- `.panel` - パネル背景（#F9FAFB）
- `.accent` - アクセントカラー適用
- `.center` - 中央配置

#### 装飾クラス（オプション）
- `.decorated-heading` - h2に装飾線を追加
  ```css
  .decorated-heading h2::after {
    content: '';
    display: block;
    width: 60px;
    height: 2px;
    background-color: var(--color-hr);
    margin-top: 8px;
  }
  ```

- `.with-footer` - フッターラインを表示
  ```css
  .with-footer::after {
    content: '';
    position: absolute;
    left: var(--slide-padding);
    right: var(--slide-padding);
    bottom: 40px;
    height: 8px;
    background-color: var(--color-heading);
  }
  ```

- `.with-logo` - ロゴを右上に配置（オプション。表紙/クロージングなど限定用途）
  ```css
  .with-logo::before {
    content: '';
    position: absolute;
    top: 40px;
    right: var(--slide-padding);
    width: var(--logo-size);
    height: var(--logo-size);
    background-image: url('logo.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    background-color: #FFFFFF;
    border-radius: 999px;
    border: 1px solid rgba(17, 24, 39, 0.16);
  }
  ```
  **注意**: ロゴは必要に応じて使用。すべてのスライドに適用しない。

#### レイアウトクラス
- `.lead` - タイトルスライド専用スタイル
  - フッターとロゴを非表示
  - h1のマージンを調整
  - 本文フォントサイズを32pxに（スライド用）

- `.with-header` - ヘッダーを表示（オプション・優先度低）
  - デフォルトでは非表示のヘッダーを表示
  - 特別な理由がある場合のみ使用を推奨
  - `<header>`要素と併用

- `.no-footer` - フッターを明示的に非表示
  - フルスクリーンコンテンツなど、全画面を使いたい場合に使用
  - パディングも通常サイズに戻す

#### パネルユーティリティ
- `.panel-center` - パネル内の中央揃え
- `.panel-large` - パネル内余白を32pxに拡張
- `.panel-compact` - パネル内余白を16pxに縮小
- `.panel-column` - パネル内を縦方向のフレックスに
- `.panel-accent-primary` - 左ボーダーをプライマリ色に
- `.panel-accent-secondary` - 左ボーダーをセカンダリ色に
- `.panel-accent-alert` - 左ボーダーをアラート色に（デメリット/注意の枠）
- `.accent-card` - 上部ラインでアクセント（プライマリ）
- `.accent-card-secondary` - 上部ラインでアクセント（セカンダリ）
- `.accent-card-brand` - 上部ラインでアクセント（ブランドテキスト色 / `--color-brand-text`）
- `.card-muted` - 淡い背景カード
  - **ルール**: ボーダーに接する角の角丸は0にする
  - **推奨**: 上部ライン分だけ `padding-top` を大きめにする（例: 32px）
  - **推奨**: グリッド内では余分な下マージンを付けない（`margin-bottom: 0`）
- `.panel-strong` - 強調パネル（プライマリグラデーション＋白文字）
- `.panel-glass` - ガラス風パネル（半透明＋ぼかし）
- `.panel-gradient` - グラデーションパネル（淡い背景グラデーション）

#### グリッドユーティリティ
- `.grid-2col` - 2カラム（gap: 24px）
- `.grid-2col-gap-32` - 2カラム（gap: 32px）
- `.grid-2col-gap-48` - 2カラム（gap: 48px）
- `.grid-2col-center` - 2カラム中央揃え（gap: 32px）
- `.grid-2col-center-wide` - 2カラム中央揃え（gap: 48px）
- `.grid-3col` - 3カラム（gap: 24px）
- `.grid-3col-fill` - 3カラム（gap: 20px / 高さフィット）
- `.grid-4col` - 4カラム（gap: 16px）
- `.grid-2x3` - 2x3グリッド（gap: 12px）
- `.grid-3x2-compact` - 3x2グリッド（gap: 8px）

#### リストユーティリティ
- `.timeline` - 番号付きのタイムライン（カウンター付き）
- `.icon-card-list` / `.icon-card` - アイコン付きリスト（カード型）

#### スタックユーティリティ
- `.stack-32` - 縦方向に32pxの間隔で配置

#### テキストユーティリティ
- `.text-block` - テキストだけのブロック（下マージンなし）
- `.mb-0` - 下マージンを強制的に0（グリッド内の余計な余白除去など）

#### プロセスフロー
- `.process-flow` - 水平方向のステップフロー
- `.flow-step` - 丸型ステップ番号
- `.flow-label` - ステップ名

#### レベル表示（横並び）
- `.level-strip` - 5カラムを横並びのラベル表示
- `.level-item` / `.level-1`〜`.level-5` - レベル色とボックス
- `.level-title` - レベル名（タイトル、h3相当: 32px）
- `.level-desc` - レベル説明（短文、本文相当: 24px）
  - **推奨**: `level-item` は `padding-top` を大きめ（例: 32px）にして、タイトル上の余白を確保する

#### 統計スライド
- `.stat-slide` - 数字を中心にした統計スライド
- `.stat-number` - 強調数値（大きめ・太字）
- `.stat-title` - 数値の説明タイトル
- `.stat-caption` - 補足説明

#### 問いかけスライド
- `.question-slide` - 問いかけを強調する配置

- `.fullscreen-background` - 全画面背景（インパクト重視）
  - section要素のpaddingを0に設定
  - section要素自体に背景色・グラデーション・画像を設定
  - フッターを自動的に非表示
  - コンテンツは中央配置で表示
  - **使用例**:
    ```markdown
    <!-- _class: fullscreen-background -->
    <style scoped>
    section {
      background: linear-gradient(to right, #0536AF, #3163E3);
    }
    </style>
    
    # タイトル
    コンテンツ...
    ```

## スタイル実装のベストプラクティス

### 1. 一貫性の維持
- 同じレベルの見出しは同じスタイルを使用
- パディングとマージンは基本単位（8px）の倍数で統一
- カラーは定義されたパレットから選択

### 2. アクセシビリティの確保
- すべての見出しに適切なコントラスト比を確保
- 装飾的な要素（::after、::before）は情報伝達に必須でない場合のみ使用
- フッターやロゴは視覚的な補助であり、必須情報ではない

### 3. 柔軟性の確保
- CSS変数を使用してテーマを簡単に変更可能に
- オプションクラスは必要に応じて適用
- 既存のスライドパターンと競合しない設計

### 4. パフォーマンス
- 背景画像は必要最小限に
- 複雑な疑似要素は控えめに使用
- シンプルなスタイルを優先

### 5. 推奨されないパターン
- ❌ h2のabsolute positioning（既存レイアウトと競合）
- ❌ すべてのスライドにフッター/ロゴを強制適用
- ❌ 固定サイズのロゴ配置（calc()は柔軟性に欠ける）
- ❌ 過度な装飾線（情報過多になる可能性）

### 6. 推奨パターン
- ✅ 通常のフローでの見出し配置
- ✅ オプションクラスによる装飾の追加
- ✅ CSS変数による柔軟なテーマ管理
- ✅ シンプルで一貫性のあるスタイル
