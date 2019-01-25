# Composer

## 常用指令

```shell
composer self-update # 更新 Composer
composer show # 列出安裝的 package
composer validate # 驗證 composer.json
```

## 套件 [Packagist](https://packagist.org/)

[thephpleague/oauth2-client](https://github.com/thephpleague/oauth2-client)

### debugger

* [http://127.0.0.1:8000/debug/phpdebugbar.php](http://127.0.0.1:8000/debug/phpdebugbar.php)
* [http://127.0.0.1:8000/debug/tracy.php](http://127.0.0.1:8000/debug/tracy.php)
* [http://127.0.0.1:8000/debug/var_dumper.php](http://127.0.0.1:8000/debug/var_dumper.php)

### [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)

檢查 coding style 是否符合 PSR 規範

常用指令

```shell
phpcs -i # 列舉 coding style
phpcs --standard=PSR1 -e # 查看 coding style 會做哪些檢茶

phpcs --config-show # 檢查設定
phpcs --config-set default_standard PSR2 # 設定用 PSR-2 檢查 coding style
phpcs --config-set colors 1 # 設定報表言顏色(預設不會上色)
phpcs --config-set show_progress 1 # 檢查時顯示進度

phpcs . # 針對目錄前目錄下的檔案檢查 coding style
phpcbf phpdebugbar.php # 修復單一檔案
phpcbf . # 修復目錄下所有檔案
```