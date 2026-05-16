# Azure Linux Practice

### 20260516

## 構築手順
1. Resource Group作成
2. Virtual Network作成
3. NSG設定
4. Ubuntu VM作成
5. SSH接続
6. nginxインストール
7. HTML編集

## 実施内容
- SSH接続
- nginxインストール
- nginx構築
- HTML公開

## 学んだこと
- Azure無料枠の注意点
- Private Endpointは課金対象になりやすい（実際に設定してみたが、これ毎日課金されるとなると結構高いな、、、やめよ）
- VM停止の重要性

## 苦戦した点
- NSG設定でHTTP通信できず、
- Inbound rule を追加して解決。

## 動作確認
- nginx Web Server
<img width="632" height="160" alt="HelloAzure" src="https://github.com/user-attachments/assets/13112b81-b8e7-4e72-8e29-0694e021f6f1" />


