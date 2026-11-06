# 横浜市営バス 時刻表メーカー（Web版）

GitHub Pagesなどの静的ホスティングで公開できる、ビルド不要のブラウザアプリです。アプリ本体は `dist/` のみで完結します。

## GitHub Pagesでの公開

1. この `webapp` フォルダ全体を新しいGitHubリポジトリのルートに置く。
2. GitHubの **Settings → Pages** で、Source を **GitHub Actions** に設定する。
3. `main` ブランチへpushすると、同梱の `.github/workflows/deploy-pages.yml` が `dist/` を公開する。Actionsの完了画面に公開URLが表示される。

手早く公開する場合は、GitHubで空のリポジトリを作ってから次を実行します（`YOUR_ACCOUNT` は自分のアカウント名）。

```bash
git init
git add .
git commit -m "Add Yokohama bus timetable web app"
git branch -M main
git remote add origin https://github.com/YOUR_ACCOUNT/yokohama-bus-timetable.git
git push -u origin main
```

公開リポジトリにAPIキーをコミットしないでください。キーはサイト訪問者のブラウザのLocal Storageにのみ保存します。公式データの直接取得はCORS設定により失敗する場合があるため、公式からダウンロードしたZIPの手動読込も常に利用できます。

公式データ: https://ckan.odpt.org/dataset/yokohama_municipal_bus
