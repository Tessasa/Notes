
### `Input 强制输入正整数`

```
<input
        type="tell"
        class="count-number"
        pattern="[1-9][0-9]{0,6}"
        maxlength="5"
        name="money"
        autocapitalize="off"
        autocorrect="off"
        onkeyup="this.value=this.value.replace(/^[0]+|[^0-9]/g,'')"
        onafterpaste="this.value=this.value.replace(/^[0]+|[^0-9]/g,'')"
        v-model='countNumber'>
```

```
input[type=tel],
在移动设备上，是支持maxlength的，而且只能输入数字键盘。

当input[type=number]时，
输入的如果是数字，则maxlength有效，输入的不为数字而是字母或者汉字，则maxlength无效，

当input[type=text]时，此时设置的maxlength只对字母或者汉字有效，对数字无效.
```