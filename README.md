# 自己紹介

[yasuhiroki](https://twitter.com/duck_yasuhiroki)

[A10 Lab Inc.](https://a10lab.com/) で [みんチャレ](https://minchalle.com/) を作っています

AWSのインフラ整備を担当しつつ、 Android アプリの開発に参加するようになってもうすぐ 3年くらい

# 話したいこと

Firebase Remote Config の管理をどうしてますか？

# 前提

アプリの ABテストに Firebase の Remote Config を活用している
Firebase プロジェクトが 3つある

- 開発用
- 検証用
- 本番用

各プロジェクトごとに Remote Config を手動で設定している

# 悩み

- パラメーターの設定を事前にレビューしたい
- 本番用の設定を忘れないようにしたい
- 検証用と本番用に差異がないようにしたい

# 公式ツール

公式の [Firebase CLI](https://firebase.google.com/docs/cli?hl=ja) は Remote Config のサポートが弱い

## できないこと

- Remote Config のパラメーターを追加・変更・削除できない
- parameterGroups に対応していない

# 先行事例

## potatotips #62 (2019/06/18)

[@imaizume](https://twitter.com/imaizume) さんの LT

<script async class="speakerdeck-embed" data-id="0001b3482d524913b9109dc9a7a8de53" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>

remocon が紹介されている

~~4年前から今に至るまで公式ツールは提供されなかったんだなぁ~~

### [remocon](https://github.com/jmatsu/remocon) (Ruby製 CLIツール)

Remote Config のパラメーターを YAML で管理できる

現在は動作しない
Remote Config の機能追加・仕様変更に remocon が対応していないと思われる

# ツールを作る

## コンセプト

### やりたいこと

- パラメーターの設定を変更する
- パラメーターの差分を確認できる
- Android や iOS 用の defaults を生成する

### やらないこと

- リッチなCUI
- 豊富なカスタマイズ性
- 自作ツール独自の表現

いずれ公式ツールが対応したら捨てる前提
不足している機能は他のツールと組み合わせてなんとかする

## DEMO

[firebase-remote-config-cli](https://github.com/yasuhiroki/firebase-remote-config-cli)

- Node.js 製
  - `firebase-admin` SDK を利用
  
# 聞きたいこと

皆さんは Firebase Remote Config の管理をどうしてますか？

