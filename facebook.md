```
/**
 * 分享网址到 facebook Message
 * 参考网址：
 * https://developers.facebook.com/docs/sharing/reference/send-dialog
 */
obj.fbMessage = function (url, callback) {
    try {
        FB.ui({
            method: 'send',
            link: url
        });
    } catch (e) {
        console.error("set up FB JavaScript SDK first");
    }
};

Facebook developer
https://developers.facebook.com/
Url Debugger
https://developers.facebook.com/tools/debug/og/object/

Share对话框：
https://developers.facebook.com/docs/sharing/reference/share-dialog
Message对话框：
https://developers.facebook.com/docs/sharing/reference/send-dialog

*******************************  Facebook 、Twitter 总结  ****************************

Url Debugger：
twitter : https://cards-dev.twitter.com/validator
facebook: https://developers.facebook.com/tools/debug/og/object/
google+: http://www.google.com.hk/webmasters/tools/richsnippets?gws_rd=cr


补充：
微信、微博、Facebook、Twitter等社交媒体分享方案探索： http://blog.csdn.net/cj1029/article/details/44466187
```