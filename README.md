## Gitflow Hands-on Playground


Playgroundはチーム全員が **Gitflow** メソッドを体験しながら、Hugo + Hextra のサイト編集を学ぶための**実践用リポジトリ**です。学びたい意欲のある方は、どなたでもご参加いただけます。


#### 目的：
Qom Wikiと同様の構成を再現した環境で、本ページの説明を見ながら実際に自分自身で作ってみることでページの構成要素や各パラメータの扱いなど、基本的な操作を理解し、共に飛行訓練に参加するための準備をここで行うことを目的とします。

#### 対象：
-　Qom Wikiの編集に参加してみたいが具体的な方法・手段を知りたい方

-　Gitの扱いに自信がなく、一度説明を見ながら体験をしてみたい方

#### 期待される成果：
- Obsidianを利用したmd ファイルの効率的な編集とレイアウト調整

- Hextraテンプレートを使用した実用的なHugoサイトビルド技術

- GitFlowに則ったチーム共同開発の基本フローの体験

- GitコマンドによるGitHubリポジトリの操作

## 0. 前提

- Git 使用法と GitHub アカウントを登録済み

- （推奨）SSH 接続設定済み（または HTTPS で OK）

- リポジトリのコラボレーターの招待を了承している（要連絡：TG:@LoveForQom88）

- ローカルで [Hugo](https://gohugo.io/getting-started/quick-start/) が動く（`hugo version` が通ればOK / Extended推奨）

- [Git Flow](/docs/references/git/gitflow)の手順に沿って作業を進めていくことを理解している

> [!important]
> まだ上記の準備がお済みでない場合は、まず[こちら](https://qom.wiki/docs/creators/gitguide/)を参考に必要な準備をお済ませください。



## 参加ルール

- ブランチ名：`feature/<username>` を作成して下さい
    
- コミットメッセージ：目的が伝わること（`feat:`, `fix:`, `docs:` 等は推奨）
    
- PR の向き先は **必ず `dev`**（`main` 直は不可）
    
- PR 作成後は **Telegram で声かけ**
    
- レビュワーが「OK」なら `dev` → `main` の反映は管理者が実施
    