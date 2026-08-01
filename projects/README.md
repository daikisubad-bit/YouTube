# projects/

動画1本ごとの進行ファイルを置く場所。`.claude/skills/youtube-video-production/templates/video_project_template.md`
をコピーして、`projects/<動画のスラッグ>.md` として保存する。

`index.json` は `dashboard/index.html`（進行ボード）が表示するための要約データ。動画プロジェクトを作成・更新したら、
このファイルにも反映してから `dashboard/index.html` を再publishする。

## index.json のスキーマ

```json
[
  {
    "id": "video-slug",
    "title": "動画テーマ名",
    "stage": 0,
    "stageLabel": "0. チャンネル基盤",
    "status": "一言ステータス（例：企画3案を検討中）",
    "nextAction": "次にやること",
    "updatedAt": "2026-08-01",
    "file": "projects/video-slug.md",
    "active": true
  }
]
```

- `stage` は 0〜6（0:基盤 / 1:リサーチ / 2:企画 / 3:タイトル・サムネ / 4:差別化 / 5:台本 / 6:公開後）。
- `active` は直近のセッションで触っていた動画に `true` を付ける（進行ボード側でハイライトするため）。同時に複数
  `true` にしない。
