# Save the Cat Board — PWA

## ファイル構成
```
stc-board-pwa/
  index.html      ← メインアプリ
  manifest.json   ← PWA設定
  sw.js           ← Service Worker（オフライン対応）
  serve.py        ← ローカルサーバー起動スクリプト
```

## 使い方

### PCの場合

1. フォルダを展開する
2. `serve.py` をダブルクリック（Pythonが必要）
   - または、フォルダ内でターミナルを開いて:
   ```
   python3 -m http.server 8080
   ```
3. ブラウザで `http://localhost:8080` を開く
4. アドレスバーの「インストール」ボタンでアプリ化できる

### Androidの場合

**方法A: PCからサーブしてスマホで開く**
1. PCで上記のサーバーを起動
2. 同じWi-Fiに接続したスマホのブラウザで `http://PCのIPアドレス:8080` を開く
3. メニュー →「ホーム画面に追加」

**方法B: Androidに直接置く**
1. フォルダごとAndroidにコピー
2. 「Simple HTTP Server」などのアプリをインストール
3. フォルダを指定してサーバー起動
4. `http://localhost:ポート番号` を開く
5. 「ホーム画面に追加」

**方法C: 最も簡単（サーバー不要、PWAなし）**
1. `index.html` だけをAndroidにコピー
2. ブラウザで直接開く
3. Service Workerは動かないがアプリ自体は完全に使える

### iPhoneの場合
- PC方法Aと同じ手順でSafariで開く →「ホーム画面に追加」

## 注意
- Service Worker（オフライン対応）はHTTPSまたは localhost でのみ動作します
- `index.html` を直接開いた場合、アプリとしては動きますがPWA機能（ホーム画面追加、オフライン）は使えません
- データはJSONファイルで保存/読込します
