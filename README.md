# this is dockerfile

# 後からポート開放する方法 (ホスト　→　コンテナ経由となる)
iptables -t nat -A DOCKER ! -i docker0 -p tcp -m tcp --dport 9000 -j DNAT --to-destination 172.30.0.3:9000
iptables -A DOCKER -d 172.30.0.3/32 ! -i docker0 -o docker0 -p tcp -m tcp --dport 9000 -j ACCEPT


# これはなんだろう？
iptables -A PREROUTING -t nat -p tcp --dport 9000 -j DNAT --to-destination 172.30.0.3:9000
iptables -A POSTROUTING -p tcp -m tcp --dport 9000 -j SNAT --to-source 172.30.0.3 
