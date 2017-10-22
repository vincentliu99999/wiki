# Homestead

- 快速建立一致化的本地開發環境
- 彈性運用虛擬機器

## 安裝

- 下載＆安裝 [Oracle VM VirtualBox](https://www.virtualbox.org/wiki/Downloads)

- 下載＆安裝 [Download - Vagrant by HashiCorp](https://www.vagrantup.com/downloads.html)

```sh
# 安裝成功會顯示版本
vagrant version
```

- 下載 Homestead vagrant box，大約 10 分鐘，可以中場休息一下

```sh
# 選擇 virtual box
vagrant box add laravel/homestead
```

```sh
# 確認 Homestead vagrant box 下載完成
cd ~/.vagrant.d/boxes
# 成功的話會有出現目錄 laravel-VAGRANTSLASH-homestead
ll

cd laravel-VAGRANTSLASH-homestead／4.0.0/virtualbox
# box-disk1.vmdk
ll
```

- 安裝 Homestead

先 clone 到本機

```sh
cd ~
git clone https://github.com/laravel/homestead.git Homestead
```

找個穩定版本安裝吧 [laravel/homestead](https://github.com/laravel/homestead/releases)

```sh
cd Homestead

// Clone the desired release...
git checkout v6.5.0
```

- 建立設定檔 `Homestead.yaml`

```sh
bash init.sh
```

## 設定 Homestead

### Provider

`provider`: `virtual box`

### 共享資料夾

`folders`：有異動的檔案會同步到本機與 Homestead 環境

```yaml
folders:
    - map: ~/Code
      to: /home/vagrant/Code
```

### Nginx Sites

`sites`: 對應 domain 到 Homestead 中的資料夾

有變更時，執行指令來更新 Nginx 設定

### 修改 hosts 檔

將 Homestead設定的 IP 加到 host 檔案中，request 才會重新導向 Homestead

- Mac/Linux: `/etc/hosts`
- Windows: `C:\Windows\System32\drivers\etc\hosts`

```log
192.168.10.10  homestead.test
```

### 啟動 Vagrant Box

`Homestead.yaml` 設定好後就可以執行 `vagrant up` 來開虛擬機囉

## 常用功能

- 透過 SSH 連接(進入 Homestead 目錄後執行)：`vagrant ssh`
- `sites` 異動：`vagrant reload --provision`

## 範例專案

- [基本任務清單 - Laravel - 為網頁藝術家創造的 PHP 框架](https://laravel.tw/docs/5.2/quickstart)
- [中級任務清單 - Laravel - 為網頁藝術家創造的 PHP 框架](https://laravel.tw/docs/5.2/quickstart-intermediate)

## 參考資料

- [Laravel Homestead - Laravel - 為網頁藝術家創造的 PHP 框架](https://laravel.tw/docs/5.3/homestead)
- [如何在OS X安裝Homestead?](http://oomusou.io/laravel/homestead/homestead-osx/)
- [Homestead · Laravel 5 學習筆記](https://kejyuntw.gitbooks.io/laravel-5-learning-notes/environment/Environment-Homestead-README.html)