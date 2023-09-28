# NSD + Unboundで自分向けのローカルDNSサーバーを構築する

NSDのコンテナとUnboundのコンテナを構築する。

## 環境構築

1. 環境変数
  `.env`ファイルに以下の要素を指定
    | 変数名 | 指定内容 |
    |--------|----------|
    | `DNS_INTERNAL_IPRANGE` | 内部ネットワークのIPv4アドレスの範囲(CIDR形式) |
    | `DNS_INTERNAL_GATEWAY` | 内部ネットワークのゲートウェイアドレス(IPv4) |
    | `NSD_CONTAINER_INTERNAL_IPADDRESS` | 権威DNSサーバーの内部ネットワーク内におけるIPアドレス(IPv4) |
    | `UNBOUND_CONTAINER_INTERNAL_IPADDRESS` | キャッシュDNSサーバーの内部ネットワーク内におけるIPアドレス(IPv4) |
    | `DNS_PRIMARY` | ホストLAN内におけるプライマリDNSサーバーのIPアドレス(IPv4) |
    | `DNS_SECONDARY` | ホストLAN内におけるセカンダリーDNSサーバーIPアドレス(IPv4) |
1. ゾーンファイル
  `zones`ディレクトリ以下にゾーンファイルを格納する
1. ビルド
  `docker compose build`


## コンテナの起動と実行

1. `docker compose up -d`する。


## 注意

- ゾーンファイルを追加、削除したら`docker compose build`する。
