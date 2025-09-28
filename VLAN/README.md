# VLAN編ネットワーク演習

このフォルダは、Cisco Packet Tracerを使ったVLAN構築演習の成果です。

## 内容
- 複数VLANの設定
- PC間通信の確認
- Router-on-a-Stick構成でVLAN間ルーティング

## フォルダ構成
```
VLAN/
├─ topology.png
├─ switch-config.txt
├─ router-config.txt
├─ vlan-lab.pkt
├─ ping-results/
│   ├─ pc0_to_pc1.png
│   ├─ pc0_to_pc2_first_fail.png
│   └─ pc0_to_pc2_success.png
└─ README.md
```

### ファイル説明
- `topology.png` : ネットワークトポロジ図
- `switch-config.txt` : スイッチ設定抜粋
- `router-config.txt` : ルーター設定抜粋
- `vlan-lab.pkt` : Packet Tracer 演習ファイル
- `ping-results/` : Ping結果画像


## Ping結果

### PC0 → PC1
同じ VLAN 内の PC0 から PC1 への通信は問題なく成功しました。
![PC0→PC1 Ping成功](ping-results/pc0_to_pc1.png)

### PC0 → PC2
異なる VLAN に属する PC0 から PC2 への通信は最初の Ping がタイムアウトしました。
これは VLAN 間ルーティングがまだ ARP テーブルに反映されていなかったためだと考えられます。
2回目以降は成功し、VLAN 間通信が正しく機能していることが確認できました。
![PC0→PC2 1回目失敗](ping-results/pc0_to_pc2_first_fail.png)
![PC0→PC2 成功](ping-results/pc0_to_pc2_success.png)

