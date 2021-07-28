---
title: "Create React Appで使うパッケージマネージャをnpmに強制する"
emoji: "💼"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["createreactapp","npm"]
published: false
---

# はじめに

[Create React App](https://create-react-app.dev/)ではローカルにYarnがインストールされているとデフォルトでパッケージマネージャとしてYarnが使われます。**Yarnがローカルにインストールされている状態**で`npx crate-react-app my-app`とした場合は以下のように表示されYarnで起動するコマンドが促されます。

```shell
# Yarnがローカルに存在
$ which yarn
/opt/homebrew/bin/yarn

# Create React Appでアプリを作成
$ npx create-react-app my-app

...

We suggest that you begin by typing:

  cd my-app2
  yarn start

Happy hacking!
```

Yarnがローカルにインストールされていない場合はnpmを使用するようになり、プロジェクト生成後に`npm start`で開発サーバーを立ち上げることを促されます。

```shell
# Yarnがローカルに存在しない
$ which yarn
yarn not found

# Create React Appでアプリを作成
$ npx create-react-app my-app

...

We suggest that you begin by typing:

  cd my-app
  npm start

Happy hacking!
```

Yarnがインストールされている状態で`npx`を使用して作成したReactプロジェクトではYarnの利用を想定してYarn.lockが生成されています。`npm start`でもアプリを立ち上げることは可能ですが、npmの利用を強制するところまでは至りません。

そこでnpmを使用してのパッケージ管理を強制したいときにできることをまとめて紹介します。

# オプションでnpmを強制させる

Create react Appにはパッケージマネージャをnpmに固定するオプションがあります。

```shell
$ npx create-react-app my-app --use-npm
```

上のように`--use-npm`というオプションを付けることでYarnがインストールされている状態でもnpmをデフォルトで使用するようにできます。

```shell
# Yarnがローカルに存在
$ which yarn
/opt/homebrew/bin/yarn

# npmを強制するオプションをつけて作成
$ npx create-react-app my-app --use-npm

...

We suggest that you begin by typing:

  cd my-app
  npm start

Happy hacking!

```

Yarnがインストールされている環境でもnpmを使用するように設定できました。`--use-npm`をつけて作成した場合、yarn.lockではなくpackage-lock.jsonがプロジェクト配下に生成されます。
# おわりに

最後まで読んでいただきありがとうございました。