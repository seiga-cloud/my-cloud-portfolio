# AWS 3-Tier Architecture （3層構成）

## 📌 概要
AWS上で基本的な3Tierアーキテクチャを構築しました。

- Web層：ALB（Application Load Balancer）
- App層：EC2（Apache）
- DB層：RDS（MySQL）

インフラエンジニアとして重要な「ネットワーク分離」「セキュリティ設計」を意識しています。

---

## 🏗️ アーキテクチャ
![architecture](architecture/diagram.png)

---

## 🧱 使用サービス
- VPC
- EC2
- RDS（MySQL）
- ALB
- IAM
- Security Group

---

## 🔐 セキュリティ設計

### ALB
- 80番ポート：0.0.0.0/0

### EC2
- 80番ポート：ALBからのみ許可
- SSH（22）：自分のIPのみ

### RDS
- 3306：EC2からのみ許可

👉 最小権限を意識した構成

---

## ⚙️ 構築手順

### ① EC2構築＆Webサーバ

```bash
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd

echo "Hello 3Tier Architecture!" | sudo tee /var/www/html/index.html
