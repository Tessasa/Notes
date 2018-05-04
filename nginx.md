```
server {
    listen       443 ssl;
    server_name  www.qfund.me;

    ssl on;
    ssl_certificate      /usr/local/etc/nginx/pem/Qfund58/www.qfund/server.crt;
    ssl_certificate_key  /usr/local/etc/nginx/pem/Qfund58/www.qfund/server.key;

    # ssl_session_cache    shared:SSL:1m;
    # ssl_session_timeout  5m;

    # ssl_ciphers  HIGH:!aNULL:!MD5;
    # ssl_prefer_server_ciphers  on;

    root   /www/qingsongchou/qsc_international/qfund_h5/release/html/;
    location / {
        index  index.html index.htm;
    }
}
```

```
    listen       443 ssl;
    server_name static.qfund.me;

    ssl on;
    ssl_certificate      /usr/local/etc/nginx/pems/www.qfund/server.crt;
    ssl_certificate_key  /usr/local/etc/nginx/pems/www.qfund/server.key;

    # ssl_session_cache    shared:SSL:1m;
    # ssl_session_timeout  5m;

    # ssl_ciphers  HIGH:!aNULL:!MD5;
    # ssl_prefer_server_ciphers  on;

    root   /Users/daishasha/Work/release/;
    # location / {
    #    index  index.html index.htm;
    #}
    location ~* \.(eot|ttf|woff|svg|otf)$ {
           add_header Access-Control-Allow-Origin *;
     }
}
```

```
server{
        listen   80;
        server_name  daishasha.com;

        root /www/study/;
        location / {
          index  index.html index.htm;
        }
}
```

```
*同一域名不同路径：

server {
    listen       443 ssl;
    server_name  www.qfund.me;

    ssl on;
    ssl_certificate      /usr/local/etc/nginx/pems/www.qfund/server.crt;
    ssl_certificate_key  /usr/local/etc/nginx/pems/www.qfund/server.key;

    root   /Users/daishasha/qsc/qfund_h5/release/html/;
    location / {
        index  index.html index.htm;
    }
    location ^~ /partner/ {
        alias /Users/daishasha/qsc/qfund_tob/release/html/;
    }
        location ^~ /manage/public/ {
        alias /Users/daishasha/qsc/outwork_simple/release/public/;
    }
```

```
*跨域问题

 location / {
         add_header 'Access-Control-Allow-Origin' 'vue.qfund.me:8080';
         index  index.html index.htm;
 }


location ~* \.(eot|ttf|woff|svg|otf)$ {
                   add_header Access-Control-Allow-Origin *;
}
```

```
location /project/index {
    try_files $uri @rewrite;
}
location @rewrite {
    rewrite ^/project/index/(.*) /detail.html?projuuid=$1;
}
```

```
location /v8/main {
    alias   /Users/daishasha/qsc/qschou-h5/static/html/v8/main/;
    try_files $uri $uri/ /v8/main/;
    index  index.html index.htm haha.html;

}
location /v8/my {
    alias   /Users/daishasha/qsc/qschou-h5/static/html/v8/my/;
    try_files $uri $uri/ /v8/my/;
    index  index.html index.htm haha.html;

}
location /v8/lovevalue {
    alias   /Users/daishasha/qsc/qschou-h5/static/html/v8/lovevalue/;
    try_files $uri $uri/ /v8/lovevalue/;
    index  index.html index.htm haha.html;
}
```

```
location /js/v8/ {
    alias   /Users/daishasha/qsc/qschou-h5/static/js/v8/;
    index  index.html index.htm haha.html;
}

location /css/v8/ {
    alias   /Users/daishasha/qsc/qschou-h5/static/css/v8/;
    index  index.html index.htm haha.html;
}

location /img/v8/ {
    alias   /Users/daishasha/qsc/qschou-h5/static/img/v8/;
    index  index.html index.htm haha.html;
}
```