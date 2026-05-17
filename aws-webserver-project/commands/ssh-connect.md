# SSH 接続コマンド

## キーファイル権限変更

```bash
chmod 400 my-key.pem
```

秘密鍵の権限を変更する。

SSHでは適切な権限設定が必要。

---

## EC2へSSH接続

```bash
ssh -i "my-key.pem" ec2-user@13.211.142.27
```

EC2インスタンスへリモート接続する。

---

# Security Group 設定

## SSH

- ポート：22
- 自分のIPアドレスのみ許可

## HTTP

- ポート：80
- 0.0.0.0/0

---

# 学んだこと

- SSHによるリモート接続
- 秘密鍵の権限管理
- Security Groupによるアクセス制御
- Linuxサーバへの接続方法
- AWSネットワーク基礎
