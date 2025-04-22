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
| Chain       | network |
|-------------|---------|
| Endless     | endless |
| EndlessTest | eds     |
| Ethereum    | eth     |
| SmartChain  | bsc     |

---
### connect
###### 连接钱包账户
##### support ```endless、eds、eth、bsc、tron```
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
### getAccount
###### 根据参数network返回钱包地址 ---> 前置方法connect()
##### support ```endless、eds、eth、bsc、tron```
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
##### support ```endless、eds```
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
##### support ```endless、eds```
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
##### support ```endless、eds、eth、bsc、tron```
###### 断开连接
##### request()
##### return()
###### 仅公共数据

---
### signMessage
##### support ```endless、eds、eth、bsc、tron```
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
### evmApprove
#### support ```eth、bsc、tron、tron```
##### evm授权合约
#### request() ```eth、bsc```
```
{
"to": "0x4B0897b0513FdBeEc7C469D9aF4fA6C0752aBea7",
"from": "0xdad87572446bc87c82ea2ff2b65cbc8ca04e44fe",
"data": "0x",
}
```
#### response() ```eth、bsc```
```
{
"hash":""//txid
}
```
#### request() ```tron```
```
{
"raw_data_hex":"abd22083b68434ef868be6240d0b9aa9de232..."
"to":"abd22083b68434ef868be6240d0b9aa9de232..."
}
```
#### response() ```tron```
```
{
"signature":""//数组转换成","拼接字符串
}
```
---
### signAndSubmitTransaction
##### support ```endless、eds、eth、bsc、tron```
###### 发送交易数据上链
##### request() ```endless、eds```
```
{
"serializedTransaction":
    {
    "data":""//16进制数据
    }
}
```
##### request() ```eth、bsc```
```
{
"to": "0x4B0897b0513FdBeEc7C469D9aF4fA6C0752aBea7",
"from": "0xdad87572446bc87c82ea2ff2b65cbc8ca04e44fe",
"value": "0x8ac7230489e80000",(根据交易传值，非必填)
"data": "0x",
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
##### support ```endless、eds```
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
##### support ```endless、eds、tron```
##### 用于多签验证结果
##### request() ```endless、eds```
```
{
"transactionData":"0x2c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b8c4000000000000000200000000000000000000000000000000000000000000000000000000000000010f656e646c6573735f6163636f756e74087472616e736665720002202c40fb1f18a8fdd9a1f894548120cdeb8b17976d34c38b0ccae8c4e7f41405b81000e1f505000000000000000000000000400d0300000000006400000000000000b2febf6700000000dd00"
}
```
##### request() ```tron```
```
{ "raw_data_hex":"83b68434ef868be6240d0b..." }
```
##### return() ```endless、eds、tron```
##### 其中tron的signature组成：jsoArray元素使用","拼接成字符串
```
{
"signature":"0020611aee782334d189d7d4cf89f092c55b08194876366d44b21c9679e29f66edad40deade94b9640bf32f8c8d12ff93f5b9cb742439a4aea0d909bbd652194d3d9ad044bbae6dfda47c889af5801af83fca427874e46e439690e9916a0b32f173501",//签名数据
"publicKey":""
}
```
---
### multipleSignApprove
##### support ```endless、eds```
##### 账户升级多签账户[仅签名不上链]
##### request()
```
{"transactionData":""}
```
##### return()
```
{"signature":""}
```
---
### packageTransaction
##### support ```endless、eds```
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
### packageTransactionV2
##### support ```endless、eds```
##### request()
```
{ "data":""}
```
##### response()
```
{ "rawData":"" }
```
---
### luffa_switchChain
##### support ```endless、eds、eth、bsc、tron```
##### request()
```
{ "targetNet":"eth"//切换的目标链 }
```
##### response()
```
{ "account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155" }
```
### currentChain
##### support ```endless、eds、eth、bsc、tron```
##### request()
##### response()
```
{
"blockChainId":1,[使用chainList网站数据]
"network":""
}
```
