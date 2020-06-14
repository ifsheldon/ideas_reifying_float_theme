![Float](static/images/Float_logo.png)

**[Taiwanese](README.md)**

Float, a theme for [Zola](https://www.getzola.org/).

[[_TOC_]]

## Features

- Responsive. Optimized for all size devices.
- Provide regular and wide article card. Feature articles are highlighted with the wide card.
- You can specify a feature image in front-matter. For an article without a specified feature image, a random image from [Unsplash Source](https://source.unsplash.com/) will be used.
- Feature images have variant sizes to optimize from DPR 1.0 to 3.0 devices.
- HTML native image lazy loading.
- Embedded semantic meta tags, including HTML SEO tags, [Open Graph](https://ogp.me/) tags, [Twitter Cards](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards) tags.
- Integrated [Google Analytics](https://analytics.google.com/).
- Integrated [Google AdSense](https://adsense.google.com/).
- Optimized layout for [AdSense Auto ads](https://support.google.com/adsense/answer/9261306).
- Integrated [LikeCoin](https://like.co/).
- Integrated [utterances](https://utteranc.es/). Use [GitHub](https://github.com/) issue as commenting system.

## Installation

In your Zola folder:

```shell
cd themes
git clone git@gitlab.com:leon0824/float.git
```

Edit your config.toml. Assign `float` to `theme`:

```TOML
theme = "float"
```

## Using

### Article and images

Article and images are co-located in the same folder:

```
content/
└── blog/
     └── 2020-06-21-Float theme for Zola/
          ├── index.md
          ├── pic1.png
          ├── pic2.png
          └── qa_report.pdf
```

Article content and front-matter are in index.md. Images are in the same folder.

### Front-matter

Some additional data are added into `[extra]` section of front-matter:

```TOML
title = "Float theme for Zola"
description = "Float features and usage guide"
draft = false
[taxonomies]
tags = ["Float", "Zola"]
[extra]
feature_image = "pic1.png" # Article card image
feature = true # Wide article card applies to feature article
```

### Font

Font CSS is at float/sass/font.scss. To change font, copy float/sass/font.scss to your sass/font.scss and edit the file.

[Google Fonts](https://fonts.google.com/) is at `font_link()` of float/templates/_macros.html. to change Google Fonts, copy float/templates/_macros.html to your templates/_macros.html and edit the `font_link()` block.

### Copyright

Copyright is at `copyright_block()` of float/templates/_macros.html. to change copyright, copy float/templates/_macros.html to your templates/_macros.html and edit the `copyright_block()` block.

### Google Analytics

Add below snippet to your `[extra]` of /config.toml to enable Google Analytics:

```TOML
google_analytics = true
google_analytics_id = "UA-xxxxxx-x" # Fill Google Analytics ID
```

### Google AdSense

Add below snippet to your `[extra]` of /config.toml to enable Google AdSense:

```TOML
google_adsense = true
google_adsense_id = "ca-pub-XXXXXXXXXXXXXXXX" # Fill Google AdSense ID
```

### Twitter Cards

Add below snippet to your `[extra]` of /config.toml to embed your Twitter account into Twitter Cards tags:

```TOML
twitter_account = "@xxx" # Fill Twitter account
```

### LikeCoin

Add below snippet to your `[extra]` of /config.toml to enable LikeCoin:

```TOML
likecoin = true
likecoin_name = "xxx" # 填入 LikeCoin 帳號
```

### utterances

Before adding a snippet, additional steps must be done. Refers to [utterances](https://utteranc.es/) document to setup your GitHub repository.

After adding utterances to your GitHub repository, add below snippet to your `[extra]` of /config.toml to enable utterances:

```TOML
utterances = false
utterances_repo = "username/repository" # Fill a GitHub repository。
```

## Known issues

- `paginate_by` must be 10. Zola template does not provide `paginate_by` from `get_section()`, so the 10 articles per page is hard coded in template files.
- Article feature image does not support SVG because Zola `resoze_image()` does not support SVG.
