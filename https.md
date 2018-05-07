####1.终端执行：`vim req.conf`

```
[req]
distinguished_name = req_distinguished_name
x509_extensions = v3_req
prompt = no
[req_distinguished_name]
C = US
ST = VA
L = SomeCity
O = MyCompany
OU = MyDivision
CN = www.company.com
[v3_req]
keyUsage = keyEncipherment, dataEncipherment
extendedKeyUsage = serverAuth
subjectAltName = @alt_names
[alt_names]
DNS.1 = www.example.com
DNS.2 = static.example.com
DNS.3 = *.example.com
```

####2.终端执行：
```
openssl req -x509 -nodes -days 730 -newkey rsa:2048 -keyout cert.pem -out cert.pem -config req.conf -extensions 'v3_req'
```

####3.配置nginx:
```
server {
    listen       443 ssl;
    server_name www.example.com;
    ssl_certificate cert.pem;
    ssl_certificate_key cert.pem;
    root   /www/example/release/html/;
    location / {
        index  index.html index.htm;
    }
}
```

####4.重启nginx:`sudo nginx -s start`

####5.IP指向本地127.0.0.1
```
浏览器访问www.example.com，打开控制台Security-View certificate，将证书拖至桌面并双击打开，在钥匙串中将其设置为信任，即可。
```





```
原始地址生成证书：
https://alexanderzeitler.com/articles/Fixing-Chrome-missing_subjectAltName-selfsigned-cert-openssl/
```