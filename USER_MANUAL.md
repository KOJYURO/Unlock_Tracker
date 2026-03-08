# Unlock Tracker User Manual

Last Updated: 2026-03-09  
Version: Unlock Tracker v1.1.1  

## EN

### 0. Documentation Policy
- Canonical docs are merged in this directory with the minimum file set.
- GitHub docs are limited to `README.md` and `USER_MANUAL.md`.

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

## JA

### 0. ドキュメント方針
- 正規ドキュメントは、このディレクトリに最小ファイル数で統合管理します。
- GitHub向け文書は `README.md` と `USER_MANUAL.md` に限定します。

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


### 12. サポート
- GitHub: `https://github.com/7DTD-JP/Unlock_Tracker`
- Discord: パッケージ内の`.url`を参照
