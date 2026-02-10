---
name: layout-fix
description: Marpスライドのレイアウト崩れを検出し自動修正する。
---

# layout-fix

レイアウト修正は以下のステップで行う：

1. サーバー起動（scripts/start-server.sh）
2. スクリーンショット撮影（scripts/take-screenshots.sh）
3. 画像を確認してレイアウト崩れを検出
4. 修正を適用
5. クリーンアップ（scripts/cleanup.sh）

前提: `agent-browser` と `npx` が利用可能であること。
