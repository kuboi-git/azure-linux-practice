# Azure Linux Practice

### 20260516
## 構成
- Azure Resource Group
- VNet
- Subnet
- NSG
- Ubuntu VM
- nginx

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
NSG設定でHTTP通信できず、
Inbound rule を追加して解決。

<img width="632" height="160" alt="HelloAzure" src="https://github.com/user-attachments/assets/13112b81-b8e7-4e72-8e29-0694e021f6f1" />


