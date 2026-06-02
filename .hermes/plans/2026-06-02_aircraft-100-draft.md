# 航空機開発プログラム — 100ノード草案

全10フェーズから各10ノード程度を抽出したサンプル。
全体の構造と命名規則・依存関係の確認用。

## 命名規則

- `p{phase}-{id}` (例: p0-concept, p1-wing, p4-assembly)
- ANDゲート: `g-{name}-done`
- トラブル: `tr-{name}`

## 100ノード一覧

### P0: プログラム計画（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| start | START | hexagon | 白/青 |
| p0-concept | 事業構想 | ellipse | white |
| p0-market | 市場調査 | diamond | white |
| p0-business | 事業計画書 | roundedRect | white |
| p0-fund | 資金調達 | hexagon | white |
| p0-partner | リスク分担パートナー選定 | roundedRect | white |
| p0-master-sched | マスタースケジュール | hexagon | white |
| p0-risk | リスク評価 | diamond | white |
| p0-corp | プログラム組織設立 | hexagon | white |
| p0-go | プログラムゴーサイン | hexagon | white |
| g-plan-done | 計画完了(AND) | hexagon(green) | green |

### P1: 機体設計（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p1-aero | 空力設計 | hexagon | blue |
| p1-wing | 主翼設計 | hexagon | blue |
| p1-fuse | 胴体設計 | hexagon | blue |
| p1-tail | 尾翼設計 | elliipse | blue |
| p1-struct | 構造解析(FEM) | diamond | blue |
| p1-hyd | 油圧系統設計 | ellipse | blue |
| p1-elec | 電気系統設計 | ellipse | blue |
| p1-avionics | アビオニクス設計 | hexagon | blue |
| p1-cockpit | コックピット設計 | ellipse | blue |
| p1-cabin | キャビン設計 | ellipse | blue |
| g-design-done | 設計完了(AND) | hexagon(green) | green |

### P2: 認証・法規（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p2-cert-plan | 認証計画書 | roundedRect | lavender |
| p2-faa | FAA申請 | roundedRect | lavender |
| p2-easa | EASA申請 | roundedRect | lavender |
| p2-far25 | FAR Part25ベースライン | diamond | lavender |
| p2-do178 | DO-178C計画 | diamond | lavender |
| p2-do254 | DO-254計画 | diamond | lavender |
| p2-ssa | System Safety Assessment | hexagon | lavender |
| p2-noise | 騒音適合計画 | ellipse | lavender |
| p2-env | 排出ガス適合計画 | ellipse | lavender |
| p2-maint | 整備審査計画 | ellipse | lavender |

### P3: サプライチェーン（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p3-strategy | 調達戦略策定 | hexagon | sky |
| p3-rfp | RFP発行 | roundedRect | sky |
| p3-engine | エンジン選定 | roundedRect | sky |
| p3-ldg | 降着装置選定 | roundedRect | sky |
| p3-av-supplier | アビオニクスサプライヤー | roundedRect | sky |
| p3-composite | 複合材部品サプライヤー | roundedRect | sky |
| p3-seat | シートサプライヤー | roundedRect | sky |
| p3-fai | First Article Inspection | diamond | sky |
| p3-audit | サプライヤー監査 | diamond | sky |
| p3-logistics | 物流計画 | ellipse | sky |

### P4: 製造工程（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p4-plant | 工場建設 | hexagon | green |
| p4-jig | 治工具製作 | diamond | green |
| p4-mach | 金属部品加工 | ellipse | green |
| p4-composite-mfg | 複合材部品成形 | ellipse | green |
| p4-wiring | 配線製作 | ellipse | green |
| p4-wing-assy | 主翼組立 | hexagon | green |
| p4-fuse-assy | 胴体組立 | hexagon | green |
| p4-fa | 最終組立 | hexagon | green |
| p4-paint | 塗装 | ellipse | green |
| p4-inspec | 完成検査 | diamond | green |
| g-build-done | 製造完了(AND) | hexagon(green) | green |

### P5: 地上試験（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p5-static-test | 静的強度試験 | hexagon | teal |
| p5-fatigue | 疲労試験 | hexagon | teal |
| p5-iron-bird | Iron Bird試験 | hexagon | teal |
| p5-lightning | 落雷試験 | diamond | teal |
| p5-emc | EMC試験 | diamond | teal |
| p5-evac | 緊急脱出試験 | diamond | teal |
| p5-bird | 鳥衝突試験 | diamond | teal |
| p5-engine-run | エンジン地上運転 | roundedRect | teal |
| p5-cabin-press | 与圧試験 | ellipse | teal |
| p5-fuel-sys | 燃料システム試験 | ellipse | teal |

### P6: 飛行試験（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p6-first-flight | 初飛行 | hexagon | yellow |
| p6-fleet | 試験機整備(FT1~6) | hexagon | yellow |
| p6-envelope | 飛行エンベロープ拡大 | hexagon | yellow |
| p6-stall | 失速特性試験 | diamond | yellow |
| p6-highlift | 高揚力装置試験 | diamond | yellow |
| p6-autoflight | 自動操縦試験 | diamond | yellow |
| p6-cold | 寒冷地試験 | ellipse | yellow |
| p6-hot | 高温地試験 | ellipse | yellow |
| p6-crosswind | 横風試験 | diamond | yellow |
| p6-fnr | 機能信頼性試験 | hexagon | yellow |

### P7: 型式証明（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p7-compliance | コンプライアンス文書 | roundedRect | peach |
| p7-flight-rvw | 飛行審査 | diamond | peach |
| p7-struct-rvw | 構造審査 | diamond | peach |
| p7-sys-rvw | システム審査 | diamond | peach |
| p7-engine-rvw | エンジン審査 | diamond | peach |
| p7-noise-cert | 騒音証明 | ellipse | peach |
| p7-maint-rvw | 整備審査 | diamond | peach |
| p7-crew-rvw | 乗員審査 | diamond | peach |
| p7-tc | 型式証明(TC)発行 | hexagon | peach |
| p7-production | 生産証明(PC) | hexagon | peach |

### P8: 量産準備（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p8-rate | 生産レート計画 | hexagon | maroon |
| p8-supplier-cap | サプライヤー容量拡大 | diamond | maroon |
| p8-line-stab | ライン安定化 | hexagon | maroon |
| p8-mod-proc | 改造(mod)対応プロセス | roundedRect | maroon |
| p8-cost-down | 製造コストダウン | diamond | maroon |
| p8-quality | 品質指標管理 | diamond | maroon |
| p8-first-prod | 量産型初号機 | hexagon | maroon |
| p8-delivery | 初号機引渡し | roundedRect | maroon |
| p8-tool-upgrade | 治工具更新 | ellipse | maroon |
| p8-train-work | 生産訓練 | ellipse | maroon |

### P9: 運航開始（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| p9-first-delivery | 初号機お披露目 | hexagon | mauve |
| p9-pilot-train | パイロット訓練 | hexagon | mauve |
| p9-maint-train | 整備士訓練 | hexagon | mauve |
| p9-manual | マニュアル完成 | roundedRect | mauve |
| p9-support-center | サポートセンター開設 | roundedRect | mauve |
| p9-spare-parts | スペアパーツ網 | diamond | mauve |
| p9-first-commercial | 初商業運航 | hexagon | mauve |
| p9-data-feedback | 運航データ収集 | diamond | mauve |
| p9-sb | Service Bulletin発行 | roundedRect | mauve |
| p9-improve | 継続的改善 | ellipse | mauve |
| goal | GOAL | hexagon | 白/青 |

### トラブル（10 nodes）

| ID | ラベル | 形状 | 色 |
|----|--------|------|-----|
| tr-weather | 天候試験遅延 | diamond | red |
| tr-design-change | 設計変更 | diamond | red |
| tr-struct-fail | 構造試験不合格 | diamond | red |
| tr-engine-dev | エンジン開発遅延 | diamond | red |
| tr-supplier-bankrupt | サプライヤー倒産 | diamond | red |
| tr-cert-delay | 認証遅延 | diamond | red |
| tr-cost-over | コスト超過 | diamond | red |
| tr-quality-issue | 品質問題発生 | diamond | red |
| tr-staff-short | 技術者不足 | diamond | red |
| tr-competitor | 競合機投入 | diamond | red |
| tr-report | トラブル対応 | roundedRect | red |

## 合計

ノード数: START(1) + GOAL(1) + P0(10+1AND) + P1(10+1AND) + P2(10) + P3(10) + P4(10+1AND) + P5(10) + P6(10) + P7(10) + P8(10) + P9(10) + TR(11) = **105ノード**

上記の草案でご確認いただけますか？
