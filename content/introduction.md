---
title: Introduction
type: docs

---

## Gitflow Hands-on Playground


![hands on](/images/hands_on.JPG)
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

- [Git Flow](../docs/references/git/gitflow)の手順に沿って作業を進めていくことを理解している

> [!important]
> まだ上記の準備がお済みでない場合は、まず[こちら](https://qom.wiki/docs/creators/gitguide/)を参考に必要な準備をお済ませください。



## 1. リポジトリの取得と初期設定

```bash
# 1. クローン（SSH の例） 
git clone git@github.com:LoveForQom/playground.git
cd playground  

# 2. 最新の dev ブランチのコードを取得 
git fetch origin 
git checkout dev 
git pull origin dev

# 3. 自分用の作業ブランチを作成してブランチの切り替え（例: feature/pomworld） 
git checkout -b feature/pomworld
```

> [!caution]
> 以降の作業は **必ず自分の `feature/<username>` ブランチ** で行ってください。


## 2. ローカルプレビュー（Hugo）


```bash
# ターミナルでローカルサーバーを起動 
hugo server --buildDrafts --disableFastRender
```

- ブラウザで `http://localhost:1313/` を開くとプレビューできます。
    
- このリポジトリは **Hugo の Hextra テンプレート**のクイックスタート構成を使用しています。
 [IMFing](https://imfing.github.io/hextra/docs/getting-started/?utm_source=chatgpt.com),[GitHub](https://github.com/imfing/hextra-starter-template?utm_source=chatgpt.com)



<div class="hx-mt-6 hx-mb-6 hx-text-right">
{{< hextra/hero-button text="Next >>" link="../docs/steps/edit_md" >}}
</div>

