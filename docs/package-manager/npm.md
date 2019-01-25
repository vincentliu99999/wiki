# npm

Node.js 裡面就包含了 npm

- [npm help docs](https://docs.npmjs.com/)
- [更新](https://www.npmjs.com/get-npm)

## 安裝

- mac `brew install node`
- windows [download](https://nodejs.org/en/download/)

```shell
node -v # 確認 Node.js 已安裝
npm -v # 確認 npm 已安裝
npm start
```

## command line

```=shell
npm list -g --depth=0 # list global package
npm install npm@latest -g # 更新
```

## [Node Package](https://www.npmjs.com/)

[TLDR-pages](https://www.npmjs.com/package/tldr)
[cloc](https://www.npmjs.com/package/cloc)

```shell
npm install bower -g # package manager
npm install cloc -g # 計算原始碼行數
npm install doctoc -g # 為 markdown 建立目錄
npm install tldr -g # 社群維護的 man page
npm install webpack -g
npm install yo -g
```

### [Plato](https://github.com/es-analysis/plato): 原始碼視覺化

```shell
npm install -g plato # install module
plato -r -d report src # 分析 /src 中的 js，產生分析報告於 /report 
```