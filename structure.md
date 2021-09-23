# 使用サービス
使用サービスは、中継サーバーや認証に使っているサービス等のリストです。<br>
使っているサービスはすべてここにリストアップされています。

## Python(Quart)
PythonライブラリであるQuartで作成されたWebサーバーです。<br>
100%完全にPythonで作成されているサーバーです。

## Nginx(Reverse Proxy)
HTTPS化のためにNginxをリバースプロキシとして利用しています。<br>
NginxにSSLやCloudflareの設定があります。

## Cloudflare(Free)
DDoS対策(OriginIPバレ防止)のため、Cloudflareを挟んでいます。<br>
SSL化の一部もこのCloudflareを使用しているため、非常に重要なサービスです。

## Freenom.com(TkDomain)
.tkのドメインを取得するためにFreenomというドメインサービスを利用しています。

# アクセス
どのような順番でアクセスしているかを確認します。

## アクセス(Authorization Server)
Web(クライアント) => Cloudflare(中継Proxyサーバー) => Nginx(ローカルProxyサーバー) => Python(Quart)

## アクセス(OAuth2)
Web(クライアント) => Cloudflare(中継Proxyサーバー) => DiscordAPI(OAuth2 API)

## GET(Authorization Server)
Python(Quart) => Nginx(ローカルProxyサーバー) => Cloudflare(中継Proxyサーバー) => PC(クライアント)

# 注意
これらの情報は100%正しいとは限りません。<br>
例えば、DiscordがCloudflareを使わなくなった場合や私がNginxから別のサーバーに変える可能性があります。<br>
ほかにも、Pythonサーバーから乗り移った場合等もあります。
