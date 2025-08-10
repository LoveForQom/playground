---
title: Classes
type: docs
prev: 
next: 
sidebar:
  open: true
---
このページでは、クラスを使用してマージンやパディング、フォントのサイズや色、要素のレイアウトを指定する方法を説明します。クラスを使用してcssを適応できるため、別ファイルを作成する必要が減るため便利です。

## 1. マージン（余白）の指定方法（Hextra/Tailwind prefix付き）


```html {filename="content/_index.md"}

<div class="hx-mt-6 hx-mb-6">
    
    Teh Playground
    
</div>

- <div>で囲まれた要素に対して上下方向に 1.5rem|24px|のマージン（空白）を入れる。
マージンとは、要素の外側の余白のことです。

```

|クラス|意味|ピクセル換算(基準: 1 = 0.25rem = 4px)|
|---|---|---|
|`hx-m-0`|全方向マージン 0|0px|
|`hx-m-4`|全方向マージン 1rem|16px|
|`hx-mb-2`|下方向だけ 0.5rem|8px|
|`hx-mt-8`|上方向だけ 2rem|32px|
|`hx-ml-6`|左方向だけ 1.5rem|24px|
|`hx-mx-4`|左右だけ 1rem|16px|
|`hx-my-10`|上下だけ 2.5rem|40px|

## 2. 主な方向指定の略語

|接頭辞|対象方向|
|---|---|
|`m`|全方向|
|`mt`|上だけ (margin-top)|
|`mb`|下だけ (margin-bottom)|
|`ml`|左だけ (margin-left)|
|`mr`|右だけ (margin-right)|
|`mx`|左右両方|
|`my`|上下両方|


## 3. 数値スケール

Tailwind のスケールは `0`～`96` のほか `px`（1px）、`auto` などがあり、  
`n` の値は **n × 0.25rem** に変換されます。

例：

- `hx-mb-1` → 0.25rem (4px)
    
- `hx-mb-6` → 1.5rem (24px)
    
- `hx-mb-10` → 2.5rem (40px)


## 4. 応用（レスポンシブ対応）

Tailwind はレスポンシブ指定も可能で、Hextraのprefix付きでも同じ書き方です。

```html
<div class="hx-mb-4 md:hx-mb-8 lg:hx-mb-12">   ... </div>

- md: → 画面幅 768px 以上なら下に32pxマージンをとる
    
- lg: → 画面幅 1024px 以上なら下に48pxマージンをとる
    
```

## 5.　その他のユーティリティ


- ### ① パディング（Padding）

|クラス例|効果|ピクセル換算|
|---|---|---|
|`hx-p-0`|全方向 0|0px|
|`hx-p-2`|全方向 0.5rem|8px|
|`hx-p-4`|全方向 1rem|16px|
|`hx-p-6`|全方向 1.5rem|24px|
|`hx-pt-4`|上だけ 1rem|16px|
|`hx-pb-8`|下だけ 2rem|32px|
|`hx-pl-2`|左だけ 0.5rem|8px|
|`hx-pr-2`|右だけ 0.5rem|8px|
|`hx-px-4`|左右 1rem|16px|
|`hx-py-4`|上下 1rem|16px|

- ### ② フォントサイズ（Font Size）

|クラス|サイズ|px換算（目安）|
|---|---|---|
|`hx-text-xs`|0.75rem|12px|
|`hx-text-sm`|0.875rem|14px|
|`hx-text-base`|1rem|16px|
|`hx-text-lg`|1.125rem|18px|
|`hx-text-xl`|1.25rem|20px|
|`hx-text-2xl`|1.5rem|24px|
|`hx-text-3xl`|1.875rem|30px|
|`hx-text-4xl`|2.25rem|36px|


- ### ③ フォントウェイト（Font Weight）

|クラス|効果|
|---|---|
|`hx-font-thin`|極細 (100)|
|`hx-font-light`|細め (300)|
|`hx-font-normal`|標準 (400)|
|`hx-font-medium`|中間 (500)|
|`hx-font-semibold`|やや太め (600)|
|`hx-font-bold`|太字 (700)|
|`hx-font-extrabold`|極太 (800)|


- ### ④ 色（テキスト色・背景色）

|テキスト色例|背景色例|
|---|---|
|`hx-text-red-500`|`hx-bg-red-500`|
|`hx-text-blue-500`|`hx-bg-blue-500`|
|`hx-text-gray-700`|`hx-bg-gray-200`|
|`hx-text-green-600`|`hx-bg-green-100`|

> 色は Tailwind のカラーパレットに準拠（`50`〜`900` まで濃淡あり）


- ### 5. レイアウト・その他

|クラス|効果|
|---|---|
|`hx-flex`|flexbox 有効化|
|`hx-items-center`|縦方向中央揃え|
|`hx-justify-center`|横方向中央揃え|
|`hx-grid`|grid 有効化|
|`hx-grid-cols-3`|3カラムレイアウト(中身の要素を3列で表示)|
|`hx-gap-4`|要素間の間隔 1rem (16px) に指定|
|`hx-rounded`|要素の角を丸くする（デフォルト半径）|
|`hx-rounded-lg`|大きめの角丸|
|`hx-shadow`|要素にシャドウを入れる|
|`hx-shadow-lg`|大きめシャドウ|


💡 **覚え方のコツ**

- `hx-` を外せば Tailwind CSS の公式ドキュメントの例そのまま
    
- 数字は 4px単位（0.25rem）で増える
    
- `m` と `p` 系は上下左右の頭文字で方向指定 (`t`, `b`, `l`, `r`, `x`, `y`)

## 6. 参考リンク（元はTailwindドキュメント）

Hextraでは `hx-` が付くだけで、[Tailwind CSS Margin](https://tailwindcss.com/docs/margin) のすべてがそのまま使えます。