# this is dockerfile

# 後からポート開放する方法  
iptables -t nat -A DOCKER ! -i docker0 -p tcp -m tcp --dport 6006 -j DNAT --to-destination 172.17.0.2:6006
