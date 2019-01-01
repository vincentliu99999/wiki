# 【Laravel道場系列 II】Laravel框架簡介及實務展示

follow psr, plenty library

## 開發環境

Laravel 5.5
HTTP server suppory rewrite
contain plenty library

Mac default case-unsensitive
solution: Homestead

### Homestead - local 的開發環境

folder: 掛載資料夾
site: setting document root

```sh
vagrant up # port forwarding, mount local folder
vagrant up --provision # 有加新的 site 時需要
vagrant ssh # 連接虛擬機, require ssh key
```

注意事項

* 安裝完要重啟
* Mac 的 timemachine 要排除 Homestead
* Homestead 頗耗電

## Composer

```sh
# 建立專案
composer create-project laravel/laravel blog --prefer-dist # 頗慢
laravel new blog # 利用 laravel/installer, composer.lock 已產生，速度比較快
```

/public/: 對外公開資料夾
/public/index.php: 程式進入點
/app/: 大部分的PHP，PSR-4 對應 namespace

## artisan

在 project folder 中使用

```sh
artisan env # 目前環境
```

### DB migration

1. 建立新增&還原計畫
1. GUI確認結果

```sh
artisan make:migration create_{name}_table # 新增 migration 檔案
php artisan make:migration create_employees_table --create=employees ## 範例: 新增 table
php artisan make:migration add_test_column_in_employees_table --table=employees ## 範例: 加欄位
artisan mirgate # 開始 migrate
artisan migrate:rollback # 上一個批次的動作還原
```

```php
$table->timestamp('publish_at');
$table->softDeletes(); // 自動新增欄位: deleted_at
$table->timestamps(); // 自動新增欄位: created_at, updated_at
```

env helper function 會先去 .evn 找，找不到才會用預設值

### Seeding - 新增測試資料

DatabaseSeeder
資料真實性

```sh
artisan make:seeder {seeder_name}
artisan make:model {model_name}
artisan db:seed # 倒資料，建議可以先清除資料
```

## Route

開始寫程式&debug的地方
通常會由 Controller 接手
用 `$data` 回傳給 view

```sh
artisan make:controller {model}Controller
artisan make:controller {model}Controller --resource ## 建立預設方法
```

## Blade

Model 取名為 單數

Mass assignment: fillable(建議使用), guarded

## reference

* [Laravel Homestead - Laravel - The PHP Framework For Web Artisans](https://laravel.com/docs/5.5/homestead)
* [Download - Vagrant by HashiCorp](https://www.vagrantup.com/downloads.html)
* [Packalyst :: Packages for Laravel](https://packalyst.com/)