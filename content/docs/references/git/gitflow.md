---
title: GitFlow
type: docs
prev: 
next: 
sidebar:
  open: true
---

**GitFlow（ギットフロー）**　とは、**Gitを使ったチーム開発でのブランチ戦略（運用ルール）** の1つで、**Vincent Driessen**によって提案された開発フローです。複数人での開発や、リリース管理を効率的に行うためのベストプラクティスとして広く使われています。

---

### 🔧 GitFlowの基本的なブランチ構成

GitFlowでは、以下のようなブランチを使い分けます：
 Playgroundでは、まず操作に慣れてもらうためにmainブランチ、devブランチ、feature/＊ブランチの3つのブランチを使用して実際の流れを体験してもらいます。

| ブランチ名                | 用途                                                                    |
| -------------------- | --------------------------------------------------------------------- |
| `main`（または `master`） | 本番環境のコード。常に安定している状態が求められる。                                            |
| `dev`                | 開発の中心となるブランチ。機能追加や修正はここをベースに行う。                                       |
| `feature/*`          | 機能開発用のブランチ。`develop`から派生し、開発完了後は`develop`にマージ。                        |
| `release/*`          | リリース準備用ブランチ。`develop`から派生し、バグ修正やバージョン番号の更新などを行い、`main`と`develop`にマージ。 |
| `hotfix/*`           | 緊急修正用ブランチ。`main`から派生し、修正後に`main`と`develop`にマージ。                       |

### 🔁 ブランチの構成イメージ

```text
main  
 ├── dev      
 |  ├── feature/add-login
 |	├── feature/add-payment
 |	└── release/1.0.0
 └── hotfix/fix-critical-bug
```




### 📝 開発フローの概要

1. **新機能の開発**  
    → `dev` ブランチから `feature/*` を作成して作業。終わったら `develop` にマージ。
    
2. **リリース準備**  
    → `develop` ブランチから `release/*` を作成して、調整・テストを行い `main` と `develop` にマージ。
    
3. **本番でバグ発見！**  
    → `main` から `hotfix/*` を作って修正、修正後に `main` と `develop` にマージ。




### 🤝 GitFlowのメリット

- 機能追加・リリース・修正などの作業が明確に分離され、**作業の混乱を避けやすい**
    
- チームでの**並列開発**がやりやすい
    
- 安定した本番コード（main）と開発コード（dev）の分離




## ✅ 開発ブランチ（featureブランチ）の作成手順

### 🔧 前提

- すでにローカルにリポジトリをクローン済み
    
- `dev` ブランチが存在している

### ⬇️ 手順（ターミナル / Git Bash）

```bash
# 1. devブランチに切り替える 
git checkout dev  

# 2. 最新のdevelopブランチを取得しておく（他の人が更新している場合もあるため）
git pull origin dev  

# 3. featureブランチを作成（名前は自由に設定。例：feature/love） 
git checkout -b feature/love  

# 4. 作業後、GitHubにプッシュ（初回は -u オプションでトラッキングも設定） 
git push -u origin feature/login-form

# 5. 2回目以降のプッシュ
git push
```

- `-b` オプションは「新しいブランチを作って同時に切り替える」という意味です。
    
- `-u` オプションは「このローカルブランチとGitHub上のリモートブランチを紐づける」ために使います。`-u`オプションで紐づけられたら、以降は`git push`のみでリポジトリにプッシュすることが可能になります。

---

### 💡 ブランチ名の命名ルール（推奨）

GitFlowでは以下のような形式がよく使われます：

- `feature/`：機能追加
    
    - 例：`feature/signup-page`、`feature/add-payment`
        
- `bugfix/`：開発中の不具合修正
    
- `hotfix/`：本番環境の緊急修正



