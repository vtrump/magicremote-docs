# 参考代码

## Demo

* [Demo](https://htmlpreview.github.io/?https://github.com/vtrump/magicremote-docs/blob/main/docs/demo.html)

## 链接申请请求

* Python

```python
import requests

resp = requests.post('https://mg-api.vtio.cn/open/connect/apply', headers={
    'token': '[Your App Secret]'
})

if resp.status_code != 200:
    print(resp.status_code)
    raise Exception('Connect Error')
resp_j = resp.json()
if not resp_j['success']:
    raise Exception('%s, %s' % (resp_j.get('errcode'), resp_j.get('errmsg')))
res = resp_j.get('result')
print(res)
```

## 转化Key成二维码

* qrcode.js

```html

<div id="qrcode"></div>
<script>
    new QRCode(document.getElementById("qrcode"), '[Key]');
</script>
```

## 接受配对后的回调

* python

```python
@app.route('/remote/callback', methods=['POST'])
def mg_callback():
    data = request.form.get('data')
    # TODO save the cnf, and wait client query this info
    return 'success'
```

## 推送命令

* python

```python
requests.post('https://connect-ts-1.vtio.cn/event/push', data={
    'key': '[key]',
    'code': '[code]',
    'data': '[CommandString]'
})
```