###ref

```
<div class="detail-wrapper" @click="detail" ref="detail" v-show="isShow">
                <div class="detail">详情>></div>
            </div>
```
```
detail(e){
                this.isShow = false;
                this.text = this._text;
            }
```