# 【Laravel道場系列 III】PHPUnit測試入門與Laravel測試功能簡介

* 沒有寫測試的開發方式: F5
* TDD開發方式
* Laravel開發方式

## 測試方法

單元測試: test one class
整合測試: test between class
驗收測試: test by browser, selenium

```sh
composer require phpunit/phpunit
composer require mockery/mockery # 例如網路資料先下載
```

generate phpunit.xml

```sh
vendor/bin/phpunit --generate-configuration # 產生測試設定檔
vendor/bin/phpunit tests/AssertionsTest # 執行 test case
php -S localhost:81 # start server
```

1. autoload
1. `/tests`: Test 結尾檔案用來寫測試程式
1. `/src`

```php
assertEquals // 驗證值
test_assert_same // 驗證型態
```

## annotation

@depends
@test: phpunit 測試 function 不加 test 也行，打中文也行

## code coverage

### mock

* Dummy: 不需使用，但要存在才能測試
* stub: input, output

常用方法

1. shouldReceive
1. andReturn

## Laravel

* feature
* unit by dusk
* brwowser

by sqllite

RefreshDatabase
透過 instance 來注入

## 範例: 爬台銀黃金牌價

* [recca0120/mockery_demo](https://github.com/recca0120/mockery_demo)

## reference

* [recca0120 (Recca Tsai)](https://github.com/recca0120)

## reference - PHP function

* [PHP: file_get_contents - Manual](http://php.net/manual/en/function.file-get-contents.php)
* [PHP: preg_match - Manual](http://php.net/manual/en/function.preg-match.php)

## referece - VsCode

* [VSCode-PHPUnit&#32;-&#32;Visual&#32;Studio&#32;Marketplace](https://marketplace.visualstudio.com/items?itemName=recca0120.vscode-phpunit)