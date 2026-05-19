# Azure Linux Practice

# 1. 概要
Azure上にLinux VMを構築し、SSH接続・nginx公開・NSG設定を実施しました。

Linux VM上でnginxを構築し、ブラウザからWebページへアクセスできることを確認しました。

---

# 2. 構成図
```text
Resource Group
└─ rg-test-01
    │
    └─ Virtual Network
       └─ vnet-Linux-01 (10.0.0.0/16)
          │
          └─ Subnet
             └─ subnet-web-01 (10.0.10.0/24)
                │
                ├─ NSG
                │  ├─ allow-ssh (22)
                │  └─ allow-http (80)
                │
                └─ Ubuntu VM
                   └─ vm-linux-01
                      ├─ Public IP
                      └─ nginx
```

---

# 3. 使用サービス
| サービス | 用途 |
|---|---|
| Resource Group | リソース管理 |
| Virtual Network | 仮想ネットワーク |
| Subnet | ネットワーク分離 |
| NSG | 通信制御 |
| Ubuntu VM | Linuxサーバ |
| Public IP | 外部接続 |
| nginx | Webサーバ |

---

# 4. 作成順序
1. Resource Group作成
2. Virtual Network作成
3. Subnet作成
4. NSG作成
5. Ubuntu VM作成
6. SSH接続
7. nginxインストール
8. HTML編集
9. ブラウザアクセス確認

---

# 5. 動作確認
## SSH接続

```bash
ssh -i vm-key.pem azureuser@PublicIP
```

SSH接続できることを確認。

---

## nginxインストール

```bash
sudo apt update
sudo apt install nginx -y
```

---

## Web公開確認

ブラウザからVMのPublic IPへアクセスし、nginxの「Hello Azure」が表示されることを確認。
<img width="632" height="160" alt="HelloAzure" src="https://github.com/user-attachments/assets/68d29a5a-346b-4bb3-a9d0-536d434a9b7b" />

---

# 6. 苦戦したこと
## HTTP通信できなかった

### 原因
NSGのInbound Ruleが未設定だった。

### 解決方法
HTTP(80)許可ルールを追加し解決。

---

## SSH接続できなかった

### 原因
.pemファイル配置ミス。

### 解決方法
PowerShellの実行ディレクトリを修正し解決。

---

# 7. 学んだこと
- Azure VMの基本構築
- SSH接続方法
- Linux基本コマンド
- nginxインストール
- NSGによる通信制御
- Public IPによる外部公開
- Azure従量課金の考え方
- VM停止（割り当て解除）の重要性
