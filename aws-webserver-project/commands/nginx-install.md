# nginx インストール・操作コマンド

## nginx インストール

```bash
sudo dnf install nginx -y
```

nginx Webサーバをインストールする。

---

## nginx 起動

```bash
sudo systemctl start nginx
```

nginxサービスを起動する。

---

## nginx 自動起動設定

```bash
sudo systemctl enable nginx
```

EC2再起動後も自動でnginxを起動する設定。

---

## nginx 状態確認

```bash
sudo systemctl status nginx
```

nginxサービスの状態を確認する。

---

## nginx 再起動

```bash
sudo systemctl restart nginx
```

HTML編集後などに設定を反映する。

---

## nginx 停止

```bash
sudo systemctl stop nginx
```

nginxサービスを停止する。

---

## HTML配置場所

```bash
/usr/share/nginx/html/
```

nginxで公開されるHTMLファイル配置ディレクトリ。

---

## index.html 編集

```bash
sudo vi /usr/share/nginx/html/index.html
```

公開ページを編集する。

---

## ポート確認

```bash
sudo ss -tuln
```

現在使用中のポートを確認する。

---

# 学んだこと

- nginxインストール方法
- Linux上でのWebサーバ運用
- systemctlによるサービス管理
- Web公開ディレクトリ構成
- HTML編集からWeb公開までの流れ
