# [Homebrew](https://brew.sh/)

安裝 macOS 沒提供的 linux 工具

## 安裝方式

參考[官網](https://brew.sh/index_zh-tw.html)

## 基本指令

```shell
brew -v # 安裝版本
brew config # 查看 Homebrew 及系統設定

# 更新
brew update
brew update && brew upgrade

# 安裝工具
brew install 工具
brew uninstall 工具

# 搜尋
brew search [TEXT|/REGEX/] # 搜尋工具
brew list # 安裝過的工具
brew leaves
brew cask list
```

![brew config](https://i.imgur.com/NIpJ6Hm.png)

```shell
brew search 工具

# search result
exercism
mkdocs
pandoc
homebrew/php/php71
wget
zsh-autosuggestions
```

[Exercism](https://exercism.io/): coding 練習

```shell
https://exercism.io/my/solutions/03b4014b56a94705ab430a01fb7764e6
# download exercise
exercism download --exercise=hello-world --track=php

# run testcase
phpunit hello-world/hello-world_test.php

# submit solution
exercism submit ./hello-world/hello-world.php
```

## 工具

* [bash](https://formulae.brew.sh/formula/bash)
* [bat](https://github.com/sharkdp/bat) cat(1) with syntax highlighting
* [jq](https://stedolan.github.io/jq/) command-line JSON processor
* [exa](https://the.exa.website/) A modern replacement for ls

```shell
exa -l --header --tree --level=2
exa -l --grid --header
```