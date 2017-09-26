# 【Laravel道場系列 I】Composer基礎入門與實戰應用

透過 PSR-4，利用 Packagelist 來找套件，用 Composer 來管理

## 實作 - 成員通訊清單

### 資料夾結構調整

* 將所有的程式碼移到 `/public`
* 變更 apache document root

### 把設定檔獨立出來

* 新增資料夾 `/config`, 新增設定檔，例如：`database.php`，包含資料庫相關設定，`define('DB_HOST', 'xxxx');`
* 有需要時再透過 require 來使用 `require __DIR__.'/../config/database.php'`

### 實作 DB 物件(注意 namespace)

#### DB

* class 名稱盡量與檔案名稱大小寫一致
* 同樣需要 `require`

#### Namespace

例如 新增 class `/src/Database/Employee.php`, namespace: `APP\Database`

* 包含 CRUD 方法
* constructor 參數加上 PDO
* 同樣需要 `require`

### 實作 helper function

* 例如：很多頁面共用的 header, footer, copyright
* global function 可以用 `function_exists` 檢查，再決定要不要 include
* 同樣需要 `require`

### 如何解決 include 地獄

* 把所有物件包在 `bootstrap.php`，但會 include 到不必要的物件
* PHP 7.2 要被棄用的 `__autoload()`(賣溝用阿)
* `spl_autoload_register()`，可指定物件不存在時要去哪邊找
  * 非物件的可以直接放到 array 裡去透過 `foreach` 處理
* 但很多套件有他自己的 autoloader 機制

## Composer

只要 require Composer 的 autoloader 就好了

composer.phar = PHP 的執行檔

```sh
composer self-update
composer self-update --rollback
php -v
php -r "echo PHP_BINARY;" # 實際執行的版本
php -m # PHP module
```

```sh
composer init # 新增 composer.json
composer require # 安裝，新增 composer.lock 紀錄實際安裝版本
composer update # 更新
```

1. package name(vender/name)
1. description
1. author(Git account)
1. mini: 建議用 stable
1. package type: project
1. license: proprietary
1. require
1. require-dev: 測試時才使用的

### 範例(google: composer 實戰)

整合套件到專案中

* 偵錯工具: recca0120/laravel-tracy
* ...

### 三大 autoload 模式

手動編輯 composer.json，完成後要執行指令 `composer dump`

1. psr-4: 至少有一層 namespace
1. classmap: 檔名與 class 名不一樣時使用
1. files: 提供檔案路徑

## 參考資料

* [Composer](https://getcomposer.org/download/)
* [wagon：免安裝可攜的 Laravel 開發環境](http://www.laravel-dojo.com/opensource/wagon)
* php-fig, PSR-4
* [Packagist](http://ttps://packagist.org/) Composer 套件軍火庫
* [ziadoz/awesome-php](https://github.com/ziadoz/awesome-php) 套件推薦
* [The League of Extraordinary Packages](https://thephpleague.com/) 號稱品質很好的套件
* [recca0120/laravel-bridge](https://github.com/recca0120/laravel-bridge)