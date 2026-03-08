# Unlock Tracker User Manual

Last Updated: 2026-03-09  
Version: Unlock Tracker v1.1.1  
Canonical Path: `/root/Release/Unlock Tracker/USER_MANUAL.md`

## English

### 0. Documentation Policy
- Canonical docs are merged in this directory with the minimum file set.
- GitHub docs are limited to `README.md` and `USER_MANUAL.md`.
- Steam publication copy is maintained at:
- `/root/Release/Steam Docs/UNLOCK_TRACKER_USER_MANUAL_STEAM.md`

### 1. Overview
Unlock Tracker helps you review unlock requirements from both in-game and web views.

1. In-game Skills UI categories
2. Web viewer: `https://7daystodie.jp/hugh/unlocktracker.php`

### 2. Quick Start (Player)

#### 2.1 In-game
1. Join the server.
2. Open Skills UI.
3. Check Unlock Tracker categories.
4. Confirm entries are unlocked after requirements are met.

#### 2.2 Web
1. Open `https://7daystodie.jp/hugh/unlocktracker.php`.
2. Click `Reload Catalog`.
3. Select categories and targets in the left panel.
4. Narrow rows by search and filters.
5. Check required conditions in `Selection Summary`.
6. Optionally compare player data in `Player Unlock Analyzer`.

### 3. Web Screen Guide

#### Left Panel
- Category toggle (includes detailed buckets from master catalog).
- Target multi-select.
- Selected JSON export.

#### Center Panel
- Summary cards: `Total Targets`, `With Conditions`, `With Unresolved`, `With Quality Caps`.
- Table search, filtering, selection, and paging.

Language behavior:
- When EN is selected, static labels and placeholders are rendered in English.
- Dynamic status and summary strings are also switched.

#### Right Panel
- `Selection Summary`
- `Player Unlock Analyzer`
- `Unresolved Mapping Editor`

### 4. Filters
- State: `All`, `Selected Only`, `Unselected Only`, `With Unresolved Only`
- Condition: `All`, `With Conditions`, `Without Conditions`
- Quality: `All`, `With Quality Caps`, `Without Quality Caps`

### 5. Player Unlock Analyzer
- Accepts a raw share token.
- Accepts full `player_card_share` URL and auto-extracts the token.
- Supports `.ttp` analysis in-page by selecting files/folder that include `.ttp` (and optional `players.xml`).
- Supports multiple parsed players from the same folder; choose one from the parsed-player selector.
- Compares selected targets and shows `met` / `missing`.

### 6. Unresolved Mapping Editor
- `unresolved_conditions` are source strings not directly mapped yet.
- This is not always an error.
- Fill `mapped_to` only for sources you want to resolve, then save.

### 7. Screenshot Placement
Recommended order:

1. `Unlock_Tracker_1.png` after in-game quick start
2. `Unlock_Tracker_2.png` after web quick start
3. `Unlock_Tracker_3.png` before troubleshooting

Markdown template:

```md
### Screenshot 01
![Unlock Tracker 01](./Unlock_Tracker_1.png)

### Screenshot 02
![Unlock Tracker 02](./Unlock_Tracker_2.png)

### Screenshot 03
![Unlock Tracker 03](./Unlock_Tracker_3.png)
```

### 8. Admin Notes

#### 8.1 Data Sources
- Baseline JSON primary: `/root/WebSite/public_html/hugh/data/unlocktracker/unlock_baseline.json`
- Baseline JSON fallback: `/root/Release/Unlock Tracker/Config/generated/unlock_baseline.json`
- Quality CSV primary: `/root/WebSite/public_html/hugh/data/unlocktracker/unlock_master_catalog.csv`
- Quality CSV fallback: `/root/Release/Unlock Tracker/unlock_master_catalog.csv`
- Mapping storage: `/root/WebSite/public_html/hugh/data/unlocktracker/unresolved_mappings.json`

#### 8.2 API Endpoints
- `GET /hugh/api/unlocktracker_api.php?action=get_catalog`
- `GET /hugh/api/unlocktracker_api.php?action=get_mappings`
- `POST /hugh/api/unlocktracker_api.php?action=save_mappings`

#### 8.3 Authentication
- Viewer/API require Hugh login session.
- `save_mappings` is login protected.

### 9. Install and Regenerate

#### Install
1. Stop the server.
2. Place the folder as `Mods/Unlock Tracker`.
3. Start server and reconnect clients.
4. Verify categories in Skills UI.

#### Regenerate
Run when game XML changes.

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py'
```

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py' \
  --game-config '/root/Release/SharedFiles/GameConfig/V2.5 Survival Revival Stable' \
  --mod-root '/root/Release/Unlock Tracker'
```

Generated files:
- `Config/progression.xml`
- `Config/items.xml`
- `Config/XUi/windows.xml`
- `Config/generated/unlock_baseline.json`

### 10. Migration Summary
- Hand-maintained perk definitions were replaced by generated XML-based output.
- Baseline generation now uses `progression.xml`, `items.xml`, `item_modifiers.xml`, `blocks.xml`, `recipes.xml`.
- UI patching moved to attribute-level `set` operations for stability.
- Generated XPath no longer enforces strict `@tiered='false'`.

### 11. Troubleshooting

#### Categories do not appear in game
- Restart server and reconnect the client.
- Confirm install path is `Mods/Unlock Tracker`.

#### Web catalog load fails
- Check `unlock_baseline.json` path and permissions.
- Confirm Hugh login session.

#### Player comparison fails
- Verify token or URL format.
- Confirm public share payload exists.

#### Some rows remain unresolved
- Add mapping in `Unresolved Mapping Editor` and reload.

### 12. Support
- GitHub: `https://github.com/7DTD-JP/Unlock_Tracker`
- Discord: see `.url` file in package

## 日本語

### 0. ドキュメント方針
- 正規ドキュメントは、このディレクトリに最小ファイル数で統合管理します。
- GitHub向け文書は `README.md` と `USER_MANUAL.md` に限定します。
- Steam公開用コピーは以下で管理します。
- `/root/Release/Steam Docs/UNLOCK_TRACKER_USER_MANUAL_STEAM.md`

### 1. 概要
Unlock Trackerは、ゲーム内とWebの両方からアンロック条件を確認するためのツールです。

1. ゲーム内Skills UIカテゴリ
2. Webビューワー: `https://7daystodie.jp/hugh/unlocktracker.php`

### 2. クイックスタート（プレイヤー）

#### 2.1 ゲーム内
1. サーバーに参加します。
2. Skills画面を開きます。
3. Unlock Trackerカテゴリを確認します。
4. 条件達成後に対象がアンロックされることを確認します。

#### 2.2 Web
1. `https://7daystodie.jp/hugh/unlocktracker.php` を開きます。
2. `Reload Catalog` を押します。
3. 左パネルでカテゴリと対象を選択します。
4. 検索とフィルタで行を絞り込みます。
5. `Selection Summary` で必要条件を確認します。
6. 必要に応じて `Player Unlock Analyzer` でプレイヤー比較を行います。

### 3. Web画面ガイド

#### 左パネル
- カテゴリ切替（master catalog由来の詳細カテゴリを含む）。
- 対象の複数選択。
- 選択JSONのエクスポート。

#### 中央パネル
- サマリーカード: `Total Targets`, `With Conditions`, `With Unresolved`, `With Quality Caps`。
- テーブル検索、フィルタ、選択、ページング。

言語挙動:
- EN選択時、静的ラベルとプレースホルダは英語表示になります。
- 動的なステータスやサマリー文言も切り替わります。

#### 右パネル
- `Selection Summary`
- `Player Unlock Analyzer`
- `Unresolved Mapping Editor`

### 4. フィルタ
- 状態: `All`, `Selected Only`, `Unselected Only`, `With Unresolved Only`
- 条件: `All`, `With Conditions`, `Without Conditions`
- 品質: `All`, `With Quality Caps`, `Without Quality Caps`

### 5. プレイヤーアンロック解析
- share token単体を入力できます。
- `player_card_share` のURL全体を入力するとtokenを自動抽出します。
- `.ttp`（任意で`players.xml`同梱）を含むファイル/フォルダを選択し、ページ内で解析できます。
- 同じフォルダ内で複数プレイヤーを解析した場合、解析済みプレイヤー選択から切り替えできます。
- 選択対象に対して `met` / `missing` を表示します。

### 6. 未解決マッピング編集
- `unresolved_conditions` は未マッピングのソース文字列です。
- これ自体が必ずしもエラーではありません。
- 解決したいsourceのみ `mapped_to` を入力して保存してください。

### 7. スクリーンショット配置
推奨順:

1. `Unlock_Tracker_1.png` はゲーム内クイックスタート後
2. `Unlock_Tracker_2.png` はWebクイックスタート後
3. `Unlock_Tracker_3.png` はトラブルシュート前

Markdownテンプレート:

```md
### スクリーンショット01
![Unlock Tracker 01](./Unlock_Tracker_1.png)

### スクリーンショット02
![Unlock Tracker 02](./Unlock_Tracker_2.png)

### スクリーンショット03
![Unlock Tracker 03](./Unlock_Tracker_3.png)
```

### 8. 管理者向け

#### 8.1 データソース
- 主要Baseline JSON: `/root/WebSite/public_html/hugh/data/unlocktracker/unlock_baseline.json`
- 代替Baseline JSON: `/root/Release/Unlock Tracker/Config/generated/unlock_baseline.json`
- 主要Quality CSV: `/root/WebSite/public_html/hugh/data/unlocktracker/unlock_master_catalog.csv`
- 代替Quality CSV: `/root/Release/Unlock Tracker/unlock_master_catalog.csv`
- マッピング保存先: `/root/WebSite/public_html/hugh/data/unlocktracker/unresolved_mappings.json`

#### 8.2 APIエンドポイント
- `GET /hugh/api/unlocktracker_api.php?action=get_catalog`
- `GET /hugh/api/unlocktracker_api.php?action=get_mappings`
- `POST /hugh/api/unlocktracker_api.php?action=save_mappings`

#### 8.3 認証
- Viewer/APIはHughログインセッションが必要です。
- `save_mappings` はログイン保護されています。

### 9. 導入と再生成

#### 導入
1. サーバーを停止します。
2. `Mods/Unlock Tracker` として配置します。
3. サーバー起動後、クライアントを再接続します。
4. Skills UIでカテゴリ表示を確認します。

#### 再生成
ゲームXML更新時に実行します。

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py'
```

```bash
'/root/Release/Unlock Tracker/scripts/generate_unlock_tracker.py' \
  --game-config '/root/Release/SharedFiles/GameConfig/V2.5 Survival Revival Stable' \
  --mod-root '/root/Release/Unlock Tracker'
```

生成ファイル:
- `Config/progression.xml`
- `Config/items.xml`
- `Config/XUi/windows.xml`
- `Config/generated/unlock_baseline.json`

### 10. 移行サマリー
- 手動管理のperk定義を、XML生成ベースの出力に移行しました。
- Baseline生成は `progression.xml`, `items.xml`, `item_modifiers.xml`, `blocks.xml`, `recipes.xml` を使用します。
- UIパッチは安定性のため属性単位の `set` 操作へ移行しました。
- 生成XPathは厳密な `@tiered='false'` 条件を要求しません。

### 11. トラブルシュート

#### ゲーム内でカテゴリが出ない
- サーバー再起動とクライアント再接続を実施してください。
- 導入先が `Mods/Unlock Tracker` か確認してください。

#### Webカタログ読み込み失敗
- `unlock_baseline.json` のパスと権限を確認してください。
- Hughログイン状態を確認してください。

#### プレイヤー比較失敗
- tokenまたはURL形式を確認してください。
- 公開share payloadが存在することを確認してください。

#### 一部行が未解決のまま
- `Unresolved Mapping Editor` でmapping追加後、再読込してください。

### 12. サポート
- GitHub: `https://github.com/7DTD-JP/Unlock_Tracker`
- Discord: パッケージ内の`.url`を参照
