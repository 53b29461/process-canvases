# Process Canvases — プロセス可視化グラフ集

Cytoscape.js を用いた業務フロー・工程のグラフ可視化プロジェクト。
各題材を **2パターン** で表現し、用途に応じて使い分ける。

## 収録題材

| 題材 | 依存関係（ANDゲート）版 | 時系列タイムライン版 |
|------|----------------------|-------------------|
| アニメ製作 | `deps/anime-prod-deps.html` | `timeline/anime-prod-timeline.html` |
| 引越し | `deps/moving-graph.html` | `timeline/moving-timeline.html` |
| PC持ち出し | `deps/pc-carryout-deps.html` | `timeline/pc-carryout-timeline.html` |

## 2つのグラフパターン

### 依存関係（ANDゲート）版
- **向き:** 「複数の前提条件が揃わないと先に進めない」構造
- **特徴:** ANDゲートノード（緑破線六角形）で依存を明示、マルチペアレントエッジ
- **エッジ:** main（青実線=必須） / dashed（灰点線=並行可能） / fb（赤破線=フィードバック）

### 時系列タイムライン版
- **向き:** 「フェーズごとに並行タスクが発生する」プロセス俯瞰
- **特徴:** phase-headノード（round-tag）でフェーズ区切り、メインライン+並行タスク分岐
- **エッジ:** main（青実線=時系列ライン） / dashed（灰点線=フェーズ内タスク） / fb（赤破線=フィードバック）

## 共通仕様

- ライトテーマ（Catppuccin Latte）
- cose レイアウト（アニメーション付き）
- START / GOAL 独立ノード（round-octagon）
- フィードバックループは赤破線（triangle-backcurve矢印）
- ドラッグ: パン / ホイール: ズーム / Re-layout ボタン

## 新規題材追加手順

1. `graph-cytoscape` スキルを読み込む
2. 題材の全タスクを洗い出し、2パターンそれぞれでHTML生成
3. 上記テーブルに追記
