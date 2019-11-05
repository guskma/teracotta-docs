---
title: '[API] connect'
date: 2019-11-03 23:26:11
tags:
  - API
  - _global
  - API v0.1.0
category:
  - API
  - _global
---

機器にtelnet/ssh/consoleのいずれかの方法で接続します。

## 使い方

```
[ini_example]
API = 'connect'
protocol = 'ssh'
port = '22'
dest = '192.168.0.1'
auth = 'password'
loginuser = 'cisco'
password = 'cisco'
```

## 入力値

### 共通

- protocol (string)
  接続種別(プロトコル)。console, telnet, ssh のいずれかを選択できます。
  入力値は接続種別ごとに異なる引数を用意しています。以下も併せて確認してください。

### console

- port (string)
  COMポート番号を指定します。(0-255)
  指定しないまたは0の場合はCOM1から順に接続を試行します。
  COMポートへの接続は、他のプロセスが使用中の場合に失敗します。

### telnet

- port (string)
  接続するTCP番号を指定します。
  指定しない場合、デフォルトの23番ポートで接続を試みます。
- dest (string)
  接続先のIPアドレスまたはホスト名を指定します。

### ssh

- port (string)
  接続するTCPポート番号を指定します。
  指定しない場合、デフォルトの22番ポートで接続を試みます。
- dest (string)
  接続先のIPアドレスまたはホスト名を指定します。
- ssh_ver (integer)
  SSHのプロトコルバージョンを指定します。
  指定しない場合、デフォルトのバージョン2で接続を試みます。
- auth (string)
  認証方法を指定します。以下の認証方法が指定可能です。
  - password
    一般的なログインID/パスワードでの認証方法です。
  - publickey
    公開鍵認証を利用した認証方法です。
  - challenge
    チャレンジレスポンスを利用した認証方法です。
  - pageant
    エージェント接続を利用した認証方法です。
- loginuser (string)
  ログインIDを指定します。
- password (string)
  ログインパスワードを指定します。
- keyfile (string)
  秘密鍵の保存先を指定します。

## 戻り値

- result (integer)
  接続結果。0で失敗、1以上で成功を返します。  
  またconsoleで接続し成功した場合は接続したポート番号を返します。

## 補足

プロトコルを直接指定してAPIを呼び出すこともできます。

```
API = 'connect_ssh'
```
