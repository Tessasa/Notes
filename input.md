
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
type="number",最大字数的限制是没有用的

在移动设备上，input[type=tel] 是支持maxlength的，而且只能输入数字键盘。
```