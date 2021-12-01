# Node.js

!!! warning "2021年12月の情報です。"

## 前提

- [Homebrew](../homebrew/)
- [asdf](../python/)

## 事前準備

必要なパッケージについては[公式ページ](https://github.com/asdf-vm/asdf-nodejs)に記載がある。

```zsh
brew install gpg gawk
```

## asdfでNode.jsをインストール

```zsh
asdf plugin add nodejs
asdf install nodejs latest

asdf global nodejs [version]
```
