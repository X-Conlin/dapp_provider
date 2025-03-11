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
"metadata":{
  "title":"",
  "url":"",
  "icon":""
}
"data"://参考不同方法请求结构
"from":""
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
"cid":"",//nft头像cid
"avatar":"",//hash头像
"uid":"",
"nickname":""
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
### signAndSubmitTransaction
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
### signTransaction
##### 仅签名交易
##### request()
```
{
"transactionData":"0x2c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b8c4000000000000000200000000000000000000000000000000000000000000000000000000000000010f656e646c6573735f6163636f756e74087472616e736665720002202c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b81000e1f505000000000000000000000000400d0300000000006400000000000000b2febf6700000000dd00"
}
```
##### return()
```
{
"signature":"0020611aee782334d189d7d4cf89f092c55b08194876366d44b21c9679e29f66edad40deade94b9640bf32f8c8d12ff93f5b9cb742439a4aea0d909bbd652194d3d9ad044bbae6dfda47c889af5801af83fca427874e46e439690e9916a0b32f173501",//签名数据
"publicKey":""
}
```
---
### signBuildTransaction
##### 用于多签验证结果
##### request()
```
{
"transactionData":"0x2c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b8c4000000000000000200000000000000000000000000000000000000000000000000000000000000010f656e646c6573735f6163636f756e74087472616e736665720002202c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b81000e1f505000000000000000000000000400d0300000000006400000000000000b2febf6700000000dd00"
}
```
##### return()
```
{
"signature":"0020611aee782334d189d7d4cf89f092c55b08194876366d44b21c9679e29f66edad40deade94b9640bf32f8c8d12ff93f5b9cb742439a4aea0d909bbd652194d3d9ad044bbae6dfda47c889af5801af83fca427874e46e439690e9916a0b32f173501",//签名数据
"publicKey":""
}
```
---
### packageTransaction
##### request()
```
{
"module":"",
"moduleName":"",
"functionName":"",
"data":"",
"argsData":["",""]
}
```
##### response()
```
{ "rawData":"" }
```
---
### luffa_switchChain()
##### request()
```
{ "targetNet":"eth"//切换的目标链 }
```
##### response()
```
{ "account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155" }
```
