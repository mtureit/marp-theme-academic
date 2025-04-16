---
marp: true
theme: academic-tml
paginate: true
math: katex
---

<!-- _class: lead -->

# Marpで研究室の発表スライドを作る

#### 〜Beamerを卒業しよう〜

<br>

**長岡　太郎**
ホゲホゲ研究室
2025年4月16日

---

<!-- _header: 目次 -->

1. はじめに
1. コードブロック
1. 数式
1. 図
1. 表
1. デザイン要素

---

<!-- _header: はじめに -->

## Marpとは

- Marpとは**Markdown**で**スライド**を作成するためのツールです
  - 基本的なMarkdownの文法がすべてサポートされています
  - <span class="marker">シンプルで効率的な研究発表資料作成が可能</span>

- Markdown上で `---` という区切り線を入れるだけで、次のページに移動できます$^1$

- <div class="bubble">GitHubでバージョン管理も簡単！</div>

> 1: Marpは CommonMarkという仕様に基づいて開発されているため、CommonMarkにない「脚注」文法（`[^1]`を使うもの）が提供されていません。そこで、https://github.com/marp-team/marp/discussions/150#discussioncomment-1302384 を参照して擬似的に脚注を実現しています。

---

<!-- _header: コードブロック -->

## プログラムコードの表示 📝

```python
import torch
print(torch.cuda.is_available())
```

このようにコードブロックを美しく表示できます。

```python
from transformers import AutoModelForMaskedLM, AutoTokenizer
model = AutoModelForMaskedLM.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")
tokenizer = AutoTokenizer.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")

inputs = tokenizer.encode_plus("私はとても[MASK]です。", return_tensors='pt')
outputs = model(**inputs)
tokenizer.convert_ids_to_tokens(outputs.logits[0][1:-1].argmax(axis=-1))
```

- <span class="marker">横幅は自動調整される</span>（[Auto-scaling](https://github.com/marp-team/marp-core#auto-scaling-features)機能）
- **Source Code Pro**フォントで可読性向上

---

<!-- _header: 数式 -->

## 数式表現の活用 ✏️

数式ブロックは以下のように記述できます：

$$ I_{xx}=\int\int_Ry^2f(x,y)\cdot{}dydx $$

$$
f(x) = \int_{-\infty}^\infty
    \hat f(\xi)\,e^{2 \pi i \xi x}
    \,d\xi
$$

- もちろんインラインの $\LaTeX$ も使えます
- <div class="bubble">KaTeXによる高速レンダリング</div>
- 絵文字も使用可能です 😄 🔬 📊 

---

<!-- _header: 図 -->

## 図の効果的な配置 📈

### 画像挿入例

![w:400 center](./images/kenkyu_woman_seikou.png)

- 中央揃えで表示: `![w:400 center](画像パス)`
- 画像サイズを指定可能: `w:幅` または `h:高さ`

---

<!-- _header: 表 -->

## 表の挿入と書式設定 📊

### 表の挿入例

| 特徴 | Marp | PowerPoint | LaTeX/Beamer |
|:-----|:----:|:----------:|:------------:|
| 学習の容易さ | ⭐⭐⭐ | ⭐⭐ | ⭐ |
| バージョン管理 | ⭐⭐⭐ | ⭐ | ⭐⭐⭐ |
| デザイン自由度 | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ |

- Markdownの表記法で簡単に作成
- 列の配置を指定可能（左寄せ、中央、右寄せ）

---

<!-- _header: デザイン要素 -->

## Marpスライドの視覚的表現

### 強調表現

- <span class="marker">マーカーによる強調</span>: `<span class="marker">テキスト</span>`
- **太字による強調**: `**テキスト**`
- <div class="bubble">吹き出しによる強調</div>: `<div class="bubble">テキスト</div>`

### カラーパレット

- 背景色: <span style="color:#F6F9F6; background-color:#333;">■</span> #F6F9F6
- 強調色: <span style="color:#0a2d92;">■</span> #0a2d92
- アクセント: <span style="color:#E60012;">■</span> #E60012

---

<!-- _class: lead -->

# ご清聴ありがとうございました

## Marpで効率的な研究発表を

<br>

**長岡　太郎**
ほげほげ研究室
