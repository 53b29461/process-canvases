# 1000ノードグラフ「航空機開発プログラム」計画

## ゴール

vis-network を用いて **1000ノード級の大規模依存関係グラフ** を生成し、プロジェクト全体の工程可視化を実現する。題材として **民間旅客機（B737/A320クラス）の開発プログラム** を選定する。

## 背景

- 既存実績: 家を建てる（196ノード）、病院建設・開業（298ノード、431エッジ）
- vis-network は公式ドキュメントで「数千ノードまでスムーズ」と謳っており、forceAtlas2Based 物理エンジンが1000ノードでも安定動作することを検証するのが本件の主目的
- Catppuccin Latte ライトテーマ、ANDゲート（緑破線六角形）、3種エッジ（main/dashed/fb）は既存のスタイルを踏襲

## 題材選定理由

航空機開発プログラム（民間旅客機）は以下により1000ノードに自然に到達する：

1. **多層的なサブシステム**: 機体構造/主翼/エンジン/アビオニクス/キャビン/降着装置 — 各サブシステムが多数のタスクを持つ
2. **厳格な認証プロセス**: FAA/EASA 型式証明（Type Certificate）は数百の審査項目
3. **サプライチェーン**: 世界中のサプライヤーとの契約・部品認定
4. **製造工程**: 部品製造→大組立→最終組立→検査
5. **試験計画**: 構造試験/疲労試験/システム試験/飛行試験 — 各種試験で多数のマイルストーン
6. **運航開始準備**: パイロット訓練/整備マニュアル/カスタマーサポート網

## フェーズ構成

| Phase | 名称 | 想定ノード数 | 色 |
|-------|------|-------------|-----|
| P0 | Program Planning（プログラム計画） | ~50 | #dce0e8 (white) |
| P1 | Aircraft Design（機体設計） | ~150 | #8caaee (blue) |
| P2 | Certification & Regulation（認証・法規） | ~70 | #b4befe (lavender) |
| P3 | Supply Chain（サプライチェーン） | ~80 | #74c7ec (sky) |
| P4 | Manufacturing Process（製造工程） | ~200 | #a6e3a1 (green) |
| P5 | Ground Testing（地上試験） | ~80 | #94e2d5 (teal) |
| P6 | Flight Testing（飛行試験） | ~100 | #f9e2af (yellow) |
| P7 | Type Certification（型式証明） | ~60 | #fab387 (peach) |
| P8 | Production Ramp-up（量産準備） | ~80 | #fe640b (maroon) |
| P9 | Entry into Service（運航開始） | ~70 | #cba6f7 (mauve) |
| TR | Troubles（トラブル） | ~50 | #d20f39 (red) |
| AND gates | | ~30 | green dashed hexagon |
| START/GOAL | | 2 | — |
| **Total** | | **~1020** | |

## フェーズ別詳細タスク設計

### P0: Program Planning (~50 nodes)

- 事業計画策定（市場調査/需要予測/競合分析/採算性評価）
- 概念設計（コンフィグレーション/ペイロード/航続距離）
- プログラムゴーサイン/リスク評価
- 資金調達（銀行融資/出資/リスク分担パートナー）
- パートナー企業選定（リスクシェアリング）
- プロジェクト管理体制構築
- マスタースケジュール策定
- 認証戦略策定

### P1: Aircraft Design (~150 nodes)

- 空力設計（主翼/胴体/尾翼/ナセル/高揚力装置）
- 構造設計（主要構造要素/応力解析/疲労設計）
- システム設計（油圧/電気/空調/燃料/酸素/防氷/消火/飛行制御）
- アビオニクス設計（コックピット/航法/通信/自動操縦/FMS/EFB）
- キャビン設計（客室レイアウト/ギャレー/ラバトリー/エンターテイメント/非常用設備）
- 降着装置設計（前脚/主脚/ブレーキ/タイヤ）
- エンジンインターフェース（ポッド/スラストリバース/システム分界）
- 設計レビュー（PDR/CDR/FDR）
- 各種解析（FEM/CFD/システムシミュレーション）

### P2: Certification & Regulation (~70 nodes)

- FAA/EASA 型式証明申請
- 認証ベースライン策定（FAR Part 25, CS-25）
- 特殊条件/同等安全レベル（SC/ELOS）合意
- 認証計画書作成（CP/CRI/PSP）
- 設計変更管理プロセス
- 耐空性審査チーム（AEG）対応
- 環境適合証明（騒音/排出ガス）
- 構造認証項目（Static/Fatigue/Damage Tolerance）
- システム認証項目（System Safety Assessment/ARINC）
- ソフトウェア認証（DO-178C）
- ハードウェア認証（DO-254）
- 認証試験計画書

### P3: Supply Chain (~80 nodes)

- サプライヤー戦略策定（Make/Buy）
- RFP発行・評価・選定
- サプライヤー契約（品質/納期/コスト）
- サプライヤー監査（AS9100/AC7004）
- 部品認定試験（First Article Inspection）
- 主要サプライヤー: エンジン/降着装置/アビオニクス/複合材部品/シート/キャビン内部品
- 輸送・物流計画
- リードタイム管理/調達リスク評価

### P4: Manufacturing Process (~200 nodes)

- 製造設備計画（工場建設/ライン設置）
- 治工具設計製作（ジグ/テンプレート/自動リベッター）
- 部品製造（金属部品/複合材部品/チューブ/配線）
- 小組立（リブ組立/スキンパネル/フレーム）
- 大組立（主翼/胴体/尾翼/エンジンストラット）
- 最終組立（機体結合/システムインストール）
- ファイナルライン（キャビン/塗装/試運転）
- 品質検査（NDT/寸法検査/機能試験）
- 製造コスト管理/歩留まり改善

### P5: Ground Testing (~80 nodes)

- 構造試験機製作（静的/疲労）
- 静的強度試験（Limit Load/Ultimate Load）
- 疲労試験（Full-scale Fatigue Test）
- 落雷試験
- タイヤ/ブレーキ試験
- システム試験（Iron Bird/Electric Bird/Cabin Mockup）
- エンジン運転試験（Ground Run/EMC）
- 燃料システム試験
- キャビン圧力/与圧試験
- 緊急脱出試験（Evacuation Demo）
- 鳥衝突試験/氷衝突試験

### P6: Flight Testing (~100 nodes)

- 初飛行（1号機/2号機）
- 飛行試験機製作（FT1〜FT6）
- フライトエンベロープ拡大
- 空力性能測定
- エンジン特性試験（Airs tart/Relight/Reverse）
- フライ・バイ・ワイヤ則検証
- 失速特性試験（Stall/GWPS）
- 高揚力装置試験
- オートパイロット/自動着陸
- 寒冷地試験/高温地試験
- 高高度試験
- 横風離着陸
- 水たまり試験（Aquaplaning）
- ETOPS認定試験
- 機能信頼性試験（Function & Reliability）

### P7: Type Certification (~60 nodes)

- 認証文書提出（Compliance Matrix/Report）
- 耐空性審査（飛行/構造/システム/パワープラント）
- 整備審査（MRB/MRD/MPD）
- 乗員審査（CCD/Flight Crew/Manual）
- 環境審査（騒音/排出ガス）
- 生産証明（PC/POA）
- 型式証明（TC）発行 / 追加型式証明（ATC）
- 運航証明書発行（COA）

### P8: Production Ramp-up (~80 nodes)

- 量産型製造ライン安定化
- 生産レート向上（Rate Readiness Review）
- サプライチェーン容量拡大
- サプライヤーパフォーマンス監視
- 製造品質指標（FAR/FAA/EASA）
- 改造（Mod）対応プロセス
- 製造コストダウン
- 量産型初号機引渡し（First Production Delivery）

### P9: Entry into Service (~70 nodes)

- 初号機引渡し（First Delivery）
- パイロット訓練（CFT/Line Training）
- 整備訓練（Maintenance Training）
- カスタマーサポートセンター開設
- スペアパーツネットワーク構築
- 運航開始記念式典
- 運航初期サポート（Initial Operation Support）
- 運航データ収集/フィードバック
- 改善プログラム（SB/Service Bulletin）

### TR: Troubles (~50 nodes)

- 設計変更発生（飛行試験結果）
- 構造試験不合格
- エンジン開発遅延
- サプライヤー倒産
- 認証遅延
- コスト超過
- 天候による試験遅延
- 生産トラブル（品質問題）
- 労働争議
- 部品調達難
- 技量パイロット不足
- 航空会社キャンセル
- 競合機投入
- 法規変更対応

## 技術的考慮

### 物理エンジンパラメータ（1000ノード想定）

| パラメータ | 値 | 理由 |
|-----------|-----|------|
| solver | forceAtlas2Based | 大規模で最も安定 |
| gravitationalConstant | -28 | 弱めの反発で拡散防止 |
| centralGravity | 0.002 | 全体が中央に収束 |
| springLength | 230 | ノード間距離を広めに |
| springConstant | 0.015 | 弱めのバネで安定化 |
| damping | 0.6 | 収束性向上 |
| maxVelocity | 3 | 発散防止 |
| stabilization.iterations | 2000 | 1000ノードでは十分な反復数 |

### エッジスムージング

- curvedCW, roundness: 0.04（密になりすぎないよう小さめ）

### ノード定義

- ラベルは 2〜5文字程度の日本語に短縮
- ANDゲートノードはサイズ32に拡大（既存の28から微増）
- 各フェーズのカラーとシェイプ統一

### ファイル生成方式

- `execute_code` ではなく `write_file` で Python スクリプトを書き、`terminal` で実行する方式に統一
- 前回の `hermes_tools` 依存問題を回避するため、`write_file` のみ使用（`execute_code` 内から `terminal` + `write_file` を呼ぶのではなく、まず Python スクリプトを `write_file` で保存 → `terminal` で実行）

## リスク

1. **JSシンタックスエラー**: 1000ノードの JS 配列でコンマ欠落が発生した場合のデバッグが困難。生成時にコンマ区切りを確実に行う。
2. **物理エンジン収束時間**: 1000ノードで forceAtlas2Based は初期安定化に時間がかかる。stabilization.iterations を2000に設定。
3. **ブラウザメモリ**: 1000ノード×700エッジ程度でも vis-network は Canvas 2D レンダリングで比較的軽量。想定範囲内。
4. **ファイルサイズ**: 1000ノードの HTML は約 250〜300KB になる見込み。問題なし。

## 実行手順

1. `/home/rkametani/process-canvases/aircraft-dev-deps.html` として生成
2. ローカル http://localhost:5173 で動作確認
3. JSエラー0、キャンバス描画確認
4. 必要に応じてノード数調整（1000±50に収める）

以上、承認いただければ実装に入ります。
