---
title: '[API] raw_command'
date: 2019-11-03 23:26:11
tags:
  - API
  - _global
category:
  - API
  - _global
---

指定したコマンドをそのまま入力し、プロンプトが戻ってくるのを待ちます。

## 使い方

```
[api_example]
API = 'raw_command'
command = 'show version'
```

## 入力値

- command (string)
  ターミナル上で実行するコマンドを入力します。
- prompt (string)
  待ち受けるプロンプト文字列を入力します。(\*)
- prompt_re (string)
  待ち受けるプロンプトの正規表現を入力します。(\*)

(\*) `prompt` 及び `prompt_re` はログイン時に設定されるため、基本的に入力の必要はありません。


## 戻り値

- result (integer)
  コマンドが失敗した場合(タイムアウト)は0が入ります。
  成功した場合は1が入ります。
  ※teratermの `wait` を利用した場合の戻り値です。

## 補足

各機器ごとに同じ `raw_command` APIを用意しています。

これはエラーメッセージの検出など、各機器固有のメッセージを抽出するためです。

詳しくはそれぞれの `raw_command` APIを参照してください。
