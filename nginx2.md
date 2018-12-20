```
nginx常用命令

nginx -V								版本
sudo nginx -t  						查看nginx配置文件(是nginx自带的管理命令， 可以管理nginx服务keeplive自动重启（不用每天重启）)

sudo brew services restart nginx   重启nginx
sudo nginx 							重启nginx
sudo brew services stop nginx		关闭nginx
sudo nginx -s stop					关闭nginx

ps -ef  | grep nginx 					查看进程是否在后台运行
sudo lsof -i :443 | awk '{print $2}' | tail +2 |uniq |xargs sudo kill -9     通杀所有占用443端口的服务


curl https://m2.qqhou.com
curl -v https://m2.qqhou.com 查看报文
```


```
root、alias指令用法和区别:

root的处理结果是：root路径＋location路径
alias的处理结果是：使用alias路径替换location路径



 location ^~ /partner/{
		root  /daishasha/release/html/;
}
如果一个请求的URI是/partner/index.html时,
web服务器将会返回服务器上的 /daishasha/release/html/partner/index.html


location ^~ /partner/ {
            alias /daishasha/release/html/new/;
}
如果一个请求的URI是/partner/index.html时,
web服务器将会返回服务器上的 /daishasha/release/html/new/index.html
(alias会把location后面配置的路径丢弃掉，把当前匹配到的目录指向到指定的目录。)



注意：
1. 使用alias时，目录名后面一定要加"/"。
3. alias在使用正则匹配时，必须捕捉要匹配的内容并在指定的内容处使用。
4. alias只能位于location块中。（root可以不放在location中）
```


```
location正则写法:

* 		/ 通用匹配, 如果没有其它匹配,任何请求都会匹配到
* 		=开头表示精确匹配,如 A 中只匹配根目录结尾的请求，后面不能带任何字符串。
* 		^~ 开头表示uri以某个常规字符串开头，不是正则匹配
* 		~ 开头表示区分大小写的正则匹配;
* 		~* 开头表示不区分大小写的正则匹配
*
顺序 no优先级：
(location =) > (location 完整路径) > (location ^~ 路径) > (location ~,~* 正则顺序) > (location 部分起始路径) > (/)

=精确匹配
location  = / {
  # 精确匹配 / ，主机名后面不能带任何字符串
  [ configuration A ]
}
/ 通用匹配
location  / {
  # 因为所有的地址都以 / 开头，所以这条规则将匹配到所有请求
  # 但是正则和最长字符串会优先匹配
  [ configuration B ]
}
location /documents/ {
  # 匹配任何以 /documents/ 开头的地址，匹配符合以后，还要继续往下搜索
  # 只有后面的正则表达式没有匹配到时，这一条才会采用这一条
  [ configuration C ]
}
~ 区分大小写
location ~ /documents/Abc {
  # 匹配任何以 /documents/ 开头的地址，匹配符合以后，还要继续往下搜索
  # 只有后面的正则表达式没有匹配到时，这一条才会采用这一条
  [ configuration CC ]
}
^~ 不是正则匹配
location ^~ /images/ {
  # 匹配任何以 /images/ 开头的地址，匹配符合以后，停止往下搜索正则，采用这一条。
  [ configuration D ]
}
~* 不区分大小写
location ~* \.(gif|jpg|jpeg)$ {
  # 匹配所有以 gif,jpg或jpeg 结尾的请求
  # 然而，所有请求 /images/ 下的图片会被 config D 处理，因为 ^~ 到达不了这一条正则
  [ configuration E ]
}

location /images/ {
  # 字符匹配到 /images/，继续往下，会发现 ^~ 存在
  [ configuration F ]
}

location /images/abc {
  # 最长字符匹配到 /images/abc，继续往下，会发现 ^~ 存在
  # F与G的放置顺序是没有关系的
  [ configuration G ]
}

location ~ /images/abc/ {
  # 只有去掉 config D 才有效：先最长匹配 config G 开头的地址，继续往下搜索，匹配到这一条正则，采用
    [ configuration H ]
}
```