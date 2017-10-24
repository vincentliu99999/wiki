# 安裝

系統要求：[Installation - Laravel - The PHP Framework For Web Artisans](https://laravel.com/docs/master/installation#server-requirements)

由於 Laravel 利用 Composer 來管理套件，請先安裝 [Composer](http://getcomposer.org/)

## 透過 Laravel 安裝

```sh
composer global require "laravel/installer"
```

安裝好後請先將 `$HOME/.composer/vendor/bin` 加入環境變數 $PATH 中

個人使用 iTerm2 + zsh

```sh
echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.zshrc
```

之後可以直接透過 `laravel` 指令來建立專案

```sh
# 指定目錄名稱
laravel new <project-name>

# 目前目錄
laravel new
```

## 透過 Composer Create-Project

```sh
composer create-project --prefer-dist laravel/laravel <project-name>
```