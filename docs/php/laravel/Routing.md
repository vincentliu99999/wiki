# 路由

可以將網址分配給 `Controller` 或是直接顯示 `View`

## 路由動作

```php
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);

# 多個動作
Route::match(['get', 'post'], '/', function () {
    //
});

# 所有動作
Route::any('foo', function () {
    //
});
```

## CSRF 防護

HTTP 動作為 POST, PUT, 或 DELETE 時，HTML from 需加上 CSRF token

[CSRF Protection - Laravel - The PHP Framework For Web Artisans](https://laravel.com/docs/master/csrf)

## 暫存

查看所有路由

```sh
php artisan route:list
```