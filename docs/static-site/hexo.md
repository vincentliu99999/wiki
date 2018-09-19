# Hexo

```shell
# 安裝 Node.js
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash

# 安裝 Hexo
npm install hexo-cli -g
```

## 使用

```shell
# 初始化
hexo init <folder>
cd <folder>
npm install

# 產生靜態檔案
hexo generate

# 啟動伺服器 預設是 http://localhost:4000/
hexo server

# publish
hexo clean
hexo generate # hexo g
hexo depoly # hexo d
```

### 建立文章

layout: `post`, `page`, `draft`

```shell
hexo new [layout] <title>
```

### 發布

```shell
# install requirement depoly to git
npm install hexo-deployer-git --save

# publish
hexo clean
hexo generate # hexo g
hexo depoly # hexo d
```

## 設定

`_config.yml`

### Site

```yml
# Site
title: 攻城獅的奇幻冒險旅程
subtitle:
description:
keywords:
author: Vincent Liu
language:
timezone:
```

### URL

```yml
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://vincentliu99999.github.io
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
```

### Deployment

```yml
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:vincentliu99999/vincentliu99999.github.io.git
  branch: master
  message: "Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }}"
```

### Feed

```shell
npm install hexo-generator-feed --save
```

```yml
# Feed
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
  content:
  content_limit: 140
  content_limit_delim: ' '
  order_by: -date
```

## 其他

### TOC

```yml
<%- toc(post.content, {list_number: false}) %>
```

新增 `themes/landscape/layout/_partial/toc.ejs`

```javascript
<% if (post.toc != false) { %>
<div id="toc">
  <%- toc(post.content, {list_number: false}) %>
</div>
<% } %>
```

修改 `themes/landscape/layout/_partial/toc.ejs`

```ejs
<%- partial('toc') %>
<%- post.content %>
```

修改 `themes/landscape/source/css/_partial/article.styl`

```css
#toc
  float right
  background-color #eee
  font-size 0.8em
  color color-link
  margin 5px
  .toc
    list-style none
```

## theme

[hexo黑色主题](https://www.jianshu.com/p/39cff9966304)

```shell
git clone https://github.com/probberechts/hexo-theme-cactus.git themes/cactus
```