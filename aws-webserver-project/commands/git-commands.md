# Git / GitHub コマンド

## Git初期化

```bash
git init
```

Git管理を開始する。

---

## ファイル追加

```bash
git add .
```

変更ファイルをコミット対象へ追加する。

---

## コミット

```bash
git commit -m "first commit"
```

変更内容を記録する。

---

## リモートリポジトリ登録

```bash
git remote add origin https://github.com/ユーザー名/aws-web.git
```

GitHubリポジトリと接続する。

---

## ブランチ名変更

```bash
git branch -M main
```

ブランチ名をmainへ変更する。

---

## GitHubへpush

```bash
git push -u origin main
```

ローカルファイルをGitHubへアップロードする。

---

# トラブル対応

## mainエラー

```bash
error: src refspec main does not match any
```

### 原因
commitしていない。

### 解決方法

```bash
git add .
git commit -m "first commit"
```

---

## pushエラー

```bash
failed to push some refs
```

### 解決方法

```bash
git push -f origin main
```

---

# 学んだこと

- Gitによるバージョン管理
- GitHubとの連携方法
- commit / push の基本操作
- Gitエラー対応方法
- 開発フローの基礎
