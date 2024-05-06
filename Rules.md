# Rules

### Basic grammar 基本语法

```yaml
[Rule-Type], [Argument], [Policy]
```

### Rule Type

1. 域名类型
    1. 域名：DOMAIN，参数填写全域名
    2. 域名后缀：DOMAIN-SUFFIX：参数填写域名后缀
    3. 域名关键字：DOMAIN-KEYWORD：参数填写单词
2. IP类型
    1. 国家代码IP：GEOIP，参数参考[GeoLite2](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)。
    2. IPv4地址：IP-CIDR，参数填写IPv4地址，如`IP-CIDR,127.0.0.0/8,DIRECT,no-resolve`，no-solve表示不通过DNS解析。
    3. IPv6地址：IPCIDR6，参数填写IPv6地址
    4. 源IP地址：SRC-IP-CIDR，参数填写IPv4地址
3. 端口类型
    1. 源端口：SRC-PORT，参数填写端口号
    2. 目标端口：DST-PORT，参数填写端口号
4. 应用类型
    1. 进程名称：PROCESS-NAME，参数填写进程名
    2. 进程路径：PROCESS-PATH，参数填写进程路径
5. 其他：
    1. IP集合：IPSET
    2. 规则集合：RULE-SET
    3. 脚本：SCRIPT
    4. 全匹配：MATCH，无参数，必需有的规则，通常放在最后一条，`MATCH,policy`



### Policy

1. DIRECT：直连
2. REJECT：拒绝
3. Proxy：路由到代理
4. Proxy Group：路由到代理组