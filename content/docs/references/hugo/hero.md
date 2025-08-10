---
title: Hero short codes
type: docs
prev: 
next: 
sidebar:
  open: true
---

# Hero系ショートコード一覧

## 1. `hextra/hero-badge`

- 役割：ヒーローの最上部に置く小さなバッジ（ラベル）。中身はスロット（自由なHTML/ショートコード）で記述。
    
- 使い方：
```
{{</* hextra/hero-badge */>}} 

...（ `<span>` タグや `{{/*< icon … */>}}` を入れる 

{{</* /hextra/hero-badge */>}}
```

 
- 備考：バッジ内にHTMLや別ショートコードを混ぜるとレンダリングが崩れる事例あり（Markdown/HTML混在が原因）。 [GitHub](https://github.com/imfing/hextra/discussions/424?utm_source=chatgpt.com)
    
- パラメータ：**（明示パラメータの公式記載なし）**。コンテンツをそのまま入れる前提。  
    ※2024-12 のリリースで「badge にアイコン対応」が言及（内部対応）。 [GitHub](https://github.com/imfing/hextra/releases)


## 2. `hextra/hero-headline`

- 役割：ヒーローの大見出し（H1 相当の強い見出し）。
    
- 使い方：
```
{{</* hextra/hero-headline */>}}
テキスト
{{</* /hextra/hero-headline */>}}

```
-　行の途中に `<br class="…">` を挟む実例あり。 [GitHub](https://github.com/imfing/hextra/discussions/411?utm_source=chatgpt.com)[Myco | Git](https://fung.uy/mycosystems/midtowndrafting.com/commit/70fbf819c7519ac80522a28999da125ebb996f3d?show-outdated=&style=unified&whitespace=show-all&utm_source=chatgpt.com)
    
- パラメータ：**なし（中身スロットのみ）**（確認できた範囲）。


## 3. `hextra/hero-subtitle`

- 役割：ヒーローのサブタイトル。
    
- 使い方：
```
{{</* hextra/hero-subtitle */>}}

テキスト

{{</* /hextra/hero-subtitle */>}}
```
実利用例多数。 
[Gitea: Git with a cup of tea+1Gitea: Git with a cup of tea+1](https://git.nicolabelluti.me/little-emulator/docs/src/commit/f9cf2928ed92e80a4f3ea42af83beb666f096d74/content/_index.md?utm_source=chatgpt.com)
    
- パラメータ：**なし（中身スロットのみ）**（確認できた範囲）。


## 4. `hextra/hero-button`

- 役割：ヒーロー内の主要CTAボタン。
    
- 使い方：
```
{{</* hextra/hero-button text="Get Started" link="docs" */>}}
```

- パラメータ（確認済み）：
    
    - `text`：ボタン表示文字列
        
    - `link`：リンク先パス/URL
    
- 注意：**テーマ作者いわく「ランディング専用の内部コンポーネントなので、むやみに流用しない方がよい」**とのコメントあり。必要なら自作（Tailwind）推奨。 [GitHub](https://github.com/imfing/hextra/discussions/424?utm_source=chatgpt.com)


## 5. `hextra/hero-section`

- 役割：ヒーロー領域の**セクション見出し**を作るユーティリティ（`h2` デフォルト）。
    
- 使い方：
    
    ```
    {{</* hextra/hero-section */>}}
    Used **Technologies　（デフォルトは h2 サイズの見出し）
    {{</* /hextra/hero-section */>}}
        
    {{</* hextra/hero-section header="h3" */>}}
    Used Technologies （（h3 などに変更））
    {{</* /hextra/hero-section */>}} 
    ```
    
    
- パラメータ（確認済み）：
    
    - `header`：`h2`/`h3`/`h4`… を指定（デフォルト `h2`） [GitHub](https://github.com/imfing/hextra/pull/390)
        
    - `style`：インラインCSSを渡せる（`style="{{ . | safeCSS }}"` の実装あり） [GitHub](https://github.com/imfing/hextra/issues/388?utm_source=chatgpt.com)


## 6. `hextra/feature-grid`（ヒーロー直下で並ぶカードの枠）

- 役割：フィーチャーカードのグリッドコンテナ。
    
- 使い方：
```
{{</* hextra/feature-grid */>}}

…（feature-card を並べる）… 
  
{{</* /hextra/feature-grid */>}}. 

```
実例多数。 [GitHub](https://github.com/imfing/hextra/discussions/411?utm_source=chatgpt.com)
    
- パラメータ：**なし**（確認できた範囲）。
    

## 7. `hextra/feature-card`（グリッド内のカード）

- 役割：画像付きフィーチャーカード。先述の`hextra/feature-grid`のショートコード内で使うことでカードの並びを自動で整理してくれる。
```

{{</* hextra/feature-card
    title="Love For Qom"
    subtitle="Cypherpunks write code"
    class="hx-aspect-auto md:hx-aspect-[1.1/1] max-md:hx-min-h-[340px]"
    image="images/sample4.jpg"
    imageClass="hx-top-[80%] hx-[24px] hx-w-[110%] sm:hx-w-[110%] dark:hx-opacity-80"
    style="background: radial-gradient(ellipse at 50% 80%,rgba(255,0,255,0.3),hsla(0,0%,100%,0));"
  */>}}
  
```
    
- よく使われるパラメータ（実利用から確認）：
    
    - `title`：カードのタイトル
        
    - `subtitle`：サブタイトル

    - `link` :ファイルパス（相対パス）/URL
        
    - `class`：カード全体に当てるクラス
        
    - `image`：画像パス/URL
        
    - `imageClass`：画像要素に当てるクラス
        
    - `style`：インラインCSS（背景グラデ等）  
        実使用コードはテーマのQ&Aに多数掲載。 [GitHub](https://github.com/imfing/hextra/discussions/411?utm_source=chatgpt.com)  
        （※完全な仕様はショートコードの実装を読む必要がありますが、上記はドキュメント/議論での反復使用が確認できるもの）
        

---

## 使い方の実務ヒント

- **HTMLでラップしない**：Hero系を`<div>`で囲んでマージンを付けると、Markdown/Goldmarkの解釈順の都合で**ショートコードが展開されなくなる**ことがあるので注意。余白は**周辺に別ブロック**を置くか、`hero-section` など**ショートコード側**で調整するのが安定です。 [GitHub](https://github.com/imfing/hextra/discussions/424?utm_source=chatgpt.com)
    
- **`hero-button`の過信に注意**：作者が「内部用なので流用は非推奨」と明言。ページ内のCTAは Tailwind で自作するか、既存の `cards` 系で代替するのが無難。 [GitHub](https://github.com/imfing/hextra/discussions/424?utm_source=chatgpt.com)
    
- **`hero-section`を積極活用**：ヒーロー直下のセクション見出しを追加したいニーズに対して、**公式にマージ済みの解**。`header` と `style` を持つので、`feature-grid` の前に見出しを置くなどがやりやすいです。