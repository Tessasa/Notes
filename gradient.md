### `竖形进度条渐变：`

```
 .popular-project-progress {
    position: absolute;
    top: 0;
    left: -8px;
    width: 8px;
    background: #EAECEE;
    border-radius: 2px;
    padding-top: 1px;
    height: 100%;

    //旋转
    transform: rotate(180deg);
    -ms-transform: rotate(180deg); /* IE 9 */
    -moz-transform: rotate(180deg); /* Firefox */
    -webkit-transform: rotate(180deg); /* Safari 和 Chrome */
    -o-transform: rotate(180deg); /* Opera */
    .popular-project-bar {
        max-height: 100%;
        width: 8px;
        border-radius: 10px;

        //渐变色
        background: -moz-linear-gradient(top, #F9F047 0%, #80E34B 100%);
        background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, #F9F047), color-stop(100%, #80E34B));
        background: -webkit-linear-gradient(top, #F9F047 0%, #80E34B 100%);
        background: -o-linear-gradient(top, #F9F047 0%, #80E34B 100%);
        background: -ms-linear-gradient(top, #F9F047 0%, #80E34B 100%);
        background: linear-gradient(to bottom, #F9F047 0%, #80E34B 100%);

    }
}
```
