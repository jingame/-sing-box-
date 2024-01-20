## 结构()
```
{
  "route": {
    "rules": [
      {
        "inbound": [
          "mixed-in"
        ],
        "ip_version": 6,
        "network": [
          "tcp"
        ],
        "auth_user": [
          "usera",
          "userb"
        ],
        "protocol": [
          "tls",
          "http",
          "quic"
        ],
        "domain": [
          "test.com"
        ],
        "domain_suffix": [
          ".cn"
        ],
        "domain_keyword": [
          "test"
        ],
        "domain_regex": [
          "^stun\\..+"
        ],
        "geosite": [
          "cn"
        ],
        "source_geoip": [
          "private"
        ],
        "geoip": [
          "cn"
        ],
        "source_ip_cidr": [
          "10.0.0.0/24"
        ],
        "source_ip_is_private": false,
        "ip_cidr": [
          "10.0.0.0/24"
        ],
        "ip_is_private": false,
        "source_port": [
          12345
        ],
        "source_port_range": [
          "1000:2000",
          ":3000",
          "4000:"
        ],
        "port": [
          80,
          443
        ],
        "port_range": [
          "1000:2000",
          ":3000",
          "4000:"
        ],
        "process_name": [
          "curl"
        ],
        "process_path": [
          "/usr/bin/curl"
        ],
        "package_name": [
          "com.termux"
        ],
        "user": [
          "sekai"
        ],
        "user_id": [
          1000
        ],
        "clash_mode": "direct",
        "wifi_ssid": [
          "My WIFI"
        ],
        "wifi_bssid": [
          "00:00:00:00:00:00"
        ],
        "rule_set": [
          "geoip-cn",
          "geosite-cn"
        ],
        "invert": false,
        "outbound": "direct"
      },
      {
        "type": "logical",
        "mode": "and",
        "rules": [],
        "invert": false,
        "outbound": "direct"
      }
    ]
  }
}
```

---
<br>

## 默认字段(Default Fields)

```
(domain || domain_suffix || domain_keyword || domain_regex || geosite || geoip || ip_cidr || ip_is_private) &&

(port || port_range) &&

(source_geoip || source_ip_cidr || source_ip_is_private) &&

(source_port || source_port_range) &&

other fields

另外，引用的规则集可视为被合并，而不是作为一个单独的规则子项。
```

---

<br>

inbound 是指 `入站标签`。  

---

ip_version 是指`ipv4或ipv6两种`。  

---

auth_user  是指`认证用户名`，参阅入站设置  

---

protocol  是指`探测到的协议`，参阅协议探测

---

network 是指`是计算机系统、设备或资源之间相互连接的集合`。  
>tcp是指`传输控制协议`。用于在计算机网络中提供可靠的、面向连接的数据传输服务。    
>udp是指`用户数据报协议`。它同样是互联网协议套件中的一个基本协议，用于在计算机网络中提供一种无连接、不可靠的数据传输服务。

---

domain是指`匹配完整域名`。  

---

domain_suffix  是指'匹配域名后缀'。

---

domain_keywords是指`匹配域名关键字`。  

---

domain_regex是指`匹配域名正则表达式`。

