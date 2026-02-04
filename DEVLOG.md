# 開発ノート / Dev Log

## 2026-02-04

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

