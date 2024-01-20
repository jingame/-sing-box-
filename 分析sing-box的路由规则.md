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

`inbound` 是指 `入站标签`。  

---

`ip_version` 是指`ipv4或ipv6两种`。  

---

`auth_user`  是指`认证用户名`，参阅入站设置  

---

`protocol`  是指`探测到的协议`，参阅协议探测

---

network 是指`是计算机系统、设备或资源之间相互连接的集合`。  
>`tcp`是指`传输控制协议`。用于在计算机网络中提供可靠的、面向连接的数据传输服务。    
>`udp`是指`用户数据报协议`。它同样是互联网协议套件中的一个基本协议，用于在计算机网络中提供一种无连接、不可靠的数据传输服务。

---

`domain`是指`匹配完整域名`。  

---

`domain_suffix`  是指'匹配域名后缀'。

---

`domain_keywords`是指`匹配域名关键字`。  

---

`domain_regex`是指`匹配域名正则表达式`。

---
`geosite` 是指`匹配Geosite`。**是一个用于描述和管理特定地理位置的技术平台**  

---

`source_geoip`是`指匹配源geoip`。**是一个用于获取IP地址地理位置信息的工具或服务**

---

`geoip`是指`匹配GeoIP`,**用于确定互联网用户的地理位置信息**

---

`source_ip_cidr`是指`匹配源IP CIDR`，**用于表示一个IP地址的范围**

---

`source_ip_is_private`是指`匹配非公开源IP`，**用来判断源IP地址是否为私有IP地址的功能或标识**  

---

`ip_cidr`是指`匹配IP CIDR`，**是一种用于表示IP地址和其关联子网的方法**

---

`ip_is_private`是指`匹配非公开IP`。**是一个用来判断IP地址是否为私有IP地址的功能或标识**

---

`source_port`是指`匹配源端口`。**是指网络通信中消息发送方所使用的端口号**

---

`source_port_range`是指`匹配源端口范围`。**用于表示可接受连接或数据传输的源端口号的范围**

---

`port`是指`匹配端口`，**用于标识一台计算机上运行的特定网络服务或进程**

---

`port_range`是指`匹配端口范围`，**在网络通信和安全配置中，可以使用端口范围规定允许通过的端口号范围，以控制对特定服务或应用程序的访问**。

---

`process_name`指`匹配进程名称`，`在操作系统中正在运行的进程的名称`,比如**windows、Linux、macOS等**

---

`process_path`指`匹配进程路径`。**是在操作系统中正在运行的进程所对应的可执行文件的路径**。  

---

`package_name`指`匹配Android应用包名`。**通常是一个占位符，用于表示需要替换为实际软件包或模块的名称**

---

`user`是指`匹配用户名`。

---

`user_id`是指`匹配用户ID`  

---

`clash_mode`是`匹配Clash模式`

---

`wifi_ssid`是指`匹配WIFI SSID`.**用于表示特定 Wi-Fi 网络名称的变量或参数**

---

`wifi_bssid`是指`匹配WIFF BSSID`。**用于表示特定 Wi-Fi `接入`点的标识符的变量或参数**

---

`rule_set`是指`匹配规则集`。**和策略组的意思差不多**

---

`rule_set_ipcidr_match_source`是指`使规则集中的ipcidr规则匹配源IP`,**用于指定允许或拒绝数据包源 IP 地址与特定 IP 地址范围的匹配操作**

---

`invert`是指`反选匹配结果`。**用于表示取反操作**

---

`outbound`，是指`目标出站的标签`，`必填`。**通常用来表示从本地网络流向外部网络的数据流或传输**

---

## 逻辑字段  

type是指'类型'
>`logical`是指'逻辑算术'

---

mode是指`代特定功能、配置或操作的模式`。  `必填`
>`and`是指`表示逻辑与操作`。**用于组合两个逻辑表达式，只有当两者都为真时，整体表达式才为真**。
>`or`也是指'表示逻辑或操作'。**用于组合两个逻辑表达式，只要其中一个为真，整体表达式就为真**

---

`rules`是指`包括的规则`。`必填`


