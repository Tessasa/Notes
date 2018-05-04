
### `Input 强制输入正整数`

```
<input type="text" id="money" class="text-validate" pattern="[1-9][0-9]{0,6}" maxlength="7" name="money" onkeyup="this.value=this.value.replace(/\D/g,'')" autocapitalize="off" autocorrect="off" onafterpaste="this.value=this.value.replace(/\D/g,'')" placeholder="请输入目标金额">
```


```
    function intInput(id) {
        var item = document.querySelector(id);

        console.log(item);
        item.onkeyup = forceInt;
        item.onafterpaste = forceInt;

        function forceInt() {
            this.value = this.value.replace(/[^0-9]+/, '').replace(/^0+/, '');
        }
    }
```
