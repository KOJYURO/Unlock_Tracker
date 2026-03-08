# Unlock Tracker

Last Updated: 2026-03-09

## English

Unlock Tracker is a 7 Days to Die support toolset with two surfaces.

1. In-game categories in Skills UI
2. Web viewer at `https://7daystodie.jp/hugh/unlocktracker.php`

### What It Solves

- Bulk review of unlock targets and requirements.
- Per-target condition inspection, including quality cap requirements.
- Player share comparison via token/URL on web.
- In-page `.ttp` parsing (optional `players.xml`) for direct current unlock-state comparison.
- Multi-player switching after folder parse via parsed-player selector.
- Manual mapping workflow for unresolved condition sources.

### Canonical Docs

Unlock Tracker documents are centralized in this directory with the minimum file set.

- `README.md`: Project overview for GitHub.
- `USER_MANUAL.md`: User guide + admin guide + migration summary (canonical).

No standalone migration notes file is maintained.

Steam publication copy is maintained at:

- `/root/Release/Steam Docs/UNLOCK_TRACKER_USER_MANUAL_STEAM.md`

### Main Files

- `Config/progression.xml`
- `Config/items.xml`
- `Config/XUi/windows.xml`
- `Config/generated/unlock_baseline.json`
- `unlock_master_catalog.csv`
- `scripts/generate_unlock_tracker.py`

### Regeneration

When game XML changes, run:

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py'
```

With explicit paths:

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py' \
  --game-config '/root/Release/SharedFiles/GameConfig/V2.5 Survival Revival Stable' \
  --mod-root '/root/Release/Unlock Tracker'
```

### Support

- GitHub: `https://github.com/7DTD-JP/Unlock_Tracker`
- Discord: included `.url` file in this folder

## 日本語

Unlock Trackerは、7 Days to Die向けの2画面構成サポートツールです。

1. ゲーム内Skills UIのカテゴリ表示
2. Webビューワー `https://7daystodie.jp/hugh/unlocktracker.php`

### 解決すること

- アンロック対象と必要条件をまとめて確認できます。
- 品質上限条件を含む、対象ごとの条件確認ができます。
- Webでtoken/URLを使ったプレイヤー比較ができます。
- ページ内で`.ttp`（任意で`players.xml`）を解析し、現在アンロック状態を直接比較できます。
- フォルダ解析後、解析済みプレイヤー選択で複数プレイヤーを切り替えできます。
- 未解決条件ソースの手動マッピング運用に対応します。

### 正規ドキュメント

Unlock Tracker関連ドキュメントは、このディレクトリに最小構成で集約しています。

- `README.md`: GitHub向け概要。
- `USER_MANUAL.md`: ユーザーガイド + 管理者ガイド + 移行サマリー（正本）。

移行ノート単体ファイルは維持せず、内容は`USER_MANUAL.md`へ統合しています。

Steam公開用BBドキュメントは以下で管理します。

- `/root/Release/Steam Docs/UNLOCK_TRACKER_USER_MANUAL_STEAM.md`

### 主要ファイル

- `Config/progression.xml`
- `Config/items.xml`
- `Config/XUi/windows.xml`
- `Config/generated/unlock_baseline.json`
- `unlock_master_catalog.csv`
- `scripts/generate_unlock_tracker.py`

### 再生成

ゲームXML更新時は次を実行します。

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py'
```

明示パス指定の場合:

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py' \
  --game-config '/root/Release/SharedFiles/GameConfig/V2.5 Survival Revival Stable' \
  --mod-root '/root/Release/Unlock Tracker'
```

### サポート

- GitHub: `https://github.com/7DTD-JP/Unlock_Tracker`
- Discord: 同梱の`.url`ファイルを参照