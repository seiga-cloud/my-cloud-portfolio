# 🔧 Troubleshooting（トラブルシューティング）

このプロジェクト構築時に発生した問題と解決方法をまとめる。

---

## ❌ SSH接続エラー（Permission denied）

### エラー内容

Permission denied (publickey,gssapi-keyex,gssapi-with-mic)


### 原因
- 秘密鍵（.pem）のパスが間違っていた
- ファイル名が `3tier-key.pem.pem` になっていた

### 解決方法
```bash
chmod 400 3tier-key.pem
ssh -i 3tier-key.pem ec2-user@<IP>
学び
ファイル名と拡張子は必ず確認する
SSH接続エラーはまず鍵を疑う
❌ ファイルが見つからない（No such file）
エラー内容
No such file or directory
原因
Git Bashでのパス指定ミス
/c/Users/... を使っていなかった
解決方法
cd /c/Users/user/Downloads
学び
Windows + Git Bashはパス形式が異なる
❌ EC2にアクセスできない
原因
セキュリティグループで22番ポート未開放
自分のIPが許可されていなかった
解決方法
セキュリティグループ設定
22番ポート
自分のIPを許可
学び
AWSは「ネットワーク設定」が最重要
❌ Webページが表示されない
原因
Apacheが起動していなかった
80番ポートが閉じていた
解決方法
sudo systemctl start httpd
sudo systemctl enable httpd
学び
サービス起動確認は基本
❌ ALB経由でアクセスできない
原因
ターゲットグループのヘルスチェック失敗
セキュリティグループ設定ミス
解決方法
ヘルスチェックパスを / に設定
EC2のセキュリティグループにALBのセキュリティグループを許可
学び
ALBは「ヘルスチェック」が超重要
❌ RDS接続できない
原因
RDSがプライベートで外部からアクセスできない
セキュリティグループ未設定
解決方法
EC2からの3306ポートを許可
同じVPC内に配置
学び
データベースは外部公開しないのが基本
💡 まとめ

トラブルの多くは以下に集約される：

パスミス
セキュリティグループ設定
サービス未起動

👉 インフラは「設定ミスとの戦い」であると理解した


---

# ✅ 使い方（超重要）

① GitHubで  
→ `docs/troubleshooting.md` を作る  

② 上の内容を**そのまま貼る**

③ Commit

---

# 💡 さらに評価上げる方法

👉 できればこれ追加👇

- 実際のエラー画面スクショ
- 自分の言葉を1行追加

例👇
```markdown
※実際に何度もSSH接続で失敗し、原因特定に時間がかかった
