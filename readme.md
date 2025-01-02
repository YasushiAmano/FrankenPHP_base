# 環境構築

## FrankenPHP

dunglas/frankenphp:1

## 初期設定

Laravelはsrcディレクトリに配置しています。

srcの中で.env.base_sampleコピーして.envを作成してください。

## Dockerを起動

```sh
docker compose up -d
```

### アプリケーションキーの生成

.envのAPP_KEYを生成します。

以下のコマンドは、コンテナー内で実行してください。

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

## IDE Helper（開発環境のみ）

```sh
# PHPDoc生成
php artisan ide-helper:generate
# モデルのPHPDoc生成
php artisan ide-helper:models -N
# DBのPHPDoc生成
php artisan ide-helper:meta
```

### Jetstream（高機能な認証）

Jetstreamは、 ログイン、新規登録、メール検証、２段階認証、セッション管理、APIサポート(Laravel Sanctum)、チーム管理などをサポートしています。

Laravelの初期画面の右上にLoginとRegisterのリンクがあります。
Registerから管理者を作成してください。

Jetstreamの初期化は、コンテナー内で実行してください。

```sh
php artisan jetstream:install livewire
```
