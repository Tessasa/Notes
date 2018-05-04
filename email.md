`
邮箱验证
`

```
//判断邮箱是否为空
if ($('.donation-email input').val().trim() == '') {
    utils.alertMessage('Please enter your email');
    return false;
}
```

```
//验证邮箱是否有效
    var EMAIL = /([\w-\.]+)@((?:[\w]+\.)+)([a-zA-Z]{2,4})/;
    if (EMAIL.test($('.donation-email input').val()) == false) {
        utils.alertMessage('Please enter a valid email');
        return false;
    }
```