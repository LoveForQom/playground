---
title: Step 3
type: docs
prev: create_card
next: _index
sidebar:
  open: false
---
（下書き）

## PR を作成（feature → dev）
{{% steps %}}

### GitHub 上で ** `dev`ブランチに プルリクエスト（PR） 作成

### レビューを受け、修正があれば修正を行う　=> 問題なければマージ

### ブランチを削除する

{{% /steps %}}

## プルリクエストの作成

- GitHub 上で **base: `dev`** / **compare: `feature/<username>`** を選んで PR 作成
    
- PR の説明欄に：
    
    - 変更点の概要
        
    - スクショ or ローカルプレビュー確認事項
        
    - 自分のページへのリンク
        
- **PRを作成したら Telegram で管理者に連絡**
    


##  レビュー → 修正 → マージの流れ

- レビューコメントが来たら、**同じブランチに修正コミット**してプッシュすれば PR に自動で反映されます。
    
- `dev` の更新を取り込みたい場合：


```bash
git fetch origin 
git checkout feature/<username>

# どちらでもOK（チーム標準に合わせる） 
git merge origin/dev 
# または 
git rebase origin/dev git push
```


- 問題なければ管理者が `dev` にマージし、適切なタイミングで `main` に反映します（基本は管理者作業）。


## 完了後ブランチを削除

- マージ後は GitHub 上の **「Delete branch」** ボタンで `feature/<username>` を削除
    
- ローカルでも削除してスッキリ：


```bash
git branch -d feature/<username> 

git fetch -p
```



