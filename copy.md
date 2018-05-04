
```
	var urlObj = document.getElementsByClassName(className)[0];
    urlObj.select(); // 选择对象
    document.execCommand("Copy"); // 执行浏览器复制命令
    obj.alertMessage("Copied to clipboard");
```

```
    var targetElement=document.getElementById("QRCode");
    targetElement.select();
    document.execCommand("Copy");
    utils.alertMessage("复制成功");
```