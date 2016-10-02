# ubuntu-desktop-ja

Ubuntu の日本語デスクトップ環境を作るための Vagrantfile です。

## インストールパッケージ

`boxcutter/ubuntu1404-desktop` をベースにして、追加で下記のパッケージをインストールします。

* Ubuntu Japanese Team 推奨パッケージ
* docker
* docker-compose
* docker の `buildpack-deps:trusty` イメージでインストールされるパッケージ

## 変更内容

* タイムゾーンを `Asia/Tokyo` に設定
* 一部の環境で `System program problem detected` というダイアログが出ないようにする（初回起動時は出てしまう）

## 日本語化

Ubuntu が起動したら右上の歯車のアイコンから

`System settings...` > `Language Support`

とたどります。ダイアログが表示されるので `install` を選択し
言語パッケージをインストールします。
パスワードを聞かれるので `vagrant` と入力します。

`Language` タブで `日本語` をドラッグして一番上に持って行き、 `Apply System-Wide` ボタンを押します。
`Regional Formats` でも `日本語` を選択し、 `Apply System-Wide` ボタンを押します。

再ログインすれば日本語化されます。

## 日本語入力

デスクトップ右上のキーボードのアイコンから `設定` を選択し
`入力メソッド` の項目に

1. キーボード - 日本語 - 日本語（かな 86）
1. Mozc

という入力メソッドがこの順に並ぶように設定してください。

## ライセンス

MIT License

Copyright (c) 2016 Kenichiro IDA
