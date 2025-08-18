---
title: Step 2
type: docs
prev: edit_md
next: pull_request
sidebar:
  open: false
---

## 🪪トップページに自分のカードを追加する

![feature card](/images/feature_card.JPG)
{{% steps %}}

### `content/_index.md`を編集し、カードセクションを追加する

### クラスにスタイルを追加して調整する

### カードにリンクを追加して`Step 1`で作成したファイルとリンクさせる

### 変更をコミット＆プッシュする

{{% /steps %}}


今回は、ホーム画面に画像付きのカードを作成し、**Step1**で作成した自己紹介のmdファイルとリンクさせます。具体的な見た目の調整や値の調整の作業が中心になります。細かい調整の方法を体験していきましょう！

## 1. カードセクションの追加

ファイル: **`content/_index.md`**

![Codes](/images/codes.JPG)


対象ファイルのコードを確認すると、今回はmdファイルの中に **`<div>タグ`** などのHTMLタグと **`{{</* hextra/hero-section */>}}`** のようなショートコードが使われていることがわかります。
今回対象となるカードセクションは、まず`{{</* hextra/feature-grid */>}} ... {{</* /hextra/feature-grid */>}}`というカードが格納されるコンテナのようなセクションがあり、その中に自分のカードのショートコード `{{</* card */>}}`　が複数のプロパティ付きで装飾されています。このショートコードを適切な位置に追加してみましょう。

```md
# カードを囲むグリッドのセクションのためのショートコード

{{</* hextra/feature-grid */>}}

# カードのショートコード（各種パラメータを設定）

{{</* card 
title="your user name"
subtitle="something blur blur blur"
.
.
.
*/>}}

.
.
.


# グリッドのセクションのショートコードはここまで
{{</* hextra/feature-grid */>}}
```

自分用の`{{</* card */>}}`ショートコードを追加し、以下を参考にカスタマイズしてみましょう。また、カードに使用したい画像は`content/images`フォルダに追加して下さい。

###  📟 各パラメータの意味

#### feature-cardの主要属性

| 属性名          | 役割                                     | 例                                                             |
| ------------ | -------------------------------------- | ------------------------------------------------------------- |
| `title`      | カードの見出し                                | `"Love For Qom"`                                              |
| `subtitle`   | 補足説明（見出しの下）                            | `"What this place is and why we're here."`                    |
| `link`       | リンクのパスを指定                              | `内部リンク・外部リンク可`                                                |
| `class`      | カードの外枠に適用するTailwindクラス（Hextraは`hx-`付き） | `hx-aspect-auto md:hx-aspect-[1.1/1] max-md:hx-min-h-[340px]` |
| `image`      | カード背景や上部に表示する画像パス                      | `"images/sample1.jpg"`                                        |
| `imageClass` | 画像要素に適用するクラス                           | `hx-absolute hx-max-w-[100%] ...`                             |
| `style`      | インラインCSSスタイルを直接指定                      | `background: radial-gradient(...)`                            |


####  クラス指定の意味（今回の例）

```
class="hx-aspect-auto md:hx-aspect-[1.1/1] max-md:hx-min-h-[340px]"
```

- `hx-aspect-auto` → 縦横比を自動設定
    
- `md:hx-aspect-[1.1/1]` → 中画面サイズ以上では縦横比 1.1:1
    
- `max-md:hx-min-h-[340px]` → 中画面未満では高さ最小 340px



```
imageClass="hx-top-[40%] hx-[24px] hx-w-[110%] sm:hx-w-[110%] dark:hx-opacity-80"
```

- `hx-top-[40%]` → 画像の位置（上から40%）
    
- `hx-[24px]` → 特殊クラス（おそらく位置か余白のカスタム値、テーマのTailwind設定依存）
    
- `hx-w-[110%]` → 幅110%
    
- `sm:hx-w-[110%]` → 小画面以上では幅110%
    
- `dark:hx-opacity-80` → ダークモード時に透明度80%
    

---

### 背景スタイルの意味


```
style="background: radial-gradient(ellipse at 50% 80%,rgba(200,80,0,0.3),hsla(0,0%,100%,0));"
```

- **背景にラジアルグラデーション**を適用
    
- 中心を少し下（50% 横方向中央、80% 縦方向）に設定
    
- 中心付近は橙系の薄い色`(200,80,0,0.3)`、外側は透明

> 参考：Hextra の **Card** ショートコード（使用例・パラメータ） [IDocument](https://imfing.github.io/hextra/docs/guide/shortcodes/cards/)
> [tailwindcss](https://tailwindcss.com/docs/installation/using-vite)

## 2. カードにリンクを追加する

カードに値を追加できたら`Step 1`で作成した記事とリンクさせるために`link`プロパティを追加し、適切な相対パスを使用してカードと記事とをリンクさせて下さい。相対パスをどのように記述するかは自分で考えてみましょう。（わからなければ実際のコードを見て下さい。）

## 3. 変更をコミット＆プッシュ

`link`のパスが記述できたらローカルサーバー：1313を起動し、ブラウザからアクセスして下さい。ホーム画面から画像をクリックして、意図した画面（自分の紹介ページ）に画面が遷移するか確認しましょう。
確認ができたら自分のブランチに変更をコミット＆プッシュしておきましょう。次はいよいよプルリクエストの作成です。