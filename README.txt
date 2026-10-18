SENSUS v0.6 — AI対話試作

1. GitHub Pages: index.html, icon.svg, manifest.webmanifest をリポジトリのルートにアップロード。
2. Cloudflare: CLOSET MIXとは別の Worker を作り、worker.js を貼り付けて Deploy。
3. Worker Settings > Bindings > Workers AI で変数名 AI を設定。
4. Worker Settings > Variables: ALLOWED_ORIGIN に https://maruko0525.github.io を設定（末尾スラッシュなし）。
5. 任意: MODEL_CHOICE に llama または qwen を指定。初期値 llama。モデル提供状況はCloudflareのモデル一覧で確認。
6. Worker の /health にアクセスして model と aiBinding:true を確認。
7. SENSUS > 設定 > Worker URL に https://...workers.dev を入力し保存・接続テスト。
8. AI対話タブで自由対話、出来事別、人生全体を選んで会話。

注意：プロトタイプにはログインやアクセス制御がなく、CORSは認証ではありません。Worker URLが知られると第三者がAPIを呼べる可能性があります。レート制限・認証・費用上限を設定するまで公開運用しないでください。実在する相談者の情報や機微な個人情報は入力しないでください。端末保存の会話はJSONバックアップに含まれます。
