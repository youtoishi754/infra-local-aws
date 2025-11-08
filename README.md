# infra-local-aws

このリポジトリは、**ローカル環境で AWS を模した構成に PHP アプリをデプロイして Hello World を表示する**ためのサンプルです。  
本構成は **Terraform + LocalStack + Docker** を使用しています。

## 構成概要

1. **Docker**  
   - PHP アプリ用コンテナ
   - LocalStack 用コンテナ（AWS の模倣）

2. **LocalStack**  
   - S3, EC2, Lambda などの AWS サービスをローカルで再現
   - Terraform で構築したリソースをここに適用可能

3. **Terraform**  
   - インフラのコード化
   - LocalStack 上にリソース作成（S3 バケットなど）

4. **PHP アプリ**  
   - `Hello World` を表示するシンプルな Web アプリ

## 動作手順（簡易）

```bash
# Docker コンテナ起動
docker-compose up -d

# Terraform 適用
terraform init
terraform apply

# ブラウザでアクセス
http://localhost:8080
