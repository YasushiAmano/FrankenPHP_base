# 環境構築

## FrankenPHP

dunglas/frankenphp:1

## パッケージ

下記のようにしてOctaneをインストールしています。

また、日本語化も行っています。


```sh
composer require laravel/octane
php artisan octane:install
php artisan octane:start
```

## 日本語化パッケージ

```sh
composer require laravel-lang/lang
composer require laravel-lang/publisher
php artisan lang:add ja
```

## 初期設定

### アプリケーションキーの生成

.envのAPP_KEYを生成します。

```sh
php artisan key:generate
```

### マイグレーションの実行

```sh
php artisan migrate
```

#### セッションテーブルの作成（.envでSESSION_DRIVER=databaseを使用している場合）

```sh
php artisan session:table
php artisan migrate
```
