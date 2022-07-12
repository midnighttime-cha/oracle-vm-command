# คำสั่งพื้นฐานใน Oracle VM

## การจัดการ Firewall
การ Allow Port พื้นฐานก่อนทำการติดตั้ง
```sh
iptables -A INPUT -m state --state NEW -m tcp -p tcp --dport 7002 -j ACCEPT
iptables -A INPUT -m state --state NEW -m udp -p udp --dport 123 -j ACCEPT 
iptables -A INPUT -m state --state NEW -m tcp -p tcp --dport 54322 -j ACCEPT
```

เมื่อแก้ไข Port เรียบร้อยให้ทำการ Save รายการ Firewall ที่แก้ไขด้วยคำสั่งต่อไปนี้
```sh
service iptables save
```
