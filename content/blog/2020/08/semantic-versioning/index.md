---
title: "Semantic Versioning"
date: "2020-08-10T08:12:03.284Z"
description: "Semantic Versioning"
tags: ["oss"]
---

バックエンドエンジニアの[ロードマップ][ロードマップ]に沿ってエンジニアとしての自己肯定感を養うシリーズです。

<br>
<br>

## セマンティックバージョニング？

アプリに振るバージョン番号を[SemVer][semver]というルールに従って付与しましょうというものです。
確かにバージョン番号に意味を持たせることで、ユーザからもアプリのバージョン番号が上がればバグ修正なのか機能追加なのかわかりますし、プログラムからも互換性を考慮して処理を分けることができるのでよいですね。

<br>

### これだけ覚えておけば OK

バージョン番号の形式は、`メジャー.マイナー.パッチ`です。(例：`1.0.0`)

#### メジャー

- 後方互換性がない変更があった時にはこの番号を上げなければいけません(MUST)
- この番号を上げた際には、マイナー/パッチの番号は 0 にリセットしなければいけません(MUST)
- この番号が「0」の場合は初期開発用として扱います。リリースの段階でこの番号を「1」に上げます。

#### マイナー

- 後方互換性を保ちつつ、機能追加のある時にはこの番号を上げなければいけません(MUST)
- この番号を上げた際には、パッチの番号は 0 にリセットしなければいけません(MUST)

#### パッチ

- 後方互換性を保ちつつ、バグ修正のある時にはこの番号を上げなければいけません(MUST) ※バグ修正とは間違った振る舞いを修正する内部の変更のことをいいます。

### ちょっと踏み込むと

- プレリリースバージョンには、パッチ番号の後ろにハイフンで区切って識別子をつけることができます。(例：`1.1.0-alpha / 1.1.0-beta / 1.1.0-rc`)
  ※ちなみに識別子の`rc`は「release candidate」の略でベータ版よりもさらに製品版に近い品質のバージョンにつけるそうです。（略を初めて知りました。）

- あと npm の packagge.json でもモジュールをセマンティックバージョンで管理してます。（`~`や`^`が付与されているのをよく見ると思います。）
  これについては[上、真ん中、下で覚えるバージョニング範囲指定][上、真ん中、下で覚えるバージョニング範囲指定]がわかりやすかったので共有しておきます。

### 余談

たかがバージョニング、されどバージョニングといった感じでした。知ってて損はないですよね。
この辺を知ってて付与できるかどうかが職業エンジニアとの分かれ道かとも思いました。

[ロードマップ]: https://github.com/kamranahmedse/developer-roadmap#back-end-roadmap
[semver]: https://semver.org/lang/ja/
[上、真ん中、下で覚えるバージョニング範囲指定]: https://qiita.com/takayukioda/items/cb55d3f433af611295a5
