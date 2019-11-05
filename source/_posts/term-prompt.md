---
title: '[Lib] prompt'
date: 2019-11-03 23:34:13
updated: 2019-11-03 23:34:13
tags:
  - Lib
  - term
category:
  - Lib
  - term
---

プロンプト文字列を取得します。

## 使い方

```
include 'lib\term\prompt.ttl'

; 取得したプロンプト
messagebox prompt 'plane'

; 取得したプロンプトの正規表現メタ文字をエスケープしたもの
messagebox prompt_re 'regexpression'
```

## 入力値

なし

## 戻り値

- prompt (string)
  取得したプロンプト文字列
- prompt_re
  取得したプロンプト文字列のメタ文字をエスケープしたもの

## 補足

`prompt_re` は teratermマクロコマンド `waitregex` や `matchstr` で利用するために用意しています。


