這是 [Float Theme](https://gitlab.com/float-theme/float.git) 的客製分支。

本分支與原始程式碼均採用 [MIT 授權](LICENSE)。

[English](README.en.md)

## 建置與預覽

請使用 Zola 0.23.6 或更新版本；本主題以 0.23.6 測試。
在使用此主題的 Zola 網站根目錄執行：

```sh
zola build
```

如需本機預覽及自動重新建置，執行：

```sh
zola serve
```

## 自訂範本

本主題使用 Tera 2 元件，定義位於 `templates/_components.html`。
覆寫範本時，請使用元件呼叫語法，並明確傳入分頁器：

```jinja
{{ <article_block post={post} /> }}
{{ <paginator_block paginator={paginator} /> }}
```

元件透過 `{% component article_block(post) %}` 與 `{% component paginator_block(paginator) %}` 定義。
