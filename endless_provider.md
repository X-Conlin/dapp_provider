Endless -> dapp协议

小程序统一使用方法
#### luffaWebRequest()
##### request()
###### 请求参数同小程序方法 luffaRequest()

##### 公共请求结构
```
{
"uuid":"qwerasdfzxcv1234",//16位随机字符串
"methodName":"connect",//支持的方法参考以下文档
"initData":{
  "network":"eds",//参数 ChainTab 表
}
"data"://参考不同方法请求结构
}
```
##### 公共响应结构
```
{
"uuid":"qwerasdfzxcv1234",//16位随机字符串
"status": 0,//0成功、-1失败、-2拒绝
"data"://参考不同方法响应结构
}
```
---
### ChainTab
| Endless     | endless |
|-------------|---------|
| EndlessTest | eds     |

---
### getAccount、connect
###### 连接钱包账户
##### request()
##### return()
```
{
"address":"0xb60e8dd61c5d32be8058bb8eb970870f07233155",
"cid":"",//nft头像ci1
"avatar":""//hash头像
}
```
---
### authorizePayment
###### 授权免密支付
##### request()
```
{
"address":"",//发起请求的地址
"module":"",//授权的合约
}
```
##### return()
```
 {
 "limit":0L,//授权限额，单位wei
 "endTime":0L//授权截止时间戳
 }
```
---
### getAuthorizeLimit
###### 当前授权信息
##### request()
```
{
"address":"0xb60e8dd61c5d32be8058bb8eb970870f07233155",
"module":""
}
```
##### return()
```
{
"address":"0xb60e8dd61c5d32be8058bb8eb970870f07233155",
"module":"",
"usable":0L,//免密支付的额度，单位wei，
"expire":0L,//截止时间，秒级时间戳
}
```

### disconnect
###### 断开连接
##### request()
##### return()
###### 仅公共数据

---
### signMessage
###### 签名自定义消息
##### request()
```
{
"message":"",//待签名消息
"from":""//请求地址
}
```
##### return()
```
{
"signature":"",//签名后数据
"publicKey":""//账户公钥
}
```
---
### sendTransaction、signAndSubmitTransaction
###### 发送交易数据上链
##### request()
```
{
"serializedTransaction":
    {
    "data":""//16进制数据
    }
}
```
##### return()
```
{
"hash":""//txid
}
```
---
