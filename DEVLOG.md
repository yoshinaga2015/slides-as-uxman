# 開発ノート / Dev Log

## 2026-02-04

### 3662326 Update example slides and assets

- **変更の具体**
  - `Maker/slides/example.md` の内容をサンプル文に置換し、目次レイアウトや見出し構成を整理
  - 表紙/クロージングのロゴ配置を「登壇者名の右隣」へ変更し、`logo.png` を追加
  - `Maker/docs/style-guide.md` のフッター/ロゴ記述を現状に合わせて更新
  - `example.html` / `example.pdf` を再生成
  - `Maker/sampleAssets/` にサンプルSVG（`dummy-qr.svg` ほか）を追加
- **意図**
  - サンプルデッキが具体的内容に引きずられず、レイアウト見本として使える状態にするため。

### 3d050c0 Refine example slides and style guide

- **変更の具体**
  - `Maker/slides/example.md` をスタイルガイド準拠で整理（レイアウトのクラス化、リスト構造の修正、フッター被りの調整、用途コメント追記など）
  - `Maker/docs/style-guide.md` にユーティリティ/パターンの定義を追記（グリッド、パネル、リスト、統計、問いかけ等）
  - `Maker/sampleAssets/sam 2.png` を追加し、背景画像サンプルの参照先を更新
  - `example.html` / `example.pdf` を再生成
- **意図**
  - 例示スライドが“スタイルガイドの実装見本”として一貫するようにし、今後の追加・修正時に崩れにくい形にするため。

### 709833a Add Slides deck files

- **変更の具体**
  - ルートにあった資料スライド一式を `Slides/20260212/` 配下で管理するよう追加
    - `Slides/20260212/20250212.md` と関連アセット（`CORLOGO.svg`、`corporateon-ui...webp`、`deskScreen.png`、`sam 1.png`）
- **意図**
  - デッキ単位で素材と本文を同じフォルダにまとめ、配布・再利用・差分管理をしやすくするため。

### d8a0f21 Remove duplicate root assets

- **変更の具体**
  - `Slides/20260212/` に移動済みのため、ルート直下の重複ファイルを削除
    - `CORLOGO.svg`
    - `corporateon-ui.TP3UI4Ue_tfonX.webp`
    - `deskScreen.png`
    - `sam 1.png`
    - `sample.md`
- **意図**
  - 同一アセットの二重管理を避け、参照元を `Slides/` 側へ一本化するため。

## 2026-02-09

### deckカード改善 + 20260212デッキ構成の見直し

- **変更の具体**
  - `Slides/20260212/` の生成物を `Slides/20260212/Slides/` に集約し、アセットは `Slides/20260212/assets/`、SVGは `Slides/20260212/svg/` に整理
    - デッキ側から参照が壊れないよう、`Slides/20260212/Slides/deck.md` / `deck.html` / `deck-preview.html` の相対パスを `../assets/` / `../svg/` に統一
  - 「作ったもの」カードのサムネ画像を実際のスクショへ差し替え
    - `TTMScreenshot00.png` / `AIforResidenceResearch01.png` / `site&discord (1).png`
  - 画像付きカード（`.image-card-thumb`）を基本は **Fit**（`object-fit: contain`）に変更
    - ただし `「頑張る」` のカードグリッドだけは **Fill**（`object-fit: cover`）に戻すため、`image-card-grid-fill` を追加して局所上書き
  - 画像付きカードに **タグ行（caption相当 18px）** を追加し、説明文の下に配置（`.image-card-tag`）
  - 上記の仕様を `Maker/docs/style-guide.md` と `Maker/slides/example.md` / `example.html` にも逆輸入して、今後の再利用の“正”を揃えた
  - `Maker/sampleAssets/` にカード用のサンプル画像を追加（tomato/cucumber/eggplant 等）
  - `.DS_Store` / `.cursor/` をコミット対象から外すため `.gitignore` を追加

- **意図**
  - “生成物の置き場所”と“参照パス”を一貫させて、配布・差分管理・再生成時の事故を減らすため。
  - 画像の見せ方（Fit/Fill）や、カード内の情報階層（タイトル→説明→タグ）をテンプレとして固定し、今後のデッキ制作で迷わないようにするため。

### 未使用画像の整理

- **変更の具体**
  - `Slides/20260212/assets/` から未使用になったサンプル画像（`tomato.png` / `cucumber.png` / `eggplant.png`）を削除
- **意図**
  - 参照されない画像を残さず、配布物とリポジトリのサイズ・混乱を抑えるため。

