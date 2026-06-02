# Process Canvases — プロセス可視化グラフ集

Cytoscape.js を用いた業務フロー・工程のグラフ可視化プロジェクト。
各題材を **依存関係（ANDゲート）版** に限定して管理する。

## 収録題材

| 題材 | 依存関係（ANDゲート）版 |
|------|----------------------|
| アニメ製作 | `anime-prod-deps.html` |
| 引越し | `moving-deps.html` |
| PC持ち出し | `pc-carryout-deps.html` |
| TryHackMe Overpass | `overpass-deps.html` |
| Webサービス開発 | `webapp-dev-deps.html` |
| 生活タスク全体マップ | `private/life-management-deps.html`（非公開） |

## 仕様

- ライトテーマ（Catppuccin Latte）
- cose レイアウト（アニメーション付き）
- START / GOAL 独立ノード（round-octagon）
- ANDゲートノード（緑破線六角形）で依存を明示、マルチペアレントエッジ
- エッジ: main（青実線=必須） / dashed（灰点線=並行可能） / fb（赤破線=フィードバック）
- ドラッグ: パン / ホイール: ズーム / Re-layout ボタン

## プライバシー

- 個人情報を含むグラフは `private/` ディレクトリに配置
- `.gitignore` で `private/` を除外済み（GitHub 非公開）

## 新規題材追加手順

1. `graph-cytoscape` スキルを読み込む
2. 題材の全タスクを洗い出し、依存関係構造でHTML生成
3. `依存関係（ANDゲート）版` のカラムに追記
