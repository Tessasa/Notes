###登陆机制：

```
页面：https://www.company.com#0（#0在这里作用是标记当前页面的tab选项卡所处的位置）

跳转登陆地址：https://passport.company.com/redir_url=https://www.company.com#0

登陆成功回跳（带有成功的token参数）：此时的回跳地址已经不再是https://www.company.com#0
https://www.company.com?access_token=example123#0
```

###注意：
```
#0这个已经和返回的参数融为一体，
这样会导致：
1.回跳地址不带有#0标记，就不会知道当前选项卡所处的位置，可能展示默认位置
2.登陆这块的token，会存储在本地缓存中，而#0会作为参数一部分存在本地，导致在获取token的时候，控制台语法错误提示；
例如：在vue中，会提示：[Vue warn]:Error in c created hook:"SyntacError:Unexpected token Ѐ in JSON an position 110"
同时，此时页面登陆机制问题阻塞渲染，导致页面白屏，并不会抛出错误提示

```

