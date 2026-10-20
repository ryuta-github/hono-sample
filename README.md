# Hono + TypeScript サンプル

Node.js 上で動く、学習用のシンプルな Web API です。

## 必要なもの

- Node.js 22 以上（推奨: Node.js 24 LTS）
- npm

## インストールと開発サーバーの起動

リポジトリのルートで実行します。

```sh
npm ci
npm run dev
```

ポート 3000 で起動します。ソースの変更時に自動で再起動します。
停止するには `Ctrl+C` を押してください。

別のターミナルから確認できます。

```sh
curl -i http://localhost:3000/hello
```

HTTP 200、Content-Type `application/json` と次の JSON を返します。

```json
{"message":"hello hono"}
```

## 型チェックとビルド

```sh
npm run typecheck
npm run build
npm start
```

`npm run build` は TypeScript を `dist/` に出力し、`npm start` はビルド済みの JavaScript を起動します。
開発サーバーと同時には起動せず、先に使用中のサーバーを停止してください。

## ファイル構成

- `src/index.ts`: Hono のルート定義と Node.js サーバーの起動
- `tsconfig.json`: TypeScript のコンパイル設定
- `package.json`: 依存関係と npm コマンド
- `package-lock.json`: 再現可能な依存関係のバージョン
- `.gitignore`: 依存関係、ビルド成果物、環境変数ファイルを Git 管理から除外

## GitHub への反映

変更を確認してからコミット・プッシュします。空のリポジトリへの初回反映例です。

```sh
git add .gitignore README.md package.json package-lock.json tsconfig.json src/index.ts
git commit -m "Add Hono TypeScript hello API"
git branch -M main
git push -u origin main
```

`node_modules/` と `dist/` はコミット不要です。
