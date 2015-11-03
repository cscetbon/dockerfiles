# 
# docker run --cap-add=NET_ADMIN --device /dev/net/tun -h openvpn --name openvpn -it openvpn
# 
# then from another container just use --net=container:openvpn
# 
# remember to add 
#  up /etc/openvpn/update-resolv-conf
#  down /etc/openvpn/update-resolv-conf
#
#  to your openvpn conf file!

FROM ubuntu:14.04

RUN apt-get update -q
RUN apt-get install -qy openvpn iptables

ADD update-resolv-conf /etc/openvpn/update-resolv-conf

ENTRYPOINT ["openvpn"]
WORKDIR /etc/openvpn