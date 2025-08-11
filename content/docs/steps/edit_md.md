---
title: Step 1
type: docs
prev: /_index
next: create_card
sidebar:
  open: false
---

## Obsidianを使ってmdファイルで自分のメンバーページを作る


{{% steps %}}

### 自分の名前の`.md`ファイルを`content/docs/members`ディレクトリに作成

### Obsidianでファイルを編集

### 変更をコミット＆プッシュする

{{% /steps %}}

最初のステップとなる今回は、まず正しいディレクトリに自分のファイルを作成し、Obsidianを使ってファイルを編集する方法を学びます。まずはとにかく手を動かしてみましょう。

### 1.　自分の名前の`<username>.md`ファイルを`content/docs/members`ディレクトリに作成
まずはcd コマンドで目的のディレクトリに移動し、`<username>.md`ファイルを作成していきます。
現在の場所はプロジェクトのルートディレクトリ（playground）にあると仮定します。
ターミナルから以下のコマンドを使用して移動して下さい。VSコードを使用している場合は画像のように画面を分割してターミナルを表示させておくと便利です。

![terminal](/images/terminal.JPG)

```bash
# membersディレクトリに移動
cd content/docs/members

# <username>.mdファイルを作成（⚠️小文字の使用推奨）

## macターミナル
touch love.md

## windows powershell
New-Item love.md

```

## 2. Obsidianで`<username>.md`ファイルを編集する。
![Obsidian](/images/obsidian.JPG)
Obsidianを使うとマークダウンファイルの編集作業効率が非常に上がるのでおすすめです。先ほど作成したファイルをObsidianで開いてみましょう。
まずはObsidianのホーム画面の **「保管庫としてフォルダを開く」** から、`menbers`フォルダを選択します。先ほど作成した`<username>.md`ファイルを自由に編集してみて下さい。マークダウン記法を使うと、記述した内容が実際にサイトで表示されるようにレンダリングされていることがわかると思います。見た目の調整はObsidianで編集することで大まかな部分を整えつつ、細かい部分はローカルホストで立ち上げたブラウザを確認しながら進めることをお勧めします。

```md {filename="members/<username>.md"}
# フロントマターを先頭に記述
---
title: <username> 
type: docs 
sidebar:   
　open: true 
---  

# 見出し
# ~ ###### (h1 ~ h6)までの見出しの文字の大きさを指定できます。

画像を差し込みたい場合は、`content/images`フォルダに画像を格納。
![テキスト](ファイルパス)という記述で差し込むことができます。
`images`フォルダにある`love.jpg`を差し込みたい場合は、以下のように記述します。(相対パスに注意)

![Love For Qom](/images/love.jpg)

ショートコードを使うことでhextraに定義された特殊なレンダリングを使うこともできます。

例：
{{</* step */>}}

///

{{</* /step */>}}

その他自己紹介やスキル、プロジェクトへの意気込みなどを、マークダウン記法を使いながら自由に書いてください。

- Twitter: … 
- Telegram: … 
- Link: …
```

> [!tip]
> テーマの詳細な設定や、ショートコード一覧は Hextra ドキュメントを参照してください。 [Document](https://imfing.github.io/hextra/docs/guide/configuration/?utm_source=chatgpt.com)



## 3.  変更のコミットとプッシュ

```bash
# 変更をステージに上げる
git add .  

# 意味のあるコミットメッセージで 
git commit -m "add <username> profile page"  

# 初回は upstream 設定込みでプッシュ 
git push -u origin feature/<username>
```
- `<username>`の部分は自分のネームに置き換えて下さい。
> [!important]
> push の際は必ずどのブランチにプッシュしようとしているかを確認して下さい。
> 初回は`git push` に`-u` オプションをつけておくことで、2回目以降は`git push` だけでプッシュできます。

## トラブルシューティング（よくある）

- **Permission denied (publickey)**  
    → GitHub に SSH 公開鍵を登録するか、HTTPS の URL でクローン/プッシュしてください。
    
- **`dev` が進んでいてコンフリクト**  
    →  `origin/dev` を取り込み、コンフリクト解消後に再コミット & プッシュ。