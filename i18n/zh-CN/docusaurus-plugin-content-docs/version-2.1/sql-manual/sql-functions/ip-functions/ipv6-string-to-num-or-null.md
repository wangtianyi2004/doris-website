---
{
"title": "IPV6_STRING_TO_NUM_OR_NULL",
"language": "zh-CN"
}
---

<!-- 
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at
  http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

## IPV6_STRING_TO_NUM_OR_NULL

IPV6_STRING_TO_NUM_OR_NULL

## 描述

## 语法

`VARCHAR IPV6_STRING_TO_NUM_OR_NULL(VARCHAR ipv6_string)`

`VARCHAR INET6_ATON(VARCHAR ipv6_string)`

IPv6NumToString 的反向函数，它接受一个 IP 地址字符串并返回二进制格式的 IPv6 地址。
如果输入字符串包含有效的 IPv4 地址，则返回其等效的 IPv6 地址。

### 注意事项

如果输入非法的 IP 地址，会返回 `NULL`。该函数有一个别名为 `INET6_ATON`。

## 举例
```sql
mysql> select hex(ipv6_string_to_num_or_null('1111::ffff'));
+-----------------------------------------------+
| hex(ipv6_string_to_num_or_null('1111::ffff')) |
+-----------------------------------------------+
| 1111000000000000000000000000FFFF              |
+-----------------------------------------------+
1 row in set (0.01 sec)

mysql> select hex(ipv6_string_to_num_or_null('192.168.0.1'));
+------------------------------------------------+
| hex(ipv6_string_to_num_or_null('192.168.0.1')) |
+------------------------------------------------+
| 00000000000000000000FFFFC0A80001               |
+------------------------------------------------+
1 row in set (0.02 sec)

mysql> select hex(ipv6_string_to_num_or_null('notaaddress'));
+------------------------------------------------+
| hex(ipv6_string_to_num_or_null('notaaddress')) |
+------------------------------------------------+
| NULL                                           |
+------------------------------------------------+
1 row in set (0.02 sec)
```

### Keywords

IPV6_STRING_TO_NUM_OR_NULL, INET6_ATON, IP