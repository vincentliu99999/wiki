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
brew list # 安裝過的 package
brew leaves # 安裝過的 package，排除 dependency
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

## Java 環境設定

[JDK7](https://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html)

```shell
# java7 要手動下載及安裝
brew tap caskroom/versions
brew cask install java java6 java8

ls /Library/Java/JavaVirtualMachines/
> 1.6.0.jdk        jdk1.7.0_80.jdk  jdk1.8.0_202.jdk openjdk-12.jdk

/usr/libexec/java_home -V
> Matching Java Virtual Machines (5):
>    12, x86_64:	"OpenJDK 12"	/Library/Java/JavaVirtualMachines/openjdk-12.jdk/Contents/Home
>    1.8.0_202, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home
>    1.7.0_80, x86_64:	"Java SE 7"	/Library/Java/JavaVirtualMachines/jdk1.7.0_80.jdk/Contents/Home
>    1.6.0_65-b14-468, x86_64:	"Java SE 6"	/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
>    1.6.0_65-b14-468, i386:	"Java SE 6"	/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home

# 設定 ~/.zshrc
export JAVA_6_HOME=$(/usr/libexec/java_home -v1.6)
export JAVA_7_HOME=$(/usr/libexec/java_home -v1.7)
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_12_HOME=$(/usr/libexec/java_home -v12)

alias java6='export JAVA_HOME=$JAVA_6_HOME'
alias java7='export JAVA_HOME=$JAVA_7_HOME'
alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java12='export JAVA_HOME=$JAVA_12_HOME'

# default to Java12
java12

# =============== 版本切換 ===============
java6
java -version
java7
java -version
java8
java -version
java12
java -version
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