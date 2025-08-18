---
title: Step 3
type: docs
prev: create_card
next: _index
sidebar:
  open: false
---

## 🎤プルリクエスト(PR) を作成する（devブランチに向けて）
{{% steps %}}

### GitHub 上で ** `dev`ブランチにPR作成

### レビューを受け、修正があれば修正を行う => 問題なければマージ

### ブランチを削除する

{{% /steps %}}

今回は最終回となるプルリクエストの送信と、修正があった場合の対応の流れを確認していきます。それでは早速始めていきましょう。
## 1. PRの作成

- GitHub 上で **base: `dev`** / **compare: `feature/<username>`** を選んで PR 作成
    
- PR の説明欄に：変更点の概要を記載  -> "submit"ボタン   
        
- **PRを作成したら Telegram で管理者に連絡**
    
![Pullrequeat](/images/pullrequest.JPG)

## 2. レビュー → 修正 → マージの流れ

レビューで問題がなければ、そのままマージされます。レビューコメントで修正依頼が来たら、**同じブランチに修正コミット**してプッシュすれば PR に自動で反映されます。

```bash
# これまでと同じように編集
git add .

# コメントは意味のあるコメントに
git commit -m "修正内容をコメント"

# 初回で　`-u`オプションをつけた場合はpushのみで変更をリモートにプッシュできます。
git push

```
    
- 修正中に`dev` に変更があった場合は、変更をプッシュできなくなることがあります。以下の手順でリモートの`dev`の変更を取り込んでから再度プッシュして下さい：

```bash
# モートリポジトリの `dev` ブランチの最新状態を取得
git fetch origin dev

# <username>の部分は自分の命名したユーザー名に置き換え
git checkout feature/<username>

# ローカルのdevブランチに最新版のdevをマージ
git merge origin/dev

# `fetch` + `merge` を一度にやりたい場合はこちらでも可
git pull --no-rebase origin dev 

```


- 問題なければ管理者が `dev` にマージし、適切なタイミングで `main` に反映します（基本は管理者作業）。


## 完了後ブランチを削除

- マージ後は GitHub 上の **「Delete branch」** ボタンで `feature/<username>` を削除
    
- ローカルでも削除してスッキリ：


```bash
git branch -d feature/<username> 

git fetch -p
```

お疲れ様でした！！🙌
プルリクエストが承認され、`main`ブランチに変更がマージされたらトップページにあなたの変更が反映されます。
この練習が終了したら、次は実際にQom Wikiの編集に参加してみましょう。