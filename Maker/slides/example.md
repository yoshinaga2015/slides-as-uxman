---
marp: true
theme: default
paginate: true
style: |
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

  /* Zen Kaku Gothic New（日本語本文用・Google Fonts） */
  /* latin */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-latin-400-normal.woff2) format('woff2');
    unicode-range: U+0000-00FF,U+0131,U+0152-0153,U+02BB-02BC,U+02C6,U+02DA,U+02DC,U+0304,U+0308,U+0329,U+2000-206F,U+20AC,U+2122,U+2191,U+2193,U+2212,U+2215,U+FEFF,U+FFFD;
  }
  /* japanese */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-japanese-400-normal.woff2) format('woff2');
  }

  /* latin */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 700;
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-latin-700-normal.woff2) format('woff2');
    unicode-range: U+0000-00FF,U+0131,U+0152-0153,U+02BB-02BC,U+02C6,U+02DA,U+02DC,U+0304,U+0308,U+0329,U+2000-206F,U+20AC,U+2122,U+2191,U+2193,U+2212,U+2215,U+FEFF,U+FFFD;
  }
  /* japanese */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 700;
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-japanese-700-normal.woff2) format('woff2');
  }

  /* latin */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 900; /* Black */
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-latin-900-normal.woff2) format('woff2');
    unicode-range: U+0000-00FF,U+0131,U+0152-0153,U+02BB-02BC,U+02C6,U+02DA,U+02DC,U+0304,U+0308,U+0329,U+2000-206F,U+20AC,U+2122,U+2191,U+2193,U+2212,U+2215,U+FEFF,U+FFFD;
  }
  /* japanese */
  @font-face {
    font-family: 'Zen Kaku Gothic New';
    font-style: normal;
    font-weight: 900; /* Black */
    font-display: swap;
    src: url(https://fonts.bunny.net/zen-kaku-gothic-new/files/zen-kaku-gothic-new-japanese-900-normal.woff2) format('woff2');
  }

  /* Lato（英数字用・Google Fonts） */
  /* latin-ext */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6uyw4BMUTPHjxAwXjeu.woff2) format('woff2');
    unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }
  /* latin */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6uyw4BMUTPHjx4wXg.woff2) format('woff2');
    unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  /* latin-ext */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 700;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6u9w4BMUTPHh6UVSwaPGR_p.woff2) format('woff2');
    unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }
  /* latin */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 700;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6u9w4BMUTPHh6UVSwiPGQ.woff2) format('woff2');
    unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }
  /* latin-ext */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 900;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6u9w4BMUTPHh50XSwaPGR_p.woff2) format('woff2');
    unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
  }
  /* latin */
  @font-face {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 900;
    font-display: swap;
    src: url(https://fonts.gstatic.com/s/lato/v25/S6u9w4BMUTPHh50XSwiPGQ.woff2) format('woff2');
    unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
  }

  /* CSS変数定義 */
  :root {
    --color-background: #FFFFFF;
    --color-foreground: #1F2937;
    --color-heading: #374151;
    --color-subheading: #4B5563;
    /*
      Brand palette (UXMAN)
      - Brand yellow is low-contrast: use only for very large/thick elements or <= 2 chars text.
    */
    --color-brand: #F4F754;
    --color-brand-text: #AFAD05;
    --color-link: #3163E3;
    --color-link-strong: #0536AF;
    --color-alert: #FA0715;

    /* Legacy slots (used by many utilities) */
    --color-primary: var(--color-link);
    --color-secondary: var(--color-link-strong);

    /* Dividers / accents */
    --color-hr: var(--color-link-strong);
    --font-family: "Lato", "Zen Kaku Gothic New", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    --font-family-mono: "Noto Sans Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
    --font-size-base: 24px;
    --font-size-title: 128px; /* h1: 2x */
    --font-size-heading: 42px;
    --font-size-subheading: 32px;
    --spacing-base: 8px;
    --spacing-small: 16px;
    --spacing-medium: 24px;
    --spacing-large: 32px;
    --spacing-xlarge: 48px;
    --slide-padding: 48px;
    --logo-size: 44px;
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
    font-weight: 900; /* Black */
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

  /*
    divにグローバルで余白を持たせると、グリッド/フレックス内の「素のdiv」まで
    下方向に膨らみ、フッター衝突や意図しない間延びの原因になる。
    余白は「スライド直下のブロック」だけに限定し、ネストしたレイアウトは gap/padding で制御する。
  */
  section > div {
    margin-bottom: var(--spacing-medium);
  }
  section > div:last-child {
    margin-bottom: 0;
  }

  /* card/panel内は「余白あり」が基本（ただし直下要素に限定してネスト汚染を防ぐ） */
  :where(.panel, .panel-strong, .panel-glass, .panel-gradient, .accent-card, .accent-card-secondary, .accent-card-brand, .card-muted) > div {
    margin-bottom: var(--spacing-medium);
  }
  :where(.panel, .panel-strong, .panel-glass, .panel-gradient, .accent-card, .accent-card-secondary, .accent-card-brand, .card-muted) > div:last-child {
    margin-bottom: 0;
  }

  /* 見出し直後の要素は上マージンなし（見出しの下マージンで間隔を確保） */
  h1 + *,
  h2 + *,
  h3 + * {
    margin-top: 0;
  }

  /* リンク（HTMLでURLが自動リンク化されるため、十分なコントラストを確保する） */
  a {
    color: var(--color-link);
    text-decoration: underline;
    text-decoration-thickness: 2px;
    text-underline-offset: 4px;
  }

  a:visited {
    color: var(--color-link-strong);
  }

  a:hover {
    color: var(--color-link-strong);
  }

  :where(.panel-strong, .section-start, .title-slide, .fullscreen-background) a {
    color: #FFFFFF;
    text-decoration-color: rgba(255, 255, 255, 0.75);
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
    justify-content: flex-start;
    gap: 12px;
    border-top: 2px solid var(--color-hr);
    font-size: var(--font-size-subheading);
    color: var(--color-subheading);
    padding: var(--spacing-small) 0;
    line-height: 1.2;
    isolation: isolate;
  }

  footer::after {
    content: counter(page) ' / ' counter(pages);
    font-weight: 600;
    font-family: var(--font-family-mono);
    font-variant-numeric: tabular-nums;
    margin-left: auto; /* 常に右寄せ */
    color: var(--color-link-strong); /* 黄色化させない */
    mix-blend-mode: normal;
    text-shadow: none;
    text-align: right;
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
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
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

  .section-start h1 {
    font-size: 88px;
    font-weight: 900;
    letter-spacing: -0.02em;
    margin-bottom: 16px;
  }

  .section-start h2 {
    font-size: 48px;
    font-weight: 600;
    opacity: 0.95;
    margin-bottom: 0;
  }

  /* 目次（ナビゲーション用。section-startと役割を分ける） */
  .toc-slide {
    background: var(--color-background);
    color: var(--color-foreground);
  }

  /* 目次専用レイアウト（2カラム、間隔を詰める） */
  .toc-layout {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 140px;
    align-items: start;
  }

  .toc-layout > div:first-child {
    padding-right: 8px;
  }

  .toc-layout > div:last-child {
    padding-left: 8px;
  }

  .toc-title-group {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 5px;
  }

  .toc-title-group h1 {
    font-size: 72px;
    font-weight: 900;
    letter-spacing: -0.02em;
    margin: 0;
    line-height: 1.1;
    text-align: left;
  }

  .toc-title-group h2 {
    font-size: 32px;
    font-weight: 600;
    letter-spacing: 0;
    margin: 0;
    line-height: 1.2;
    color: var(--color-subheading);
    text-align: center;
    align-self: center;
  }

  .toc-title-group + * {
    margin-top: 32px;
  }

  .toc-slide ol {
    margin: 0;
    padding-left: 36px;
    font-size: 32px;
    line-height: 1.55;
  }

  .toc-slide li {
    margin-bottom: 12px;
  }

  /* セクション終了（締め用。section-startと見た目を分ける） */
  .section-end {
    background: linear-gradient(to right, var(--color-primary), var(--color-secondary));
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-top: var(--slide-padding);
    padding-bottom: var(--slide-padding);
  }

  .section-end footer {
    display: none;
  }

  .section-end h1,
  .section-end h2,
  .section-end h3 {
    color: white !important;
  }

  .section-end h1 {
    font-size: 72px;
    font-weight: 900;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
  }

  .section-end h2 {
    font-size: 56px;
    font-weight: 700;
    margin-bottom: 0;
  }

  /* パネル */
  .panel {
    background: #F9FAFB;
    padding: var(--spacing-medium);
    border-radius: 8px;
  }

  .panel-strong {
    background: linear-gradient(to right, var(--color-secondary), var(--color-primary));
    color: #FFFFFF;
    padding: 32px;
    border-radius: 8px;
  }

  .panel-strong h2,
  .panel-strong h3,
  .panel-strong p,
  .panel-strong div {
    color: #FFFFFF;
  }

  .panel-glass {
    background: rgba(249, 250, 251, 0.8);
    backdrop-filter: blur(10px);
    padding: 32px;
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.5);
  }

  .panel-gradient {
    background: linear-gradient(135deg, #F9FAFB 0%, #E5E7EB 100%);
    padding: 32px;
    border-radius: 8px;
  }

  .panel-compact {
    padding: 16px;
  }

  .accent-card {
    background: #F9FAFB;
    padding: 32px 24px 24px;
    border-radius: 8px;
    border-top: 6px solid var(--color-primary);
    border-top-left-radius: 0;
    border-top-right-radius: 0;
    margin-bottom: 0;
  }

  .accent-card-secondary {
    background: #F9FAFB;
    padding: 32px 24px 24px;
    border-radius: 8px;
    border-top: 6px solid var(--color-secondary);
    border-top-left-radius: 0;
    border-top-right-radius: 0;
    margin-bottom: 0;
  }

  .accent-card-brand {
    background: #F9FAFB;
    padding: 32px 24px 24px;
    border-radius: 8px;
    border-top: 6px solid var(--color-brand-text);
    border-top-left-radius: 0;
    border-top-right-radius: 0;
    margin-bottom: 0;
  }

  .card-muted {
    background: #F3F4F6;
    padding: 24px;
    border-radius: 8px;
  }

  /* 3カラム画像付きカード */
  .image-card-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .image-card {
    background: #F9FAFB;
    border: 1px solid #E5E7EB;
    border-radius: 12px;
    display: flex;
    flex-direction: column;
  }

  .image-card-thumb {
    width: 100%;
    aspect-ratio: 1 / 1;
    border-radius: 12px 12px 0 0;
    display: block;
    object-fit: contain;
    background: #E5E7EB;
  }

  .image-card-content {
    padding: 16px 20px 20px;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .image-card-title {
    font-size: 24px;
    font-weight: 700;
    color: var(--color-heading);
  }

  .image-card-tag {
    font-size: 18px; /* caption 相当 */
    color: #9CA3AF;
    line-height: 1.6;
    margin: 0;
  }

  .image-card-text {
    font-size: 22px;
    color: var(--color-subheading);
    line-height: 1.5;
  }

  /* 右側全面画像 */
  .right-image-full {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    align-items: center;
    min-height: calc(100% - 100px);
  }

  .right-image-full .image-pane {
    position: absolute;
    top: calc(-1 * var(--slide-padding));
    right: calc(-1 * var(--slide-padding));
    bottom: -100px;
    left: calc(50% + 12px);
    border-radius: 0;
    overflow: hidden;
    z-index: 0;
  }

  .right-image-full > div:first-child {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .right-image-full .image-pane img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .panel-center {
    text-align: center;
  }

  .panel-large {
    padding: 32px;
  }

  .panel-column {
    display: flex;
    flex-direction: column;
  }

  .panel-accent-primary {
    border-left: 4px solid var(--color-primary);
    border-top-left-radius: 0 !important;
    border-bottom-left-radius: 0 !important;
  }

  .panel-accent-secondary {
    border-left: 4px solid var(--color-secondary);
    border-top-left-radius: 0 !important;
    border-bottom-left-radius: 0 !important;
  }

  .panel-accent-alert {
    border-left: 4px solid var(--color-alert);
    border-top-left-radius: 0 !important;
    border-bottom-left-radius: 0 !important;
  }

  /* グリッドレイアウト */
  .grid-2col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  .grid-2col-gap-32 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
  }

  .grid-2col-gap-48 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 48px;
  }

  .grid-2col-center {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
    align-items: center;
  }

  .grid-2col-center-wide {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 48px;
    align-items: center;
  }

  .grid-3col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 24px;
  }

  .grid-3col-fill {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
    height: calc(100% - 80px);
    align-items: stretch;
  }

  .grid-4col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 16px;
  }

  .level-strip {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 6px;
  }

  .level-item {
    padding: 32px 12px 28px;
    border-radius: 12px;
    text-align: center;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .level-title {
    font-size: var(--font-size-subheading);
    font-weight: 600;
    color: inherit;
  }

  .level-desc {
    font-size: var(--font-size-base);
    font-weight: 400;
    opacity: 0.95;
    color: inherit;
  }

  .level-1 { background: #F3F4F6; color: #374151; }
  .level-2 { background: #E5E7EB; color: #374151; }
  .level-3 { background: #D1D5DB; color: #374151; }
  .level-4 { background: var(--color-link); color: #FFFFFF; }
  .level-5 { background: var(--color-link-strong); color: #FFFFFF; }

  .grid-2x3 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: repeat(3, 1fr);
    gap: 12px;
  }

  .grid-3x2-compact {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    gap: 8px;
  }

  /* ユーティリティクラス */
  .accent {
    color: var(--color-primary);
  }

  .center {
    text-align: center;
  }

  .mb-0 {
    margin-bottom: 0 !important;
  }

  /* セーフエリア */
  .safe-area {
    max-width: 90%;
    max-height: 80vh;
    margin: 0 auto;
    padding: 0 5%;
  }

  .center-stack {
    padding: 40px 0;
  }

  .stack-32 {
    display: flex;
    flex-direction: column;
    gap: 32px;
  }

  /* 統計スライド */
  .stat-slide {
    text-align: center;
  }

  .stat-number {
    font-size: 96px;
    font-weight: 800;
    color: var(--color-primary);
    line-height: 1;
    letter-spacing: -0.02em;
    margin-bottom: 0;
  }

  .stat-title {
    font-size: 36px;
    color: var(--color-heading);
    margin-top: 16px;
    font-weight: 700;
    margin-bottom: 0;
  }

  .stat-caption {
    font-size: 24px;
    color: var(--color-subheading);
    margin-top: 12px;
    margin-bottom: 0;
  }

  .text-block {
    margin: 0;
  }

  .text-block + .text-block {
    margin-top: 8px;
  }

  .caption-sm {
    font-size: 18px;
    color: #9CA3AF;
    line-height: 1.6;
    margin: 4px 0 0;
  }

  /* 問いかけスライド */
  .question-slide {
    text-align: left;
  }

  .question-slide h1 {
    font-size: 56px;
    color: var(--color-heading);
    margin-bottom: 24px;
  }

  .question-slide p {
    font-size: 28px;
    color: var(--color-subheading);
    margin: 0;
  }

  /* リスト系 */
  .timeline {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 16px;
    counter-reset: timeline-step;
  }

  .timeline li {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 0;
    font-size: 22px;
    color: var(--color-foreground);
  }

  .timeline li::before {
    counter-increment: timeline-step;
    content: counter(timeline-step);
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: var(--color-primary);
    color: #FFFFFF;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 18px;
    flex-shrink: 0;
  }

  /* パネル内ステップリスト（キャプションサイズ） */
  .usecase-steps {
    font-size: 20px;
    color: var(--color-subheading);
    margin: 0;
    padding-left: 24px;
    line-height: 1.45;
  }

  .usecase-steps li {
    margin-bottom: 8px;
  }

  .usecase-steps li:last-child {
    margin-bottom: 0;
  }

  /* アイコン付きリスト（カード型） */
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
    background: #F9FAFB; /* gray-50 */
    border: 1px solid #E5E7EB; /* gray-200 */
    border-radius: 12px;
  }

  .icon-badge {
    width: 44px;
    height: 44px;
    border-radius: 999px;
    background: rgba(62, 155, 164, 0.14); /* primary tint */
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
    min-width: 0;
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

  /* 引用（左アクセントライン。blockquoteのデフォルト線と二重にならないようにする） */
  .quote-accent {
    border-left: 4px solid var(--color-primary);
    padding-left: 24px;
    margin: 32px 0;
  }

  .quote-accent blockquote {
    margin: 0;
    padding: 0;
    border-left: none !important;
  }

  .quote-accent blockquote > p:last-child {
    margin-bottom: 0;
  }

  /* QRコード（中央配置・大きめ） */
  .qr-slide {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 24px;
  }

  .qr-code-box {
    width: 360px;
    height: 360px;
    background: #F3F4F6; /* gray-100 */
    border: 1px solid #E5E7EB; /* gray-200 */
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .qr-code-img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    display: block;
    background: #FFFFFF;
  }

  .qr-caption {
    display: flex;
    flex-direction: column;
    gap: 8px;
    text-align: center;
  }

  .qr-caption-title {
    font-size: 24px;
    font-weight: 600;
    color: var(--color-heading);
    margin: 0;
  }

  .qr-caption-url {
    font-size: 20px;
    color: var(--color-subheading);
    font-family: var(--font-family-mono);
    font-variant-numeric: tabular-nums;
    margin: 0;
    word-break: break-all;
  }

  /* 説明用画像（パネルの代替） */
  .explain-figure {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .explain-img {
    width: 100%;
    max-width: 520px;
    height: auto;
    display: block;
    border-radius: 16px;
    border: 1px solid #E5E7EB;
    background: #FFFFFF;
    box-shadow: 0 14px 28px rgba(17, 24, 39, 0.12);
  }

  .process-flow {
    list-style: none;
    margin: 0;
    padding: 16px 0;
    display: flex;
    align-items: stretch;
    gap: 12px;
  }

  .process-flow li {
    flex: 1;
    min-height: 140px;
    text-align: center;
    margin: 0;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .process-flow li::after {
    content: '→';
    position: absolute;
    right: -16px;
    top: 50%;
    transform: translateY(-50%);
    color: var(--color-primary);
    font-size: 26px;
  }

  .process-flow li:last-child::after {
    content: '';
  }

  .flow-step {
    width: 64px;
    height: 64px;
    background: var(--color-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #FFFFFF;
    font-weight: 700;
    margin: 0 auto 12px;
    font-size: 20px;
  }

  .flow-label {
    font-size: 22px;
    color: var(--color-heading);
    margin: 0;
  }

  /* 2段フロー比較（上下に2本並べる） */
  .dual-flow {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .dual-flow .panel {
    padding: 20px 24px;
  }

  /* 2本入れるため、フローはdual-flow内だけコンパクト化 */
  .dual-flow .process-flow {
    padding: 8px 0;
    gap: 10px;
  }
  .dual-flow .process-flow li {
    min-height: 110px;
  }
  .dual-flow .flow-step {
    width: 52px;
    height: 52px;
    font-size: 18px;
    margin: 0 auto 10px;
  }
  .dual-flow .process-flow li::after {
    font-size: 22px;
    right: -14px;
  }
  .dual-flow .flow-label {
    font-size: 18px;
  }

  /* 上段（従来）はニュートラルなグレーで表現 */
  .flow-legacy .flow-step {
    background: var(--color-subheading);
  }
  .flow-legacy .process-flow li::after {
    color: var(--color-subheading);
  }
  .flow-legacy .flow-label {
    color: var(--color-subheading);
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
  /* インラインロゴ（Yuki Yoshinagaの右隣に配置） */
  .logo-inline {
    display: inline-block;
    vertical-align: middle;
    width: var(--logo-size);
    height: var(--logo-size);
    margin-left: 12px;
    border-radius: 999px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    background-color: #FFFFFF;
    object-fit: cover;
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

  .fullscreen-background > *:not(.panel):not(.panel-glass) {
    padding: var(--slide-padding);
    max-width: 100%;
  }

  /* fullscreen-background用の白文字スタイル */
  .fullscreen-background h1 {
    color: white;
    font-size: 72px;
    font-weight: 800;
    line-height: 1.2;
    margin: 0 0 48px 0;
    letter-spacing: -0.02em;
    text-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
    text-align: left;
  }

  .fullscreen-background h2 {
    color: white;
    font-size: 56px;
    font-weight: 800;
    line-height: 1.2;
    margin: 0 0 28px 0;
    letter-spacing: -0.02em;
    text-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
    text-align: left;
  }

  .fullscreen-background p {
    color: white;
    font-size: 32px;
    line-height: 1.6;
    margin: 24px 0 48px 0;
    opacity: 0.95;
    font-weight: 300;
    text-align: left;
    text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
  }

  .fullscreen-background img {
    filter: drop-shadow(0 8px 20px rgba(0, 0, 0, 0.25));
  }

  .fullscreen-background .panel-glass img {
    filter: none !important;
  }

  .fullscreen-background .panel-glass {
    max-width: 50% !important;
  }

  .fullscreen-background footer {
    border-top-color: rgba(255, 255, 255, 0.35);
    color: rgba(255, 255, 255, 0.8);
  }

  .fullscreen-background footer::after {
    color: #FFFFFF;
  }

  /* fullscreen-background + 引用オーバーレイ（背景画像を暗くして引用を目立たせる） */
  .fullscreen-background.quote-overlay::before {
    content: '';
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.42);
    z-index: 0;
  }

  .fullscreen-background.quote-overlay > * {
    position: relative;
    z-index: 1;
  }

  .fullscreen-background.quote-overlay blockquote,
  .fullscreen-background.quote-overlay blockquote p {
    color: white !important;
    font-size: 32px !important;
    line-height: 1.6;
    margin: 0;
    opacity: 0.95;
    font-weight: 400;
    text-align: left;
    text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
  }

  .fullscreen-background.quote-overlay .quote-accent {
    background: rgba(0, 0, 0, 0.38) !important;
    padding: 28px 32px !important;
    border-radius: 0;
    border-left: none !important;
    margin: 0 !important;
  }

  .fullscreen-background.quote-overlay blockquote strong {
    font-weight: 600;
    letter-spacing: 0.01em;
    color: white !important;
  }

  /* border-leftがある時は左上と左下のradiusを削除（レガシー互換） */
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

# タイトル
<!-- パターン: A. タイトル・セクション系 / 用途: 冒頭でテーマと登壇情報を提示し、期待値を揃える時。 -->
## サブタイトル

Yuki Yoshinaga <img class="logo-inline" src="logo.png" alt="" />  
202X年X月X日

---

<!-- _class: toc-slide -->

<div class="toc-layout">

<div>

<div class="toc-title-group">
  <h1>目次</h1>
  <h2>Index</h2>
  <!-- パターン: A. タイトル・セクション系 / 用途: 全体構成を提示し、聞き手の「地図」を作る時。 -->
</div>

</div>

<div>

1. セクションA
2. セクションB
3. セクションC
4. セクションD
5. セクションE

</div>

</div>

---

<!-- _class: section-start -->

# セクション開始
<!-- パターン: A. タイトル・セクション系 / 用途: 章の切り替わりに使うインパクトのあるパターン。 -->
## セクションタイトル

---

## ここにタイトルが入ります
<!-- パターン: A. タイトル・セクション系 / 用途: 導入の問題提起を文章で説明する通常スライド。 -->

ここに説明文が入ります。

**ここに強調文が入ります。**

---

## ここにタイトルが入ります
<!-- パターン: A. タイトル・セクション系 / 用途: フォーマットや書式をコード例で示す時。 -->

```markdown
# サンプルタイトル
- 項目A
- 項目B
- 項目C
- 項目D
```

ここに説明文が入ります。

---

## 2カラム比較：Before/After
<!-- パターン: B. カラムレイアウト系 / 用途: 変更前後の比較を端的に見せたい時。 -->

<div class="grid-2col">

<div class="mb-0">

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">Before</h2>
<div style="font-size: 24px; color: #1F2937; margin-bottom: 16px;">
ここに短い説明が入ります
</div>
<div style="font-size: 26px; color: #4B5563; font-style: italic;">
「ここに例文が入ります」
</div>

</div>

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">After</h2>
<div style="font-size: 24px; color: #1F2937; margin-bottom: 16px;">
ここに短い説明が入ります
</div>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>項目A</li>
<li>項目B</li>
<li>項目C</li>
<li>項目D</li>
</ul>

</div>

</div>

---


## 2カラム対比：タイトル
<!-- パターン: B. カラムレイアウト系 / 用途: 2つの性質や考え方を対比して示す時。 -->

<div class="grid-2col">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">項目A</h2>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>説明文A</li>
<li>説明文B</li>
<li>説明文C</li>
</ul>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">項目B</h2>
<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>説明文A</li>
<li>説明文B</li>
<li>説明文C</li>
</ul>

</div>

</div>

---


## 3カラムレイアウト：タイトル
<!-- パターン: B. カラムレイアウト系 / 用途: 構成要素を3点で整理したい時。 -->

<div class="grid-3col">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルA</h2>
<div style="font-size: 26px; color: #1F2937;">
テキスト  
テキスト
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルB</h2>
<div style="font-size: 26px; color: #1F2937;">
テキスト  
テキスト
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルC</h2>
<div style="font-size: 26px; color: #1F2937;">
テキスト  
テキスト
</div>

</div>

</div>

---


## 3カラム（アクセント）
<!-- パターン: B. カラムレイアウト系 / 用途: 重要ポイントをアクセントで強調したい時。 -->

<div class="grid-3col">

<div class="accent-card">

<h2 style="margin: 0 0 24px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルA</h2>
<div style="color: #1F2937;">
ここに説明文が入ります
</div>

</div>

<div class="accent-card-brand">

<h2 style="margin: 0 0 24px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルB</h2>
<div style="color: #1F2937;">
ここに説明文が入ります
</div>

</div>

<div class="accent-card">

<h2 style="margin: 0 0 24px 0; font-size: 24px; font-weight: 700; color: #374151;">タイトルC</h2>
<div style="color: #1F2937;">
ここに説明文が入ります
</div>

</div>

</div>

---

## 3カラム画像付き
<!-- パターン: B. カラムレイアウト系 / 用途: 画像付きカードを3つ並べて紹介したい時。 -->

<div class="image-card-grid">
  <div class="image-card">
    <img class="image-card-thumb" src="../sampleAssets/tomato.png" alt="トマト" />
    <div class="image-card-content">
      <div class="image-card-title">タイトルA</div>
      <div class="image-card-text">ここに説明文が入ります</div>
      <div class="image-card-tag">#タグ</div>
    </div>
  </div>
  <div class="image-card">
    <img class="image-card-thumb" src="../sampleAssets/cucumber.png" alt="きゅうり" />
    <div class="image-card-content">
      <div class="image-card-title">タイトルB</div>
      <div class="image-card-text">ここに説明文が入ります</div>
      <div class="image-card-tag">#タグ</div>
    </div>
  </div>
  <div class="image-card">
    <img class="image-card-thumb" src="../sampleAssets/eggplant.png" alt="なす" />
    <div class="image-card-content">
      <div class="image-card-title">タイトルC</div>
      <div class="image-card-text">ここに説明文が入ります</div>
      <div class="image-card-tag">#タグ</div>
    </div>
  </div>
</div>

---

## 4カラムレイアウト：タイトル
<!-- パターン: B. カラムレイアウト系 / 用途: 4つの利点・項目を並列に示す時。 -->

<div class="grid-4col">

<div class="panel panel-center">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">タイトルA</h3>
<div style="font-size: 24px; color: #4B5563;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-center">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">タイトルB</h3>
<div style="font-size: 24px; color: #4B5563;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-center">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">タイトルC</h3>
<div style="font-size: 24px; color: #4B5563;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-center">

<h3 style="margin: 0 0 16px 0; font-size: 26px; font-weight: 600; color: #374151;">タイトルD</h3>
<div style="font-size: 24px; color: #4B5563;">
ここに説明文が入ります
</div>

</div>

</div>

---


## 5カラム：成熟度レベル
<!-- パターン: B. カラムレイアウト系 / 用途: レベルや成熟度を段階的に示す時。 -->

<div class="level-strip">
  <div class="level-item level-1">
    <div class="level-title">Lv.1 タイトル</div>
    <div class="level-desc">ここに説明文が入ります</div>
  </div>
  <div class="level-item level-2">
    <div class="level-title">Lv.2 タイトル</div>
    <div class="level-desc">ここに説明文が入ります</div>
  </div>
  <div class="level-item level-3">
    <div class="level-title">Lv.3 タイトル</div>
    <div class="level-desc">ここに説明文が入ります</div>
  </div>
  <div class="level-item level-4">
    <div class="level-title">Lv.4 タイトル</div>
    <div class="level-desc">ここに説明文が入ります</div>
  </div>
  <div class="level-item level-5">
    <div class="level-title">Lv.5 タイトル</div>
    <div class="level-desc">ここに説明文が入ります</div>
  </div>
</div>

---


## 2x2グリッド：タイトル
<!-- パターン: B. カラムレイアウト系 / 用途: 4象限で用途や分類を整理したい時。 -->

<div class="grid-2col">

<div class="panel panel-compact">

<h2 style="margin: 0 0 12px 0; font-size: 22px; font-weight: 700; color: #374151;">カテゴリA</h2>
<div style="font-size: 24px; color: #4B5563;">
テキスト  
テキスト
</div>

</div>

<div class="panel panel-compact">

<h2 style="margin: 0 0 12px 0; font-size: 22px; font-weight: 700; color: #374151;">カテゴリB</h2>
<div style="font-size: 24px; color: #4B5563;">
テキスト  
テキスト
</div>

</div>

<div class="panel panel-compact">

<h2 style="margin: 0 0 12px 0; font-size: 22px; font-weight: 700; color: #374151;">カテゴリC</h2>
<div style="font-size: 24px; color: #4B5563;">
テキスト  
テキスト
</div>

</div>

<div class="panel panel-compact">

<h2 style="margin: 0 0 12px 0; font-size: 22px; font-weight: 700; color: #374151;">カテゴリD</h2>
<div style="font-size: 24px; color: #4B5563;">
テキスト  
テキスト
</div>

</div>

</div>

---


## 3x2グリッド：タイトル
<!-- パターン: B. カラムレイアウト系 / 用途: 複数の短い実例を一覧で見せたい時。 -->

<div class="grid-3x2-compact">

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルA</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルB</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルC</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルD</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルE</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-compact">

<h3 style="margin: 0 0 6px 0; font-size: 18px; font-weight: 600; color: #374151;">タイトルF</h3>
<div style="font-size: 20px; color: #4B5563; margin: 0;">
ここに説明文が入ります
</div>

</div>

</div>

---


## ステップリスト：タイトル
<!-- パターン: C. リスト系 / 用途: 手順を順番に伝えたい時。 -->

1. **項目**の説明文が入ります
2. **項目**の説明文が入ります
3. **項目**の説明文が入ります
4. **項目**の説明文が入ります
5. **項目**の説明文が入ります
6. **項目**の説明文が入ります
7. **項目**の説明文が入ります
8. **項目**の説明文が入ります

---

## 定義 + ステップ例（右パネル）
<!-- パターン: B. カラムレイアウト系 / 用途: 左で定義、右で手順例を見せて理解を固定したい時。 -->

<div class="grid-2col-center">

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">ユースケース記述</h2>

<div style="font-size: 26px; color: #1F2937; line-height: 1.6;">
主体ごとの挙動を、シナリオベースで叙述した作文。<br>
物事が起きる順に、行動とシステムの反応を並べる。
</div>

</div>

<div class="panel">

<ol class="usecase-steps">
  <li>ユーザーはホーム画面を開く</li>
  <li>アプリはホーム画面を表示する</li>
  <li>アプリはニュース一覧を表示する</li>
  <li>ユーザーはいずれかのニュースを開く</li>
  <li>アプリは当該ニュースを表示する</li>
  <li>ユーザーは...</li>
</ol>

</div>

</div>

---


## タイムライン：タイトル
<!-- パターン: C. リスト系 / 用途: 時系列の流れを示したい時。 -->

<ol class="timeline">
  <li>ここに工程名が入ります</li>
  <li>ここに工程名が入ります</li>
  <li>ここに工程名が入ります</li>
  <li>ここに工程名が入ります</li>
</ol>

---


## アイコン付きリスト：タイトル
<!-- パターン: C. リスト系 / 用途: 特徴を視覚的に分かりやすく伝える時。 -->

<ul class="icon-card-list">
  <li class="icon-card">
    <span class="icon-badge">📝</span>
    <div class="icon-card-content">
      <div class="icon-card-title">タイトルA</div>
      <div class="icon-card-body">ここに説明文が入ります</div>
    </div>
  </li>
  <li class="icon-card">
    <span class="icon-badge">🎯</span>
    <div class="icon-card-content">
      <div class="icon-card-title">タイトルB</div>
      <div class="icon-card-body">ここに説明文が入ります</div>
    </div>
  </li>
  <li class="icon-card">
    <span class="icon-badge">⚡</span>
    <div class="icon-card-content">
      <div class="icon-card-title">タイトルC</div>
      <div class="icon-card-body">ここに説明文が入ります</div>
    </div>
  </li>
</ul>

---


## チェックリスト：タイトル
<!-- パターン: C. リスト系 / 用途: 確認項目や達成条件を一覧化する時。 -->

<div class="checklist">

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">ここに確認項目が入ります</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">ここに確認項目が入ります</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">ここに確認項目が入ります</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">ここに確認項目が入ります</div>
</div>

<div class="checklist-item">
<div class="checklist-checkbox">☑</div>
<div class="checklist-text">ここに確認項目が入ります</div>
</div>

<div class="checklist-item unchecked">
<div class="checklist-checkbox">☐</div>
<div class="checklist-text">ここに確認項目が入ります（オプション）</div>
</div>

<div class="checklist-item unchecked">
<div class="checklist-checkbox">☐</div>
<div class="checklist-text">ここに確認項目が入ります（オプション）</div>
</div>

</div>

---


## 基本パネル
<!-- パターン: D. パネルデザイン系 / 用途: まとまった説明をパネルで読みやすく提示したい時。 -->

<div class="panel">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
ここに説明文が入ります。

ここに説明文が入ります。

ここに説明文が入ります。
</div>

</div>

---


## 強調パネル
<!-- パターン: D. パネルデザイン系 / 用途: 重要メッセージを背景色で強調したい時。 -->

<div class="panel panel-strong">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700;">ここにタイトルが入ります</h2>

<div>
ここに説明文が入ります。

ここに強調文が入ります。
</div>

</div>

---


## ガラス風パネル
<!-- パターン: D. パネルデザイン系 / 用途: 背景の上に“浮かぶ”情報パネルを置きたい時（装飾多め）。 -->

<div class="panel panel-glass">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
ここに説明文が入ります。
</div>

</div>

---


## グラデーションパネル
<!-- パターン: D. パネルデザイン系 / 用途: 事例やストーリーを少しリッチに見せたい時。 -->

<div class="panel panel-gradient">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

<div style="font-size: 24px; color: #1F2937; line-height: 1.6;">
  <p>ここに説明文が入ります。</p>
  <p><strong>ここに強調文が入ります。</strong></p>
</div>

</div>

---


## ボーダーパネル
<!-- パターン: D. パネルデザイン系 / 用途: 枠線で情報ブロックを明確に区切りたい時。 -->

<div style="background: #FFFFFF; padding: 32px; border-radius: 8px; border: 2px solid var(--color-link);">

<h2 style="margin: 0 0 24px 0; font-size: 32px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

```markdown
# サンプルタイトル
- 項目A
- 項目B
- 項目C
- 項目D
```

<div style="font-size: 24px; color: #1F2937; margin-top: 16px;">
ここに説明文が入ります。
</div>

</div>

---


<!-- _class: fullscreen-background -->
<!-- パターン: E. 背景・画像系 / 用途: 章の切り替えや強い主張で、全画面背景で印象づけたい時。 -->
<style scoped>
section {
  background: linear-gradient(135deg, #0536AF 0%, #3163E3 55%, #F4F754 100%);
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

# ここにタイトルが入ります

ここに説明文が入ります

ここに説明文が入ります

---

<!-- _class: fullscreen-background -->
<!-- パターン: E. 背景・画像系 / 用途: 写真を全面背景にして“空気感”を作りたい時（文字は最小限）。 -->
<style scoped>
section {
  background-image: url('../sampleAssets/sam 2.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
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
  text-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
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
  text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
}

section footer {
  display: flex;
  border-top-color: rgba(255, 255, 255, 0.35);
  color: rgba(255, 255, 255, 0.8);
}

section footer::after {
  color: #FFFFFF;
}
</style>

# 背景全面：画像サンプル

画像をスライド全面に配置した例です。テキストは白とシャドウで可読性を確保しています。

---

<!-- _class: fullscreen-background quote-overlay -->
<!-- パターン: E. 背景・画像系 / 用途: 背景画像＋オーバーレイ＋引用で印象的なメッセージを伝えたい時。 -->
<style scoped>
section {
  background-image: url('../sampleAssets/sam 2.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
  padding: 56px !important;
}

.quote-accent {
  background: rgba(0, 0, 0, 0.38) !important;
  padding: 28px 32px !important;
  border-radius: 0 !important;
  border-left: none !important;
  margin: 0 !important;
}

blockquote {
  color: white !important;
  font-size: 32px !important;
  line-height: 1.6 !important;
  margin: 0 !important;
  opacity: 0.95;
  font-weight: 400;
  text-align: left;
  text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
  border-left: 4px solid var(--color-primary) !important;
  padding: 0 0 0 24px !important;
}

blockquote p {
  color: white !important;
  font-size: 32px !important;
  line-height: 1.6 !important;
  margin: 0 !important;
  opacity: 0.95;
  font-weight: 400;
  text-align: left;
  text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
}

blockquote strong {
  font-weight: 600;
  letter-spacing: 0.01em;
  color: white !important;
}
</style>

<div class="quote-accent">

> ここに引用文が入ります。  
> 複数行で記載できます。  
> <strong>強調したい部分</strong>はstrongタグで囲みます。
>
> ー 引用元

</div>

---

<!-- _class: fullscreen-background -->
<!-- パターン: E. 背景・画像系 / 用途: 事例紹介など、背景画像＋ロゴ＋説明文＋補足要素を配置したい時。 -->
<style scoped>
section {
  background-image: url('../sampleAssets/temporary-art.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
  padding: 56px !important;
}

.panel-glass {
  max-width: 50%;
}
</style>

![width:520px](../sampleAssets/temporary-art.png)

<p>
製品やサービスの説明文がここに入ります。<br>
背景画像の上でも読みやすい白文字とシャドウを使用しています。
</p>

<div class="panel panel-glass" style="padding: 24px;">
  <img src="../sampleAssets/temporary-art.png" alt="補足要素（例：導入企業ロゴ）" style="width: 100%; display: block; filter: none;" />
</div>

---

## 右側配置：サンプル
<!-- パターン: E. 背景・画像系 / 用途: 右にビジュアル、左に説明を置きたい時。 -->

<div class="grid-2col-center">

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li><strong>項目</strong>の説明文が入ります</li>
<li><strong>項目</strong>の説明文が入ります</li>
<li><strong>項目</strong>の説明文が入ります</li>
<li><strong>項目</strong>の説明文が入ります</li>
<li><strong>項目</strong>の説明文が入ります</li>
</ul>

</div>

<div class="explain-figure">
  <img class="explain-img" src="../sampleAssets/explain-medium-library.svg" alt="説明画像（サンプル）" />
</div>

</div>

---


## 左側配置：サンプル
<!-- パターン: E. 背景・画像系 / 用途: 左にビジュアル、右に説明を置きたい時。 -->

<div class="grid-2col-center">

<div class="explain-figure">
  <img class="explain-img" src="../sampleAssets/explain-repo-overview.svg" alt="説明画像（サンプル）" />
</div>

<div>

<h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに長めの説明文が入ります</li>
</ul>

</div>

</div>

---


## 右側全面画像
<!-- パターン: E. 背景・画像系 / 用途: 右側を写真で全面的に見せたい時。 -->

<div class="right-image-full">
  <div>
    <h2 style="margin: 0 0 24px 0; font-size: 28px; font-weight: 700; color: #374151;">ここにタイトルが入ります</h2>
    <ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
      <li>ここに説明文が入ります</li>
      <li>ここに説明文が入ります</li>
      <li>ここに説明文が入ります</li>
    </ul>
  </div>
  <div class="image-pane">
    <img src="../sampleAssets/temporary-art.png" alt="右側全面画像サンプル" />
  </div>
</div>

---

## 大きめ画像（単独）
<!-- パターン: E. 背景・画像系 / 用途: 画像のみをセーフエリアギリギリまで大きく見せたい時。UIスクリーンショットやデモ画面などに最適。 -->

<div class="center">

![width:1150px](../sampleAssets/temporary-art.png)

</div>

---

## 引用スライド
<!-- パターン: E. 背景・画像系 / 用途: 引用や印象的な一文を強調したい時。 -->

<div class="quote-accent">

> ここに引用文が入ります。
>
> ここに引用文が入ります。
>
> ここに引用文が入ります。

</div>

---


## 統計スライド
<!-- パターン: F. 強調・特殊系 / 用途: 重要な数値を強く印象づけたい時。 -->

<div class="center safe-area center-stack stat-slide">

<div class="stat-number">1</div>

<div class="stat-title">ここにタイトルが入ります</div>

<div class="stat-caption">ここに補足文が入ります</div>

</div>

---


<div class="center safe-area center-stack">
<!-- パターン: F. 強調・特殊系 / 用途: 強い一文メッセージを中央に置いて記憶に残したい時。 -->

# ここに訴求文が入ります

<div class="text-block" style="font-size: 28px; color: var(--color-subheading); margin-top: 16px;">
ここに説明文が入ります
</div>

</div>

---


## Q&Aスライド
<!-- パターン: F. 強調・特殊系 / 用途: よくある質問と回答を整理して示す時。 -->

<div class="stack-32">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">Q. ここに質問文が入ります</h2>

<div style="font-size: 26px; color: #1F2937; line-height: 1.6;">
A. ここに回答文が入ります。
</div>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">Q. ここに質問文が入ります</h2>

<div style="font-size: 26px; color: #1F2937; line-height: 1.6;">
A. ここに回答文が入ります。
</div>

</div>

</div>

---


<!-- パターン: F. 強調・特殊系 / 用途: 聞き手に考えさせたい問いかけを提示する時。 -->
<div class="center safe-area center-stack question-slide">

# ここに問いかけのタイトルが入ります

<p>ここに問いかけの説明文が入ります</p>

</div>

---

## QRコード：参考資料
<!-- パターン: G. 応用パターン / 用途: 参照リンクや資料への導線を提示する時。 -->

<div class="center safe-area center-stack qr-slide">
  <div class="qr-code-box">
    <img class="qr-code-img" src="../sampleAssets/dummy-qr.svg" alt="QR code" />
  </div>
  <div class="qr-caption">
    <div class="qr-caption-title">タイトルがここに入ります</div>
    <div class="qr-caption-url">https://example.com</div>
  </div>
</div>

---


## まとめ：要点整理
<!-- パターン: G. 応用パターン / 用途: 章や話題の要点を簡潔に振り返る時。 -->

<div class="grid-2col">

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">1. タイトルA</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
ここに説明文が入ります
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">2. タイトルB</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
ここに説明文が入ります
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">3. タイトルC</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
ここに説明文が入ります
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">4. タイトルD</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5;">
ここに説明文が入ります
</div>

</div>

</div>

---


## 企業事例：タイトル
<!-- パターン: G. 応用パターン / 用途: 事例やケーススタディを紹介する時。 -->

<div class="grid-2col">

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">ケース1：タイトル</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
</ul>

</div>

<div class="panel">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">ケース2：タイトル</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
</ul>

</div>

</div>

---


## 比較表：タイトル
<!-- パターン: G. 応用パターン / 用途: 複数項目を表形式で比較したい時。 -->

| 項目 | 比較A | 比較B |
|:-----|------|------|
| 項目1 | テキスト | テキスト |
| 項目2 | テキスト | テキスト |
| 項目3 | テキスト | テキスト |
| 項目4 | テキスト | テキスト |
| 項目5 | テキスト | テキスト |
| 項目6 | テキスト | テキスト |

---


## プロセスフロー：タイトル
<!-- パターン: G. 応用パターン / 用途: 工程の全体像や流れを可視化したい時。 -->

<ol class="process-flow">
  <li>
    <div class="flow-step">1</div>
    <div class="flow-label">ステップ1</div>
  </li>
  <li>
    <div class="flow-step">2</div>
    <div class="flow-label">ステップ2</div>
  </li>
  <li>
    <div class="flow-step">3</div>
    <div class="flow-label">ステップ3</div>
  </li>
  <li>
    <div class="flow-step">4</div>
    <div class="flow-label">ステップ4</div>
  </li>
</ol>

<div class="text-block center" style="font-size: 22px; color: var(--color-subheading); margin-top: 16px;">
ここに説明文が入ります
</div>

---

<!-- パターン: G. 応用パターン / 用途: 従来と変化を上下のフローで比較したい時。 -->

<div class="dual-flow">

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 700; color: #374151;">従来</h3>

<div class="flow-legacy">
<ol class="process-flow">
  <li><div class="flow-step">1</div><div class="flow-label">工程A</div></li>
  <li><div class="flow-step">2</div><div class="flow-label">工程B</div></li>
  <li><div class="flow-step">3</div><div class="flow-label">工程C</div></li>
  <li><div class="flow-step">4</div><div class="flow-label">工程D</div></li>
</ol>
<div class="text-block center" style="font-size: 20px; color: var(--color-subheading); margin-top: 10px;">
ここに説明文が入ります
</div>
</div>

</div>

<div class="panel">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 700; color: #374151;">変化</h3>

<ol class="process-flow">
  <li><div class="flow-step">1</div><div class="flow-label">工程A</div></li>
  <li><div class="flow-step">2</div><div class="flow-label">工程B</div></li>
  <li><div class="flow-step">3</div><div class="flow-label">工程C</div></li>
  <li><div class="flow-step">4</div><div class="flow-label">工程D</div></li>
</ol>
<div class="text-block center" style="font-size: 20px; color: var(--color-subheading); margin-top: 10px;">
ここに説明文が入ります
</div>

</div>

</div>

---


## メリット・デメリット（サンプル）
<!-- パターン: G. 応用パターン / 用途: メリット/デメリットなど両面を並べて判断材料を出す時。 -->

<div class="grid-2col-gap-32">

<div class="panel panel-accent-primary">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">メリット</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
</ul>

</div>

<div class="panel panel-accent-alert">

<h2 style="margin: 0 0 20px 0; font-size: 24px; font-weight: 700; color: #374151;">デメリット</h2>

<ul style="font-size: 26px; color: #1F2937; margin: 0; padding-left: 24px;">
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
<li>ここに説明文が入ります</li>
</ul>

</div>

</div>

---


## チェックポイント：タイトル
<!-- パターン: G. 応用パターン / 用途: 最終確認のチェック項目を提示する時。 -->

<div class="checklist">
  <div class="checklist-item">
    <div class="checklist-checkbox">☑</div>
    <div class="checklist-text">ここに確認項目が入ります</div>
  </div>
  <div class="checklist-item">
    <div class="checklist-checkbox">☑</div>
    <div class="checklist-text">ここに確認項目が入ります</div>
  </div>
  <div class="checklist-item">
    <div class="checklist-checkbox">☑</div>
    <div class="checklist-text">ここに確認項目が入ります</div>
  </div>
  <div class="checklist-item">
    <div class="checklist-checkbox">☑</div>
    <div class="checklist-text">ここに確認項目が入ります</div>
  </div>
</div>

---


## 参考資料（サンプル）
<!-- パターン: G. 応用パターン / 用途: 参考リンクや根拠をまとめて提示する時。 -->

<div style="display: flex; flex-direction: column; gap: 16px; font-size: 24px;">

1. **サンプル資料A**
   - ここに説明文が入ります

2. **サンプル資料B**
   - https://example.com

3. **サンプル資料C**
   - https://example.com

4. **サンプル資料D**
   - ここに説明文が入ります

</div>

---


## まとめ：タイトル
<!-- パターン: G. 応用パターン / 用途: プレゼンの結論や価値を強調して締める時。 -->

<div class="grid-3col-fill">

<div class="panel panel-column">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">タイトルA</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-column">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">タイトルB</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
ここに説明文が入ります
</div>

</div>

<div class="panel panel-column">

<h3 style="margin: 0 0 12px 0; font-size: 24px; font-weight: 600; color: #374151;">タイトルC</h3>
<div style="font-size: 22px; color: #1F2937; line-height: 1.5; flex: 1;">
ここに説明文が入ります
</div>

</div>

</div>

---

<!-- _class: section-end -->

# セクション終了
<!-- パターン: A. タイトル・セクション系 / 用途: 章や発表の区切りとして“締め”を作る時。 -->
## まとめ

---

<!-- _class: title-slide -->

## ありがとうございました
<!-- パターン: A. タイトル・セクション系 / 用途: クロージングで連絡先と呼びかけを提示する時。 -->

ご質問・ご意見をお待ちしています

Yuki Yoshinaga <img class="logo-inline" src="logo.png" alt="" />  
@uxman
