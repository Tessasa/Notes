```
复制至粘贴板：

JS实现各种复制到剪贴板:
http://www.cnblogs.com/huijieoo/articles/5569990.html
Javascript中document.execCommand()的用法：
http://blog.csdn.net/woshinia/article/details/18664903
```

```
<textarea cols="20" rows="10" id="biao1">用户定义的代码区域</textarea>
<input type="button" value="点击复制代码"  id="biao_input"/>
```

```
$('body').on('click', '#biao1', function () {
    copyUrl2();

    return false;
});


该事件仅适用于<input type="text">和<textarea>文本框
function copyUrl2() {
    var Url2 = document.getElementById("biao1");
    Url2.select(); // 选择对象
    document.execCommand("Copy"); // 执行浏览器复制命令
    utils.alertMessage("已复制好，可贴粘。");
}
```