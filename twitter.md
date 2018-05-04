```
Tweet developer
https://dev.twitter.com


发推：
https://twitter.com/intent/tweet?text=&url=
Url Debugger：
https://cards-dev.twitter.com/validator

补充：
Tweet Button发送成功后回调
http://www.it610.com/article/670851.htm
Twitter forms:
https://twittercommunity.com/t/tweet-intent-response-the-same-for-successful-and-unsuccessful-posts/56780
How to know when the user tweeted (with custom button):
http://projs.hackhat.com/how-to-make-a-custom-share-tweet-button-and-know-when-the-user-clicked/
```


```
Twitter share

<a class="twitter-share-button"
   href="https://twitter.com/intent/tweet">Tweet</a>

或：

<button class="tweet-this btn-default">Tweet this!</button>

// Helper to create the url.
var tweetUrlBuilder = function (o) {
    return [
        'https://twitter.com/intent/tweet?tw_p=tweetbutton',
        '&url=', encodeURI(o.url),
        '&via=', o.via,
        '&text=', o.text
    ].join('');
};

// When the button is clicked:
$('.tweet-this').on('click', function () {
    // Create our custom url.
    var url = tweetUrlBuilder({
        url: 'http://bit.ly/OChT65',
        via: 'ProJavaScript',
        text: 'How to make a custom share tweet button and know when the user tweeted'
    });
    // Open the window.
    window.open(url, 'Tweet', 'height=500,width=700');
});

console.log('callback:',callback);
var callback = function (e) {
    if (e && e.data) {
        var data;
        try {
            data = JSON.parse(e.data);
        } catch (e) {
            // Don't care.
        }
        if (data && data.params && data.params.indexOf('tweet') > -1) {
            alert('Thanks for the tweet!');
        }
    }
};
// Here is the secret ingredient
window.addEventListener ? window.addEventListener("message", callback, !1) : window.attachEvent("onmessage", callback)

```