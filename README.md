# MAISON IVOIRE — beauty-salon / ivoire

架空のヘア中心トータル美容メゾン **MAISON IVOIRE**（メゾン・イヴォワール）のブランドサイト実装。
beauty-salon シリーズの `ivoire` ペルソナ（銀座白基調メゾン）向け。

## ブランドコンセプト

> **白、三階調と半音で。**

純白 `#ffffff` を使わず、Ivoire / Marbre / Vélin の三段階の白だけで「白の階調」自体を主役に据える。
顔出しスタッフ写真とビフォーアフターを排し、髪・首筋・銀器・自然光のマクロのみで構成。
ローズ `#c9a999` は "唯一の体温" として、リンク下線・JOURNAL の日付・引用記号のみに極小面積で残す。

- **配色** — Ivoire `#f4f0e8` × Marbre `#e8e4dc` × Vélin `#ede8de` × Acier `#3a3a3a` × Rose `#c9a999`
- **書体** — Cormorant Garamond 300–500（欧文）/ Yu Mincho（和文・fallback: Noto Serif JP）
- **写真** — 自然光・白の質感・銀器・髪のマクロ（Unsplash）
- **CTA** — 「ご予約」「お問合せ」「Reservation」の丁寧語のみ。煽らない

## セクション構成

1. **Hero** — 大判マクロ＋ Cormorant 英文短句「White, in three & a half tones.」＋明朝サブ（FR-01）
2. **Philosophy** — 水 / 光 / 道具 / 所作の四要素を縦長カードで（FR-03）
3. **Menu** — 六つの仕度（カット／カラー／トリートメント／スパ／メゾン施術／初回対話）。hairline 罫線のみ（FR-04）
4. **Quote** — Cormorant italic で銀座メゾンの founding principle
5. **Atelier** — 主室・道具・床・北窓のマクロ四枚を縦一列で（FR-05）
6. **Artisans** — 山城 / 朝倉 / 樋口、姓のみ＋手・後ろ姿マクロ。顔写真なし（FR-06）
7. **Journal** — 髪・道具・水に関する短い記事三件、日付はローズ（FR-08）
8. **Access / Reservation** — 銀座本店の住所・徒歩経路・電話・メール（FR-07 / FR-09）

「Reservation」CTA は header / access / footer の三箇所に静かに固定。

## 技術スタック

- Pure HTML + CSS + Vanilla JS（ビルドステップなし）
- シングルファイル `index.html`
- Google Fonts（Cormorant Garamond / Noto Serif JP / Noto Sans JP、preconnect 付き）
- IntersectionObserver でゆっくり reveal、`prefers-reduced-motion` で全停止（FR-13）
- Mobile-first / 768px 以下で 1 カラム化、ヒーロー写真は portrait に切替（FR-12）
- Cormorant 300 はモバイルで 400 に昇格（線痩せ対策）

## 反面教師として避けたこと

- 純白 `#ffffff` のページ地 → アイボリーと大理石と羊皮紙の三階調に置換
- 顔出しスタッフ集合写真 → 手・道具・後ろ姿のマクロ＋姓のみ表記
- 鮮やかな差し色 → ローズ `#c9a999` を全体面積 2% 以下に制限（リンク下線・日付・引用記号のみ）
- スケール変化・影・上下移動のホバー → hairline と僅かな `transform: scale(1.03)` 程度に留める
- 「今すぐ予約」「初回割引」 → 「Reservation」「初回の対話」「四十五分」の丁寧語

## ファイル

| Path | Purpose |
|---|---|
| `index.html` | メイン実装（hero / philosophy / menu / atelier / artisans / journal / access） |
| `spec.md` | 要件定義（FR-01〜FR-14） |
| `DESIGN_LEARNINGS.md` | 実装から得た知見 |
| `.nojekyll` | GitHub Pages 用（Jekyll 無効化） |
| `CNAME` | `design.beauty-salon-ivoire.riumu.net` |

## デプロイ

- **Live**: <https://design.beauty-salon-ivoire.riumu.net/>
- **Repo**: <https://github.com/torifo/design-beauty-salon-ivoire>

## License

架空のブランド／デザイン学習用途のみ。Unsplash 画像は各撮影者の Unsplash License に従う。

— *2026, by torifo*
