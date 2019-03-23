# [Homebrew](https://brew.sh/)

安裝 macOS 沒提供的 linux 工具

安裝方式參考[官網](https://brew.sh/index_zh-tw.html)

## 基本指令

```shell
brew -v # 安裝版本
brew config # 查看 Homebrew 及系統設定
brew update # 更新 homebrew
brew upgrade # 更新所有 package
brew upgrade <package> # 更新指定的 package
brew update && brew upgrade

# 安裝工具
brew install <package>
brew uninstall <package>
brew list # 安裝過的 CLI 工具
brew leaves # 安裝過的 CLI 工具，排除 dependency
brew cask list # 安裝過的 GUI 工具

# 搜尋
brew search [TEXT|/REGEX/] # 搜尋工具
```

![brew config](https://i.imgur.com/NIpJ6Hm.png)

```shell
brew install mkdocs pandoc zsh-autosuggestions
brew install homebrew/php/php71 wget bash bat jq exa
brew cask install aerial iterm2 eclipse-jee
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