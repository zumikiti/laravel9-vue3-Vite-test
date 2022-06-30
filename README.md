## about

Taylor のツイートで Vite が初期インストールで採用されたと見たので、やってみた。

https://twitter.com/taylorotwell/status/1541795873838989314?s=20&t=DnD7hqFETNqHOVSWnEJZBg

- Laravel9
- inertia.js
- Tailwind CSS
- Vue3
- Laravel Vite

の初期設定環境

なお、 `npm run dev` をコンテナ内で実行するように設定しています。


## using
### webdev の設定
db 等のコンテナを複数プロジェクトで共通化するため、 webdev の設定を使用しています。

https://github.com/zumikiti/webdev

### Taskfile をエイリアスに設定する（任意）
```
alias task="./Taskfile"
```

### .env の作成
```
cp .env.example .env
```

### コンテナの起動
```
task up
```

### 初期実行コマンド
```
task composer i
task artisan key:generate
task artisan migrate

task npm ci
```

### vite の起動
```
task dev
```

vite 起動時のポートが他と競合してしまう場合は、 `.env` の `VITE_PORT` を変更

http://localhost:8080
