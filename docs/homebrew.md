# Homebrew

!!! warning "2021年12月の情報です。"

## CommandLineTools for Xcodeのインストール

### ディベロッパーディレクトリの変更

```zsh
$ xcode-select -p
/Library/Developer/CommandLineTools
```

とならない場合は変更する。

```zsh
$ xcode-select -p
/Applications/Xcode.app/Contents/Developer
$ sudo xcode-select -s /Library/Developer/CommandLineTools
$ xcode-select -p
/Library/Developer/CommandLineTools
```

### インストール

```zsh
xcode-select --install
```

### 確認

```zsh
pkgutil --pkg-info=com.apple.pkg.CLTools_Executables | grep version
```

バージョンが表示されない場合はインストールがうまくいっていないので、一旦削除する。

```zsh
sudo rm -r /Library/Developer/CommandLineTools
```

そして[Appleのデベロッパーサイト](https://developer.apple.com/download/more/)からダウンロードする。

## Homebrewのインストール

[公式ページ](https://brew.sh/index_ja)のコマンドを実行

## 絶対に使うパッケージたち

<!-- インストールスクリプトほしい -->

### formula

- zsh
- git

### cask

- iterm

## 参照

- [Homebrewのインストール方法について詳細に解説する - Qiita](https://qiita.com/DaikiSuyama/items/5a2a96859b44595cba76)
