# okteto部署vless

### okteto地址：https://okteto.com/

### 变量

对部署时需设定的变量名称做如下说明：

UUID: 自行修改entrypoint.sh文件中的UUID变量

路径：/app

### 通过 CloudFlare Workers 反向代理

```js
addEventListener(
    "fetch",event => {
    let url=new URL(event.request.url);
    url.hostname="xxx.cloud.okteto.net;
    let request=new Request(url,event.request);
    event. respondWith(
      fetch(request)
    )
  }
)
```

