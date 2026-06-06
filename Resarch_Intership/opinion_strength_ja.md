---
marp: true
theme: academic-tml
paginate: true
math: katex
---

<!-- _class: lead -->

# HCMUT 共同研究：言語間意見強度比較

### Cross-Lingual Opinion Strength Study — 3-Month Prep Roadmap

**松浦 瑛太**
指導教員：雲居 玄道 准教授
機械学習理論研究室（TML Lab）
長岡技術科学大学

2026 年 6 月

---

## 研究概要

### Research Overview

<div class="bubble">

**中核問い：** 同一個人が日本語・英語・ベトナム語で同じテーマについて話すとき、<span class="marker">主張の強さ（Opinion Strength）</span> と <span class="marker">論証の一貫性（Argumentative Consistency）</span> はどう変わるか？

</div>

**測定方法：**
- **Live API**（音声対話 AI、Gemini）によるアダプティブ・インタビュー
- 同一個人 × 3 言語条件で定量化

---

## なぜこの研究か

### 先行研究の 3 つのギャップ

**1. 従来手法の限界**
- 固定質問の対訳を書面提示するのみ
- 柔軟性のある質問応答が不可能

**2. ベトナム語話者の FLE 研究：文献ゼロ**
- Foreign Language Effect の越語研究は前例なし

**3. 日英越トリリンガル比較も前例なし**

<div class="bubble">

Live API なら応答に連動したフォローアップが可能 → 自然な対話から意見の強さを引き出せる。

</div>

---

## 2 つのコア指標

### Two Core Metrics

| 指標 | 定義 | 測定方法 |
|:---|:---|:---|
| **Opinion Strength**（意見強度）| 確信度・断定性・反論への応答強度 | ヘッジ語頻度・韻律特徴（eGeMAPS）・反論後の立場保持度 |
| **Argumentative Consistency**（論証一貫性）| 言語を変えても同じ立場・根拠を維持するか | 多言語埋め込み（LaBSE）コサイン類似度・立場の二値一致率 |

---

<!-- _class: compact -->

## 研究デザイン

### Study Design

**参加者：**
- 日英バイリンガル：長岡技大生
- 日英越トリリンガル：HCMUT 学生

**手続き：**
- 同一テーマについて各言語で Live API インタビュー
- 言語提示順は <span class="marker">カウンターバランス</span>

**デザイン：**
- <span class="marker">Within-subject</span>（同一個人が全言語条件に参加）

**テーマ：**
- 多文化共修ディスカッションに関わる教育・社会的トピック

---

## 応用先

### Application

<div class="bubble">

多文化共修ディスカッション前の **事前インタビュー** で各学生の <span class="marker">「言語間意見プロファイル」</span> を取得 → グループ分け最適化への入力（概念実証）

</div>

**狙い：**
- 異なる意見強度・主張パターンの学生を組み合わせる
- ディスカッションの質を高めるグループ構成を提案

---

## 投稿戦略

### Publication Strategy

| 投稿先 | 特性 | 採択率 | APC |
|:---|:---|:---:|:---:|
| **IEEE Access**（第一候補）| 応用志向・技術健全性重視 | ~27–28% | $2,160 |
| IEEE Trans. Affective Computing | 感情・確信度・音声の計算的研究 | より厳しい | 高め |

**IEEE Access 通過のための 3 点セット：**

1. 再現可能なシステム実装（コード公開）
2. 新規多言語データセット（音声＋転写＋アノテーション）
3. 指標の妥当性検証

---

<!-- _class: compact -->

## Month 1（6 月）：文献精読

### Literature Reading

**① FLE（外国語効果）基礎**
- Costa et al. (2014). *Your morals depend on language.* PLOS ONE
- Keysar, Hayakawa & An (2012). *The Foreign-Language Effect.* Psych. Sci.
- Circi et al. (2021). *Meta-analysis of FLE in decision-making.* PB&R

**② Cultural Frame Switching**
- Ramírez-Esparza et al. (2006). *Do bilinguals have two personalities?* JRP

**③ 音声・確信度の定量化**
- Eyben et al. (2015). *eGeMAPS.* IEEE T. Affective Computing

**④ アダプティブ AI インタビュー**
- Wuttke et al. (2024). *AI Conversational Interviewing.* arXiv:2410.01824

**⑤ グループ分け最適化（応用背景）**
- Minimum Entropy Collaborative Groupings (2023). PLOS One

---

## Month 1：タスク

### Tasks

- 各自が担当論文を読み、**A4 1 枚で概要まとめ**（日英いずれでも可）
- **用語集の共同作成**：Opinion Strength・Argumentative Consistency・FLE・CFS・within-subject を日英越で確認
  - 意図：翻訳ズレで結果が歪まないよう、参加者説明・プロトコル・論文で一貫した用語を使うため
- **Gemini Live API のデモ起動**（Hello World レベル）
- **ディスカッション用テーマ候補 3 つを考える**（多文化共修で議論されそうなもの）

---

## Month 2（7 月）：システム設計

### System Design

**追加読書：**
- Stab & Gurevych (2017). *Parsing Argumentation Structures.* Comp. Linguistics
- Qi et al. (2023). *Cross-Lingual Consistency of Factual Knowledge.* arXiv:2310.10378
- Vietnamese politeness 研究（面子・間接表現の機能把握）

**タスク：**
- **インタビュープロトコル設計**：フォローアップロジック・反論提示・言語切替手順
- **Live API 実装スケッチ**：WebSocket・VAD・セッション管理・ログ
- **ヘッジ語対応表**（JA：〜と思います / EN：I think / VI：tôi nghĩ など）
- **IRB 申請準備**：音声録音・個人情報の同意書草案（日越両国）

---

## Month 3（8 月）：パイロット & 妥当性検証

### Pilot Run & Validity Check

**追加読書：**
- Bilingualism: Language and Cognition. *Resisting persuasion in cases of ideological conflict.* （反論フォローアップ設計の根拠）

**タスク：**
- **パイロット実施**：日英バイリンガル 5〜10 名（NUT 側）で全パイプライン検証
- **人手アノテーション**：自動指標と人手評価の一致（<span class="marker">Cohen's κ &lt; 0.4 なら再設計</span>）
- **越語 ASR 精度の事前測定**：Gemini Live API の越語認識精度を実測
- **データパイプライン完成**：音声 → Whisper → 特徴抽出 → スコアリング → 可視化
- **HCMUT 向けブリーフィング資料**（英語・越語）を渡越前に完成

---

## 役割分担（暫定）

### Tentative Role Assignment

| 担当 | NUT 側 | HCMUT 側 |
|:---|:---|:---|
| システム実装 | Eita| — |
| 日英プロトコル設計 | NUT 学生 | — |
| 越語プロトコル・翻訳監修 | — | HCMUT 学生 |
| データアノテーション（越語）| — | HCMUT 学生 |
| 統計解析 | Eita | - |
| 論文執筆 | 雲居（主導）| 共著 |

---

## リスクと対策

### Key Risks & Mitigations

**① 越語 ASR 精度**
- Live API は英語品質が最高 → Month 3 で実測し、誤認識率を統制変数として記録

**② FLE 効果量の幅**
- g = 0.09〜0.40 と研究間で大きい → <span class="marker">null result 想定設計</span>で論文化保証

**③ 倫理審査（IRB）**
- 日越両国で IRB・インフォームドコンセント・匿名化・Google API への音声送信同意

**④ Live API セッション制限**
- 1 セッション約 15 分で期限切れ → 長いインタビューは <span class="marker">分割設計</span>

---

## 今後の作業

### Next Steps（チーム間協働計画）

**6 月中（プレ調査フェーズ）**
- EitaとHieuのチームは関連論文を輪読し理解を深める
- 両チームは **Slack** 上で内部的に議論・意見交換
- **Eita・Kei** が Khai と Hieu の研究進捗をサポートし、共同研究のための課題を提供

**7 月以降（定期報告フェーズ）**
- Tho 教授に <span class="marker">2 週間ごとの会議開催</span> を提案
- 2 チームは 7 月上旬から教授へ **2 週間ごと** に進捗報告

---

<!-- _class: lead -->

# ご清聴ありがとうございました

### Thank You for Listening!

**松浦 瑛太**
機械学習理論研究室（TML Lab）
長岡技術科学大学


---
<!-- _class: compact -->

## 付録：用語集 ①（研究デザイン・倫理）

### Glossary ① — Study Design & Ethics

**カウンターバランス**
複数条件（3 言語）の提示順を参加者ごとに系統的に変える研究手法。順序効果（疲労・慣れ）を統制する。

**Within-subject（被験者内デザイン）**
同一個人が全条件に参加するデザイン。個人差の影響を取り除き、少ない参加者数で統計的検出力を得られる。

**プロトコル**
インタビューの標準化された手順書。開始挨拶〜質問順序〜終了挨拶までを文書化し、誰がやっても同じ条件で再現できるようにする。

**インフォームドコンセント**
研究の目的・手順・リスク・辞退権を参加者に十分説明し、書面で同意を得る倫理手続き。



---
<!-- _class: compact -->

## 付録：用語集 ②（評価・統計・技術）

### Glossary ② — Measurement, Statistics & Tech

**人手アノテーション**
人間（研究者）が手作業でデータに評価値を付ける作業。自動指標の妥当性検証に使う。

**Cohen's κ（カッパ）**
2 評価者間の一致度を測る統計指標（0 〜 1）。0.4 未満は一致不十分（Landis & Koch 1977）。

**eGeMAPS**
音声から確信度・感情・話し方の特徴を抽出する標準 88 特徴セット（Eyben et al. 2015）。Opinion Strength の韻律的指標として使用。

**LaBSE**
Google が公開した多言語文埋め込みモデル。異言語間の文意味類似度を計算できる。Argumentative Consistency 測定に使用。

**ASR（Automatic Speech Recognition）**
自動音声認識。Live API が内部で音声を文字に変換する処理。


