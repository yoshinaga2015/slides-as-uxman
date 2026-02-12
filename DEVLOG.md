# 開発ノート / Dev Log

## スライド生成（Marp）手順メモ

### 最短手順（このリポジトリではこれを使う）

リポジトリルートで実行。

```bash
# HTML
npx -y @marp-team/marp-cli@latest --no-stdin --allow-local-files \
  "Slides/20260212/Slides/deck20260212.md" \
  -o "Slides/20260212/Slides/deck20260212.html"

# PDF（初回はChromiumのDL/起動で時間がかかりがち）
npx -y @marp-team/marp-cli@latest --no-stdin --allow-local-files --pdf \
  "Slides/20260212/Slides/deck20260212.md" \
  -o "Slides/20260212/Slides/deck20260212.pdf"
```

### つまずきポイント

- `npx marp ...` が **stdin待ちで止まる**ことがある → `--no-stdin` を付ける（上のコマンドは付与済み）
- PDF生成は **Chromium起動（初回はDL）** が走るため、HTMLより遅いのは正常

### もう少し速くしたい場合（任意）

- **グローバルに入れる**（`npx` の解決/取得を省ける）

```bash
npm i -g @marp-team/marp-cli
marp --version
```

- 以後は `marp --no-stdin ...` を使う（コマンド形は上と同じ）

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

### フロー比較（dual-flow）の標準化 + 20260212デッキのフロー更新

- **今日やったこと（変更の具体）**
  - `Slides/20260212/Slides/deck.md` の「上下に2本のフローを並べて比較する」レイアウトを、スライド内の `scoped` CSS ではなく共通CSSとして定義し直した
    - `process-flow` と同じ“よく使う部品”として、`.dual-flow` / `.flow-legacy` を共通側に寄せた（`!important` 依存も解消）
  - 上記の標準パターンを `Maker/slides/example.md` と `Maker/docs/style-guide.md` に逆輸入した
    - スタイルガイドに `.dual-flow` / `.flow-legacy` の説明と使用例（HTML）を追加
  - デッキ内のフローを更新した
    - **従来の開発戦術**: `要件` / `仕様設計` / `UI` の後にそれぞれ `議論` を挟み、番号を 1〜9 に振り直し
    - **変化した開発戦術**: 末尾に `6. 実装` を追加
  - 併せて `deck.md` 内の表現を微調整した（見出しやカード文言など）

- **意図**
  - フロー比較レイアウトを“その場しのぎの scoped”にせず、テンプレとして再利用しやすい形に揃えるため。
  - 「議論が何度も挟まる」という現実の進め方をフロー上にも反映して、説明の納得感を上げるため。

## 2026-02-10

### 7ef3646 chore(slides): 20260212デッキ生成物を版管理し、必要アセットを更新

- **今日やったこと（変更の具体）**
  - `Slides/20260212/Slides/deck.md` を `deck20260212.md` にリネームし、登壇用の本文・スタイルを更新した
  - `deck-preview.html` を `deck20260212.html` にリネームし、生成物を最新状態に更新した
  - 配布用の `deck20260212.pdf` を追加した（固定成果物としてコミット）
  - 旧生成物 `deck.html` と、メモ用途だった `deck.md.backup` を削除して二重管理を解消した
  - `CORvideo.gif`（デモ）と `profileBG.png`（背景）を追加し、`sampleUIs.png` を差し替えた
  - 未使用になった `skills/slide-style-rector/SKILL.md` を削除した

- **意図**
  - デッキ本文/生成物/配布物を「日付付き命名」に揃えて、どれが正なのか迷わない状態にするため。
  - 生成物を残しつつも、古い成果物は消して参照先を一本化し、配布や再生成時の事故を減らすため。

### 49b7300 chore(cursor): 共有ガイダンスとSkillsを追跡し、rulesは除外

- **今日やったこと（変更の具体）**
  - `.cursor/AGENTS.md` を追加し、スライド制作における共通ルール（文体など）をリポジトリで共有できるようにした
  - `.cursor/*/SKILL.md` を追加し、スライド制作の補助手順（Skills）をプロジェクトに同梱した
  - `.cursor/README.md` を追加し、「何を追跡し何を追跡しないか」を明文化した
  - `.gitignore` を更新し、`.cursor/**` は原則無視しつつ、共有したいファイルだけ例外で追跡する形に変更した
    - 例外: `AGENTS.md` / `README.md` / `*/SKILL.md`
    - 非追跡: `.cursor/rules/`（秘匿情報が混ざる可能性があるため）

- **意図**
  - Public運用でも、エージェント運用ルールや制作ノウハウは共有しつつ、個人環境・キャッシュ・秘匿情報がコミットされる事故を構造的に防ぐため。

### d9814ae chore(slides): deck20260212の文言調整と生成物更新

- **今日やったこと（変更の具体）**
  - 「アイデアのレベル」スライドの説明文を調整した
    - 強調（太字）と主張は維持しつつ、文章を分割して読みやすくした
    - 「高レベルな方が完成形をイメージできる」を明示し、行動喚起（作らないと上がらない）に繋げた
  - 変更に合わせて `deck20260212.html` / `deck20260212.pdf` を再生成して更新した

- **意図**
  - スライド上で一読して理解できる密度に落とし、主張が流れで伝わるようにするため。
  - 配布物（HTML/PDF）も本文と同期し、差分や混乱が残らないようにするため。

## 2026-02-12

### deck20260212 のHTML/PDF更新手順を明文化（--no-stdin 追加）

- **今日やったこと（変更の具体）**
  - `deck20260212.md` から `deck20260212.html` / `deck20260212.pdf` を再生成して更新した
  - Marp CLI が stdin 待ちで停止するケースがあったため、生成コマンドに `--no-stdin` を入れた
  - 次回からの更新を速く・迷わず行えるよう、本ファイル先頭に「スライド生成（Marp）手順メモ」を追記した

- **意図**
  - 生成物（HTML/PDF）を毎回確実に本文と同期し、配布時の齟齬を防ぐため。
  - “コマンドが止まる/忘れる” をなくし、更新コストと再現性のブレを減らすため。

### deck20260212 の配布物（HTML/PDF）を再生成して同期

- **今日やったこと（変更の具体）**
  - `Slides/20260212/Slides/deck20260212.html` / `deck20260212.pdf` を最新の `deck20260212.md` に合わせて再生成し直した
  - `Slides/20260212/assets/sampleUIs.png` を最新状態に差し替えた（スライド内のUI例が古いままになっていたため）

- **意図**
  - 登壇/配布で参照される成果物（HTML/PDF）と本文の不一致をなくし、閲覧者側の混乱を防ぐため。
  - スライド中の例示画像が意図した最新版になっていることを保証するため。

