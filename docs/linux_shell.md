# linux shell

## 基礎指令

* 目錄操作： `ls`, `cd`, `pwd`, `mkdir`, `rmdir`
* 檔案操作： `cp`, `rm`, `mv`
* 檔案內容： `cat [file]`, `more [file]`, `less [file]`

## 目錄

* `/`: 跟目錄
* `~`: home
* `.`: now dir
* `..`: 上一層目錄
* `-`: 上一次的工作目錄

## 快捷鍵

* [Ctrl]+[u] 清除單行指令
* [Ctrl]+[l]`: 清空畫面
* [shift]+[PageUp], [shift]+[PageDown]： 上下移動螢幕畫面

## vim

上下移動 `:m +1`, `:m -2`

## daemon

預設要啟動： chkconfig daemon on
預設不啟動： chkconfig daemon off
觀察預設為啟動否： chkconfig --list daemon