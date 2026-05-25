# MAISON IVOIRE — beauty-salon/ivoire Spec

**Status:** Draft
**Author:** torifo
**Created:** 2026-05-25
**Updated:** 2026-05-25

---

## 1. Overview

### Problem Statement
銀座・丸の内圏の高単価ヘアサロン Web は、白基調を標榜しながら実態は「白＋彩度の高い差し色＋大きなスタッフ顔写真＋ビフォーアフター」に着地しがちで、本来の「白の純度で勝負する」という美学から外れている。顔写真と賑やかなメニュー表が前面に出ることで、メゾン（maison）としての静謐さ・素材感・職人性が伝わらず、結果として「銀座らしい高級ヘアサロン」が量産的なテンプレートに同化してしまう。白の階調と素材のマクロだけで上質さを成立させた事例が国内ヘアサロン Web には極端に少ない。

### Goal
架空のヘア中心トータル美容メゾン **MAISON IVOIRE**（メゾン・イヴォワール、東京銀座を本店想定）を実装し、「**白の彩度の支配**」だけで高級感を完結させる Web を成立させる。アイボリー・大理石・鋼の三段階の白〜灰の階調と、髪・首筋・銀器・自然光のマクロ写真のみで構成し、顔出しスタッフ写真とビフォーアフターを排した「銀座メゾンの静謐」を提示する。和文明朝と Cormorant Garamond の組合せで、欧州メゾンと和の所作の双方を匂わせる。

### Non-Goals
- 顔出しスタイリスト集合写真（メゾンの匿名性を保持）
- ビフォーアフターの並置（変化は数値ではなく所作と仕上がりのマクロで匂わせる）
- 割引・キャンペーン・期間限定訴求
- 多店舗展開を強調する「全国 N 店舗」の数値訴求
- 鮮やかな差し色（ローズアクセントは唯一のニュアンスカラーとして極小面積のみ）
- カート / EC / オンライン決済
- 多言語切替（コピー内に英語を併記する設計で代替）

---

## 2. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 銀座勤務 30 代後半女性・年 4 回の指名予約 | 担当の技術と所作の質を確認したい | 自分の時間と髪を預ける判断ができる |
| US-02 | 都内在住 40 代女性・ヘアと頭皮ケアを一体で受けたい | メニューが価格を明示し、所要時間と工程が分かること | 当日の予定を組み立てやすい |
| US-03 | 海外赴任前の 30 代女性・最後の信頼サロンを探す | サロンの哲学・素材・水・道具に関する記述を読みたい | 数年来の付き合いに足るか判断できる |
| US-04 | 50 代女性・白髪との付き合いを再設計したい | 煽らないトーンで、長期の関係を提案するサロンか確かめたい | 安心して相談に行ける |

---

## 3. Functional Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | ヒーローは大判の白基調マクロ写真（髪 or 銀器 or 大理石）と、Cormorant Garamond の英文短句＋明朝の和文サブを縦組み風に配置。動画なし | P0 |
| FR-02 | 配色はアイボリー `#f4f0e8`、大理石 `#e8e4dc`、鋼 `#3a3a3a`、ローズアクセント `#c9a999` の 4 色のみ。アクセントは全体面積の 2% 以下に制限 | P0 |
| FR-03 | "PHILOSOPHY"（メゾンの哲学）セクション：水・光・道具・所作の 4 項目を縦長カードで提示。各カードはマクロ写真＋短文 | P0 |
| FR-04 | "MENU" セクション：ヘアを中心に 5〜7 メニュー（カット／カラー／トリートメント／ヘッドスパ／メゾン施術）。価格・所要時間・工程概要を明朝で整然と並べ、装飾罫線は hairline (`1px solid var(--line)`) のみ | P0 |
| FR-05 | "ATELIER"（店内）セクション：道具・椅子・床・窓のマクロ 4〜6 枚をモザイク状ではなく縦一列の余白多めレイアウトで配置 | P0 |
| FR-06 | "ARTISANS"（職人＝担当者紹介）：顔写真は使わず、手・はさみ・後ろ姿のマクロ＋経歴テキストのみ。匿名性を保つため氏名は姓のみ表記、入店年と修練分野を併記 | P0 |
| FR-07 | "RESERVATION" は「ご予約・お問合せ」の文言で、フォーム送信ではなく電話番号と問合せメール、来訪予約に必要な情報（希望日時・指名・初回/再訪）を提示するに留める | P0 |
| FR-08 | "JOURNAL"（メゾン便り）：髪・季節・道具に関する短い記事 3 件のリスト。日付＋タイトル＋簡素な抜粋のみ | P1 |
| FR-09 | アクセス・営業時間・定休日を本店情報として 1 ブロックに集約。地図画像は使わず、住所と最寄駅からの徒歩経路をテキストで | P0 |
| FR-10 | 全画面で vertical rhythm 6rem 以上、セクション間 8rem 以上の縦余白を確保。情報密度を意図的に下げる | P0 |
| FR-11 | ホバー演出は hairline の左→右伸展のみ。スケール変化・影・上下移動は禁止 | P1 |
| FR-12 | モバイル 1 カラム化（768px 以下）。ヒーロー写真は縦長 portrait に切替、英文短句は和文より先頭に置く | P0 |
| FR-13 | `prefers-reduced-motion: reduce` で reveal アニメーション全停止 | P1 |
| FR-14 | 画像はすべて Unsplash 外部 URL、`loading="lazy"`、`alt` は日本語で被写体を記述 | P0 |

---

## 4. Key Design Decisions

| Decision | Chosen | Rationale | Rejected |
|----------|--------|-----------|----------|
| 配色の支配 | アイボリー × 大理石 × 鋼 × ローズ（差し極小） | 「白の彩度の支配」を成立させるには、白の中に階調を 2 段以上設け、テキスト色も純黒ではなく温度のある鋼にする必要がある。ローズは "唯一の体温" としてリンク下線などに極小面積で残す | 白単色＋黒文字（コントラストが強すぎてメゾンの静謐が出ない）、白＋金（noir と方向性が被る） |
| ベース白の選定 | アイボリー `#f4f0e8` をページ地に、大理石 `#e8e4dc` をセクション区切り背景に | 紙の白ではなく、黄味と灰味のある二段階の白を併用することで「白の階調」を可視化。純白 `#ffffff` は使わない | `#ffffff` ベース（写真の白と地色が同化して階調が死ぬ） |
| テキスト色 | 鋼 `#3a3a3a`（純黒不使用） | 銀器と大理石の灰に同調する温度感。純黒 `#000` だと写真の白に対して刺さりすぎる | `#000000`、`#1a1614`（noir と被る暖色寄り黒） |
| 書体（欧文） | Cormorant Garamond 300–500 | Didot より柔らかく、Playfair より細身。銀座メゾンの "細い線" の美学に最も近い | Didot（強すぎる）、Playfair（rouge と被る）、Tenor Sans（細すぎて見出しに弱い） |
| 書体（和文） | Yu Mincho を第一候補、Noto Serif JP 400–500 を fallback | 明朝の縦線の細さでアイボリー地に溶けこむ。游明朝が macOS/Windows で標準搭載のため Web フォント未読時も品位を保つ | Shippori Mincho B1（wabi 担当）、Klee One（手書き感が強すぎる） |
| 写真トーン | 自然光・白の質感・銀の道具マクロ・髪のクローズアップ・大理石床 | 顔出しスタッフ・施術中の人物を排除し、素材と所作の "気配" のみで構成。彩度低め、ハイライト残し気味 | スタッフ集合写真、ビフォーアフター、笑顔の接客風景 |
| ヒーロー構成 | 大判マクロ写真 + Cormorant 英文短句 + 明朝の和文サブ + メタ情報極小 | 動画は通信負荷と静謐の阻害。文字は写真の余白側に寄せ、写真と文字を重ねない | 全画面動画背景、文字を写真に重ねるオーバーレイ |
| メニュー表現 | 価格・所要時間・工程を明朝で平行配置、罫線は hairline のみ | 「銀座らしさ」は装飾ではなく整列の精度で出す。メゾンとしての透明性も担保 | カード型・色付き枠・"人気No.1" バッジ |
| スタッフ匿名化 | 姓のみ表記＋手・道具・後ろ姿マクロ。顔写真なし | メゾンの匿名性を貫く（個人ブランドではなく館の格を売る）。指名は可能だが、顔出しはしない | 顔写真＋自己紹介文＋SNS リンク |
| CTA 言葉 | 「ご予約」「お問合せ」「Reservation」 | 煽らない丁寧語のみ。「今すぐ予約」「無料カウンセリング」は使わない | 「ご予約はこちら」「お得な初回限定」 |
| ホバー演出 | hairline の左→右伸展のみ | 動きは "気配" レベルに抑える。スケールや影は銀座の所作に合わない | scale(1.05)、box-shadow、translateY |
| 余白 | section 間 8rem、要素間 4rem を最低基準 | 「白の支配」は面積で決まる。情報密度を上げると即座にメゾンの格が落ちる | 1 画面に複数情報を詰める density-first レイアウト |
| ローズ差し色 | リンク下線・JOURNAL の日付・引用記号など極小面積のみ | "唯一の体温" の役割。広く使うと romantic に転び、メゾンの硬質感が崩れる | ボタン塗り・見出し色・背景帯 |

---

## 5. Design System

```css
/* ── Color ─────────────────────────────────────── */
--bg:          #f4f0e8;  /* Ivoire：ページ地。アイボリーの基準白 */
--bg-alt:      #e8e4dc;  /* Marbre：セクション区切り背景。大理石の灰白 */
--bg-paper:    #ede8de;  /* Vélin：中間階調。引用ブロック等 */
--fg:          #3a3a3a;  /* Acier：本文テキスト。鋼の温度ある灰黒 */
--fg-soft:     #6c6760;  /* Cendre：補助テキスト・キャプション */
--muted:       #9a948a;  /* Brume：メタ情報・日付 */
--line:        #c9c3b6;  /* Trait：hairline 罫線 */
--line-soft:   #ddd6c8;  /* Trait clair：背景に近い極薄罫 */
--accent:      #c9a999;  /* Rose：唯一の体温色。リンク下線・日付・引用記号のみ */
--accent-deep: #a98778;  /* Rose foncé：ホバー時のみ */

/* ── Typography ────────────────────────────────── */
--font-serif-en: 'Cormorant Garamond', 'Times New Roman', serif;
--font-serif-jp: 'Yu Mincho', '游明朝', 'YuMincho', 'Noto Serif JP', serif;
--font-sans-jp:  'Yu Gothic Medium', '游ゴシック Medium', 'Noto Sans JP', sans-serif;
                 /* sans はメタ情報・小キャプション・電話番号など極小範囲のみ */

--fw-serif-light:  300;
--fw-serif-base:   400;
--fw-serif-medium: 500;

--ls-display: 0.12em;  /* 見出し英文 letter-spacing */
--ls-body:    0.04em;  /* 本文 letter-spacing */
--lh-body:    1.9;     /* 本文行間 */
--lh-display: 1.3;     /* 見出し行間 */

/* ── Rhythm ────────────────────────────────────── */
--rhythm-section: 8rem;  /* セクション間 */
--rhythm-block:   4rem;  /* ブロック間 */
--rhythm-line:    1.5rem;
--gutter:         clamp(1.5rem, 4vw, 3rem);
--maxw-text:      62ch;
--maxw-page:      1180px;

/* ── Motion ────────────────────────────────────── */
--ease:       cubic-bezier(0.22, 0.61, 0.36, 1);
--dur-slow:   900ms;
--dur-base:   600ms;
--dur-quick:  300ms;

/* ── Borders ───────────────────────────────────── */
--hairline:   1px solid var(--line);
--hairline-soft: 1px solid var(--line-soft);
```

### タイポグラフィ・スケール

| 用途 | フォント | サイズ | weight | letter-spacing |
|------|---------|--------|--------|----------------|
| Hero 英文 | Cormorant Garamond | clamp(3.5rem, 7vw, 6rem) | 300 | 0.08em |
| Hero 和文サブ | Yu Mincho | clamp(0.95rem, 1.2vw, 1.05rem) | 500 | 0.18em |
| Section 英見出し | Cormorant Garamond | clamp(2.4rem, 4vw, 3.4rem) | 400 | 0.12em |
| Section 和小見出し | Yu Mincho | 0.85rem | 500 | 0.3em |
| 本文 | Yu Mincho | 0.95rem | 400 | 0.04em / lh 1.9 |
| メタ・キャプション | Yu Gothic Medium | 0.75rem | 500 | 0.2em / 大文字 |
| 価格・数値 | Cormorant Garamond | 1.1rem | 400 | 0.04em |

---

## 6. References

### 参考にした実サイト
- PEEK-A-BOO — https://www.peek-a-boo.co.jp/（白基調・大判英文 + 和文の階層・余白の取り方）
- MINX — https://minx-net.co.jp/（白＋自然光・モダンクラシックの整然レイアウト）
- TAYA — https://www.taya.co.jp/（トータルビューティーの理念主導コピー）
- Aesop — https://www.aesop.com/（ミニマリスト・アポセカリーの素材主義／※ 403 のため記述参考のみ）
- Shiseido — https://www.shiseido.com/us/en/（白基調・余白・和洋折衷の階層構造）

### シリーズ内
- 上位計画 — [`../../PLAN_BEAUTY_SALON.md`](../../PLAN_BEAUTY_SALON.md)
- 白基調 spec 参考 — [`../../stationery/mono/spec.md`](../../stationery/mono/spec.md)
- フォーマット基準 — [`../../fitness-gym/reshape/spec.md`](../../fitness-gym/reshape/spec.md)
- 親ナビゲーター（予定）— [`../README.md`](../README.md)

### Fonts
- [Cormorant Garamond](https://fonts.google.com/specimen/Cormorant+Garamond)
- [Noto Serif JP](https://fonts.google.com/noto/specimen/Noto+Serif+JP)（Yu Mincho の fallback）

### Image Source
- Unsplash — 自然光・大理石・銀のはさみ・髪のマクロ・白い窓辺などのキーワードで選定（実装時に確定）
