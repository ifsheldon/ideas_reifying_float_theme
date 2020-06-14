+++
title = "Float theme for Zola"
description = "Float features and usage guide"
draft = false
[taxonomies]
tags = ["Float", "Zola"]
[extra]
feature_image = ""
feature = true
+++

**[English](/en/blog/float-theme-for-zola/)**

Float 是一款為 [Zola](https://www.getzola.org/) 設計的佈景主題。

## 特色

- 依據不同的螢幕尺寸提供最佳化版面，從小尺寸到大尺寸都可獲得優秀的閱讀體驗。
- 文章卡片提供兩種卡片尺寸，重點文章可採用更醒目的寬版卡片。
- 文章卡片配圖可自行指定，未指定者使用 [Unsplash Source](https://source.unsplash.com/) 的隨機圖片。
- 使用 Zola 的 `resize_image()` 自動產生適用於 DPR 1.0 ~ 3.0 的圖片，卡片配圖會由瀏覽器依據設備之 DPR 自動選用最佳尺寸的圖片。
- 圖片啟用延遲載入，縮短頁面載入時間。
- 預設埋入 HTML SEO 標籤、[Open Graph](https://ogp.me/) 與 [Twitter Cards](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards) 標籤。
- 整合 [Google Analytics](https://analytics.google.com/)。
- 整合 [Google AdSense](https://adsense.google.com/)。
- 版面為 [AdSense 自動廣告](https://support.google.com/adsense/answer/9261306)最佳化，不會因自動廣告的寬度不一而破版。
- 整合 [LikeCoin](https://like.co/)。
- 整合 [utterances](https://utteranc.es/)，利用 [GitHub](https://github.com/) issue 作為留言系統。

## 安裝與啟用

在您的 Zola 專案資料夾內：

```shell
cd themes
git clone git@gitlab.com:leon0824/float.git
```

編輯您的 config.toml，指定 Float 作為佈景主題：

```TOML
theme = "float"
```

## 使用 Float

### 文章與配圖

文章皆以資料夾的方式存在，如下例：

```
content/
└── blog/
     └── 2020-06-21-Float theme for Zola/
          ├── index.md
          ├── pic1.png
          ├── pic2.png
          └── qa_report.pdf
```

文章為 index.md，文內的配圖或其它檔案也是放在文章資料夾內。

### Front-matter

Front-matter 請參照下列註解說明：

```TOML
title = "Float theme for Zola"
description = "Float features and usage guide"
draft = false
[taxonomies]
tags = ["Float", "Zola"]
[extra]
feature_image = "pic1.png" # 卡片圖片。
feature = true # 是否為重點文章，重點文章會以寬版卡片顯示。
```

### 字體

字體的 CSS 位於 float/sass/font.scss，欲更換字體，把 float/sass/font.scss 複製到自己的 sass/font.scss，並修改之。

[Google Fonts](https://fonts.google.com/) 在 float/templates/_macros.html 內的 `font_link()` 區段。欲更換載入字體，把 float/templates/_macros.html 複製到自己的 templates/_macros.html 並修改之。


### 版權宣告

版權宣告在 float/templates/_macros.html 內的 `copyright_block()` 區段。欲更換版權宣告，把 float/templates/_macros.html 複製到自己的 templates/_macros.html 並修改之。

### Google Analytics

在您的 config.toml 內的 `[extra]` 寫入下列設定即可自動啟用 Google Analytics：

```TOML
google_analytics = true
google_analytics_id = "UA-xxxxxx-x" # 填入 Google Analytics ID
```

### Google AdSense

在您的 config.toml 內的 `[extra]` 寫入下列設定即可自動啟用 Google AdSense：

```TOML
google_adsense = true
google_adsense_id = "ca-pub-XXXXXXXXXXXXXXXX" # 填入 Google AdSense ID
```

### Twitter Cards

在您的 config.toml 內的 `[extra]` 寫入下列設定即可在網頁內的 Twitter Card 區域埋入您的 Twitter 帳號：

```TOML
twitter_account = "@xxx" # 填入 Twitter 帳號
```

### LikeCoin

在您的 config.toml 內的 `[extra]` 寫入下列設定即可自動啟用 LikeCoin：

```TOML
likecoin = true
likecoin_name = "xxx" # 填入 LikeCoin 帳號
```

### utterances

須先在 GitHub 設定 [utterances](https://github.com/apps/utterances)，詳細的步驟請參考 [utterances 網站](https://utteranc.es/)。

在您的 config.toml 內的 `[extra]` 寫入下列設定即可自動啟用 utterances：

```TOML
utterances = false
utterances_repo = "username/repository" # 填入欲搭配使用的 GitHub repository。
```

## 已知問題

- 分頁設定皆須設為 10 篇分頁。因為 Zola 的 `get_section()` 無法取得該 section 的分頁設定。
