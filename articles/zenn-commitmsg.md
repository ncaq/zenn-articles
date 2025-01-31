---
title: "Zenn執筆時のコミットメッセージを考える"
emoji: "📝"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: ["zenn", "git", "github", "zenncli"]
published: true
---

# はじめに

Zennには[Zenn CLI](https://zenn.dev/zenn/articles/install-zenn-cli)と呼ばれるコマンドラインツールがあり、記事の管理をGitHub、記事の執筆をローカルのエディタを使うといった執筆が可能となっています。

Zennの執筆環境周りについての説明は以下の公式記事にまとめられています。

https://zenn.dev/zenn/articles/editor-guide

Web上のエディターだけに縛られることなく、記事の執筆、記事のバージョン管理ができるといった執筆体験がとても新鮮だったというのが私のZennを積極的に使おうとしたきっかけの1つでもあります。

普段、プログラミングを学習する中でのアウトプットとしてZennに投稿する記事を執筆する中で、上記のZenn CLIを使って記事の管理をしています。
ローカルで記事を執筆し、GitHubリポジトリへプッシュすることで記事の更新が行えるのですが、その際にコミットメッセージをどのように編集してコミットするのがベストなのか悩むことがありました。

記事の執筆に関して、コミットメッセージを見るのは基本的に自分だけなので自分が見てわかればそれでいいというのはありますが、やはり管理するうえでわかりやすいことに越したことはないと感じます。

# プレフィックスとは？

プレフィックス（prefix）とは英語で**接頭辞**のことです。

GitHubのコミットメッセージを見るとき目にすることが多いです。
使用するプレフィックスの種類、プレフィックス仕様の有無などは各々のプロジェクトによってルールが定められていることが多いようです。
プレフィックスを適切につけコミットログのフォーマットを統一することで**コミット、コミットログの検索がしやすくなる、レビューをしやすくなる**とったメリットがあるそうです。
フォーマットの統一ができ、それぞれのコミットの内容が見やすくなるという点では個人開発や、記事の管理にも活用できると感じました。

# 個人的な運用について

コミットメッセージの先頭にプレフィックスをつけワンライン（1行）形式にするのが個人的に運用しやすいと感じました。

プレフィックスについては以下の記事を参考にしています。

https://qiita.com/numanomanu/items/45dd285b286a1f7280ed

https://qiita.com/konatsu_p/items/dfe199ebe3a7d2010b3e

上の記事ではともに[angular.js/DEVELOPERS.md](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#type)が参考にされています。
Gitコミットガイドラインの中にプレフィックスとして8つ挙げられていますが、それぞれしっかりとした意味を持っており、プレフィックを見ただけで意味がわかりやすいと感じました。

これらを踏まえた上で考えた結果、個人的なプレフィックス運用方針は以下のようになりました。

| プレフィックス | どんなときにつけるのか                 |
| -------------- | -------------------------------------- |
| add:           | 新規に記事を作成したとき               |
| update:        | 記事を追記、更新したとき               |
| style:         | 記事の文体やマークダウンを修正したとき |
| fix:           | 記事の誤字・脱字を修整したとき         |
| publish:       | 記事をZennに公開したとき               |
| chore:         | パッケージをアップデートしたとき       |

あまり多くても管理が大変というのと、プレフィックスについて悩む時間を減らしたいと考えた結果、上記の6つになりました。

# まとめ

今までコミットメッセージにプレフィックスをつけずにコミットしていましたが、プレフィックスが付くことでパッと見で変更点を把握しやすいと感じました。

今までの記事管理のコミットメッセージのルールが定まっておらず、毎回コミットメッセージが煩雑化してしまっていたため、今後見直して統一化できるようにしたいです。

調べる中でプレフィックスに絵文字を含め視覚的にわかりやすくするなど、工夫次第でかなり便利に活用できると感じました。
コミットメッセージには正解がないため、どのように運用するかを様々なリポジトリやドキュメントを見ながら吟味していくのも楽しいです。私も自分の中でのベストプラクティスを模索中なので今後執筆を続けていく中で、もっと改善していきたいです。

最後まで読んでいただきありがとうございました。