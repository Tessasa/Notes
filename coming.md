###less

```
// 跑马灯效果
.tips {
    display: block;
    height: 44px;
    position: relative;
    background: #f5f4ef;

    .light {
        position: absolute;
        width: 40px;
        height: 44px;
        .lamp {
            position: absolute;
            bottom: 14px;
            left: 19px;
            width: 13px;
            height: 16px;
            background: url(../img/light1.png) no-repeat center;
            background-size: 13px 16px;
        }
        .flashlight {
            position: absolute;
            top: 9px;
            left: 15px;
            width: 21px;
            height: 10px;
            background: url(../img/light2.png) no-repeat center;
            background-size: 21px 10px;
            animation: light 1s ease-in-out infinite;
        }
    }

    .marquee {
        margin-left: 40px;
        height: 100%;
        width: 100%;
        font-size: 14px;
        color: #ff8919;
        overflow: hidden;
        position: relative;
    }

    .marquee .tip {
        display: block;
        width: 200%;
        height: 100%;
        line-height: 44px;
        position: absolute;
        left: 40px;
        overflow: hidden;
        animation: marquee 10s linear infinite;
    }

    .marquee span {
        float: left;
        width: 50%;
        strong {
            color: #D0021B;
            font-weight: 400;
        }
    }
    .arrow {
        position: absolute;
        top: 0;
        right: 0;
        width: 32px;
        height: 44px;
        background: #f5f4ef;
        &::after {
            content: '';
            position: absolute;
            right: 15px;
            top: 18px;
            width: 8px;
            height: 8px;
            transform: translateY(-50%);
            border-bottom: solid 1px #FF8919;
            border-right: solid 1px #FF8919;
            transform: rotate(315deg);
        }
    }
}

@keyframes marquee {
    0% {
        left: 0;
    }
    100% {
        left: -100%;
    }
}

@keyframes light {
    0% {
        opacity: .2;
    }
    100% {
        opacity: 1;
    }
}
```

###html

```
  <a class="tips" id="hzTopbarAdv" href="#">
        <div class="light">
            <i class="lamp"></i>
            <i class="flashlight"></i>
        </div>
        <div class="marquee">
            <div class="tip">
                <span>您的账户内有会员卡未完善信息，请于90天内完善信息</span>
                <span>您的账户内有会员卡未完善信息，请于90天内完善信息</span>
            </div>
        </div>
        <i class="arrow" href=""></i>
    </a>
    ```