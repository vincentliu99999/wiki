# Chocolately

使用目的

1.  免去繁瑣安裝過程（安裝軟體時有完沒完的下一步或是裝完了，但跟你說 “oops，你少裝了ＸＸＸ喔”）
2. 升級方便
3. 拿到新電腦要裝一堆軟體時

類似 Mac 的 Homebrew

## 安裝

- [cmd 安裝](https://chocolatey.org/install#install-with-cmdexe)
- [PowerShell 安裝](https://chocolatey.org/install#install-with-powershellexe)

## 使用

1. 下指令
2. Chocolatey GUI

`須以管理者身份進行安裝`

## Package

*.nuspec xml version

通常會安裝在 `ChocolateyInstall\lib`，`.mis` 可能會安裝在 `Program Files`

- [ChocolateyGUI](https://chocolatey.org/packages/ChocolateyGUI): 透過 GUI 操作
- [Everything](https://chocolatey.org/packages/Everything): 秒搜檔案
- [Keepass](https://chocolatey.org/packages/keepass): 密碼管理工具
- [Sysinternals](https://chocolatey.org/packages/sysinternals): Process Explorer, Process Monitor, TCP view...
- [Screen To Gif](https://chocolatey.org/packages/screentogif): 錄製 Gif
- [Java Decompiler GUI](https://chocolatey.org/packages/javadecompiler-gui): 反組譯 class 原始碼
- [AWS Command Line Interface](https://chocolatey.org/packages/awscli)

```shell
# hyper https://chocolatey.org/packages/hyper
# choco install hyper -y
# choco upgrade hyper

# Lepton https://chocolatey.org/packages/lepton
choco install lepton -y
choco upgrade lepton

# Sysinternals https://chocolatey.org/packages/sysinternals
choco install sysinternals -y
choco upgrade sysinternals

# AWS Command Line Interface https://chocolatey.org/packages/awscli
# choco install awscli -y
# choco upgrade awscli

# Screen To Gif
choco install screentogif -y
choco upgrade screentogif

# javadecompiler-gui
choco install javadecompiler-gui -y

choco install golang -y
choco install nodejs.install -y
choco install nvm -y
choco install yarn -y
cinst -y ripgrep

# hugo
choco install hugo -confirm
hugo version
hugo new site resource-hugo
cd resource-hugo
git init;
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke;
echo 'theme = "ananke"' >> config.toml
hugo new posts/my-first-post.md
hugo server -D

# document
choco install pandoc -y
pandoc test.md -f markdown -t html -s -o test.html --metadata pagetitle="test"
```

## 指令

```shell
# choco list alias: choco search, clist
choco list --local-only # LocalOnly
choco list -li # LocalOnly
clist -li # sorrtcut choco list -li

# Install/Uninstall/Upgrade
choco install <pkg|packages.config>
cinst <pkg|packages.config>

choco uninstall <pkg|all>
cuninst <pkg|all>

choco upgrade <pkg|all>
cup <pkg|all>

# Outdated 過時的軟體
choco outdated
```

## Reference

* [Command Reference](https://chocolatey.org/docs/commands-reference)
* [Will 保哥的開發人員工具軟體清單 ( 最新 2017 年版 )](https://blog.miniasp.com/post/2017/09/13/Will-2017-Ultimate-Developer-Tool-Software-List.aspx)
* [chocolatey-workshop](https://github.com/ferventcoder/chocolatey-workshop)