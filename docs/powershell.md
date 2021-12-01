# PowerShell

!!! warning "2021年9月の情報です。"

## 概要

Windows PowerShellとWindows Terminalの両方で以下のことをする。

- Powerlineをセットアップ
- Draculaテーマを適用

## Powerlineをセットアップ

### Posh-GitとOh-My-Poshをインストール

```powershell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

### プロファイルを編集

`~\Documents\PowerShell\Microsoft.PowerShell_profile.ps1`に以下のスクリプトを追加する。
使用できるテーマは`Get-PoshThemes`から確認可能。

=== "Microsoft.PowerShell_profile.ps1"

    ```powershell
    Import-Module posh-git
    Import-Module oh-my-posh
    Set-PoshPrompt -Theme Paradox
    ```

### フォント

Powerlineに対応したフォントをインストールする。フォントは1種類しか指定できないため、和文も含まれている方が望ましい。
[HackGen Console](https://github.com/yuru7/HackGen)が良さそう。

## Draculaテーマを適用

Draculaがベストかはわからないが、他に良いものを探すのがめんどくさいので。

### Windows Terminal

Windows Terminalの設定からjsonファイルを開き、[公式の説明](https://draculatheme.com/windows-terminal)にあるスクリプトを追加する。
ついでにフォントをHackGen Consoleにしておく。

### Windows PowerShell

[公式の説明](https://draculatheme.com/powershell)通りにやる。
プロファイルはGitPromptSettingsの部分は省いてもよさそう。

## サジェストを有効にする

サジェストはPSReabLine 2.1から使用できる。必要であればv2.1以上にアップデートする。

```powershell
(Get-Module PSReadLine).Version
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

プロファイルに以下を記載することで有効になる。

=== "Microsoft.PowerShell_profile.ps1"

    ```powershell
    Set-PSReadLineOption -PredictionSource History
    ```

## 参照

- [Windows ターミナルのカスタム プロンプトのセットアップ \_ Microsoft Docs](https://docs.microsoft.com/ja-jp/windows/terminal/tutorials/powerline-setup)
- [Windows \_ Oh My Posh](https://ohmyposh.dev/docs/windows)
- [\[PowerShell\] Oh my Posh (Powerline) を使ってPowerShellコンソールをおしゃれにカスタマイズする \_ DevelopersIO](https://dev.classmethod.jp/articles/customize-your-powershell-console-with-oh-my-posh3/)
- [Windows TerminalでPowerlineの環境を整える - ビー鉄のブログ](https://www.beeete2.com/blog/?p=2619)
- [\[PowerShell\] PSReadLine 2.1がリリースされました \_ DevelopersIO](https://dev.classmethod.jp/articles/powershell-psreadline-21-released/)
- [PSReadLine について - PowerShell \_ Microsoft Docs](https://docs.microsoft.com/ja-jp/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1)
