# this is dockerfile

# 後からポート開放する方法 (dockerのコンテナに直接アクセス可能になる)
iptables -t nat -A DOCKER ! -i docker0 -p tcp -m tcp --dport 9000 -j DNAT --to-destination 172.30.0.3:9000
iptables -A DOCKER -d 172.30.0.3/32 ! -i docker0 -o docker0 -p tcp -m tcp --dport 9000 -j ACCEPT


# ホストPCからルーティングしてアクセスする方法（dockerのコンテナ直接ではなく、ホスト側にアクセスしてからdockerコンテナへアクセス）  
iptables -A PREROUTING -t nat -p tcp --dport 9000 -j DNAT --to-destination 172.30.0.3:9000
iptables -A POSTROUTING -p tcp -m tcp --dport 9000 -j SNAT --to-source 172.30.0.3 （これはなくてもアクセスできた）
