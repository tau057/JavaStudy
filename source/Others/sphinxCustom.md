# Sphinxデザインのカスタム

## 概要

sphinxデザインの手動調整の方法を記載。

sphinxデザインは、基本的に公式から提供されているテーマで事足りるとは思うが、  
本document独自のカスタムとして、見出しカラーを見出しサイズごとに変えている。  
（いちからCSS覚えるのもだるかったのでChatGPTに任せたりもした。生成AI便利だねぇ。）

## カスタム内容

### 追加・修正するファイル

- （追加）source/_static/custom.css
- （修正）source/conf.py
  - 以下を追記（上記のCSSファイルを適用するための設定）

  ```
    html_css_files = ['custom.css']
  ```

- custom.cssの中身

```
/* static/custom.css */

/* 全ての見出し (h1 ～ h6) に共通の設定 */

/* h1 見出し */
section h1 {
    background-color: rgb(103, 174, 219); /* 控えめな水色系 */
    padding: 3px 10px; /* 上下のパディングを小さく、左右は少し広め */
    border-radius: 5px;
    color: #003366; /* 文字色（濃い青系） */
}

/* h2 見出し */
section h2 {
    background: linear-gradient(to right, rgba(103, 219, 111, 0.6), rgba(103, 219, 111, 0.6) 80%, transparent 100%);
    padding: 3px 10px;
    border-radius: 5px;
    color: #003366;
}

/* h3 見出し */
section h3 {
    background: linear-gradient(to right, rgba(195, 218, 102, 0.4), rgba(195, 218, 102, 0.4) 60%, transparent 100%);
    padding: 3px 10px;
    border-radius: 5px;
    color: #003366;
}

/* h4 見出し */
section h4 {
    background: linear-gradient(to right, rgba(195, 218, 102, 0.3), rgba(195, 218, 102, 0.3) 50%, transparent 100%);
    padding: 3px 10px;
    border-radius: 5px;
    color: #003366;
}

/* h5 見出し */
section h5 {
    background: linear-gradient(to right, rgba(195, 218, 102, 0.2), rgba(195, 218, 102, 0.2) 40%, transparent 100%);
    padding: 3px 10px;
    border-radius: 5px;
    color: #003366;
}

/* h6 見出し */
section h6 {
    background: linear-gradient(to right, rgba(195, 218, 102, 0.1), rgba(195, 218, 102, 0.1) 30%, transparent 100%);
    padding: 3px 10px;
    border-radius: 5px;
    color: #003366;
}

```