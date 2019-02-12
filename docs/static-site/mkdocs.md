# [MkDocs](http://www.mkdocs.org/)

常用指令

```shell
mkdocs new [dir]
mkdocs build --clean
mkdocs gh-deploy
```

## 安裝

* Mac 使用 [Homebrew](https://brew.sh)

```sh
brew install mkdocs
```

* Windows 請用 python or chocolatey

```shell
# python
python get-pip.py
pip install --upgrade pip
pip install mkdocs
mkdocs --version

# chocolatey
choco install mkdocs
```

## 建立知識庫

* 預設會產生`mkdocs.yml`, `docs/index.md`

```sh
mkdocs new [dir-name]
```

* `mkdocs.yml`: 知識庫設定檔
* `docs/`: markdown 文件目錄
  * 修改 `mkdocs.yml`

```yml
site_name: wiki
pages:
    - Home: index.md
    - About: about.md
```

* 新增文件

```sh
curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
```

* 本地端即時預覽，改文件也會即時更新，url: <http://127.0.0.1:8000/>

```sh
mkdocs serve
```

* 根據你的文件及設定，產生網站內容在新的目錄下： `site`

```sh
mkdocs build
echo "site/" >> .gitignore 
mkdocs build --clean # Removing documentation
```

## 發佈知識庫

* 發佈到 Github Page

```sh
mkdocs gh-deploy
```

### 主題

#### [Material theme](https://github.com/squidfunk/mkdocs-material) 支援 emoji

```shell
pip install mkdocs-material
```

安裝後要啟用[PyMdown Extensions](http://squidfunk.github.io/mkdocs-material/extensions/pymdown/)

#### [MkDocs Bootstrap Theme](http://mkdocs.github.io/mkdocs-bootswatch/)

```shell
pip install mkdocs-bootswatch
```