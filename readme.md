# 💎Powershellの設定忘備録

## 💎便利なモジュール

![](/image/get-module.png)

下記は入ってると嬉しい。

- [PSReadLine](https://github.com/lzybkr/PSReadLine)
- [posh-git](https://github.com/dahlbyk/posh-git)

PSReadLineはpowershellコンソールでシンタックスハイライトがつくやつ。

posh-gitはpowershellコンソールでgitを便利に使いやすく保管してくれるやつ。

ちなみにPSreadLineは2.0未満だとCJK文字が崩れる不具合があったりするので、利用するなら2.0以上がよい。

## 💎コンソールの設定

オプション  
![](/image/console.option.png)

フォント  
![](/image/console.font.png)

レイアウト  
![](/image/console.layout.png)

画面の文字  
![](/image/console.color.font.png)

画面の背景  
![](/image/console.color.background.png)

ポップアップの文字  
![](/image/console.color1.popup.font.png)

ポップアップの背景  
![](/image/console.color1.popup.background.png)

## 💎profileの設定

powershellを立ち上げ時に読み込まれるprofileファイルのパスは$profileに書いてる。

```powershell
# posh-gitのインポート
Import-Module posh-git

# コンソールでパス表示が長くなると見づらいので改行させる
$GitPromptSettings.DefaultPromptSuffix = '`n$(''>'' * ($nestedPromptLevel + 1)) '

# git logを見やすくするやつ
function gitl {
    git log --graph --branches --tags --remotes HEAD --pretty=format:"%Cgreen%ai %Cred%an %Cgreen%h %Cred%d %Creset%s"
}
```