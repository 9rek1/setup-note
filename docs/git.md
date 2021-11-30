# Git & GitHub の設定

## git config --global

```zsh
git config --global user.name "your_name"
git config --global user.email "your_email@example.com"
git config --global init.defaultbranch main
```

## GitHubとSSH

### SSHキーを作成

```zsh
cd ~/.ssh
ssh-keygen -t ed25519 -C "your_email@example.com"
```

passphraseも入力しておくとよい

### GitHubにSSHキーを登録

`~/.ssh/id_ed25519.pub`の中身をGitHubに登録する

### パスフレーズの入力を省略

以下はmacのみ

=== "~/.ssh/config"

    ```
    Host github.com
    HostName github.com
    IdentityFile ~/.ssh/id_ed25519
    User git
    UseKeychain yes
    AddKeysToAgent yes
    ```

<!-- セットアップスクリプトを用意したい -->

## 参照

[【2021年8月13日まで】Githubでssh認証に切り替える方法](https://zenn.dev/dev_kenta/articles/github-ssh-change)
