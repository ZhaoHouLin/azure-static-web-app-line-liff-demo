# 建立一個HTML檔案，並載入 LIFF.js 

```javascript
<script charset="utf-8" src="https://static.line-scdn.net/liff/edge/2/sdk.js"></script>
```

# 初始化liff

```javascript
const liffId = '<your liff id>';
liff.init({
    liffId: liffId, // Use own liffId
})
.then(() => {
    // start to use LIFF's api
    const islogin = liff.isLoggedIn()
    console.log(islogin);
})
.catch((err) => {
    console.log(err);
});
```

# 登入資訊

```javascript
liff.login({ redirectUri: "<導回的URL>" });
```

# 取得 LINE profile

```javascript
liff.getProfile()
.then(profile => {
    console.log(profile)
})
.catch((err) => {
    console.log('error', err);
});
```

# Share Target Picker
```javascript
liff.shareTargetPicker(
    [
        // Message Objects: 放入要傳送的訊息
    ],
    {
        isMultiple: true,
    }
)
.then(function (res) {
    console.log(`[${res.status}] Message sent!`)
}).catch(function (error) {
        // something went wrong before sending a message
        console.log(error);
        console.log('something wrong happen')
})
```

# 文件導讀

https://developers.line.biz/en/reference/liff/