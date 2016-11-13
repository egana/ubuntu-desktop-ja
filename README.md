# ubuntu-desktop-ja

Ubuntu の日本語デスクトップ環境を作るための Vagrantfile です。

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
英語キーボードは削除していいです。

## インストールパッケージ

Ansible を使って各種パッケージがインストールできるようにしています。
Playbook には下記を用意しています。
初回起動時に自動で実行されるのは `bootstrap` だけです。
追加の Playbook を実行したい場合は、 `Vagrantfile` の `provision` の項目のコメントを外して

    $ vagrant provision --provision-with <playbook>

を実行してください。

### bootstrap

Ubuntu Japanese Team が推奨するパッケージをインストールします。
その他下記の変更を行っています。

* タイムゾーンを `Asia/Tokyo` に設定
* 起動時に `System program problem detected` というダイアログが出ないようにする（初回起動時は出てしまう）

### develop

開発でよく使用されるライブラリと docker をインストールします。

### extra

`develop` でインストールされるパッケージに加えて各種言語のライブラリなどをインストールします。

## ライセンス

[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

Copyright (c) 2016 Kenichiro IDA
