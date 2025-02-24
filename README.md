
### DeepLink


##### 公共请求结构
```
{
"uuid":"qwerasdfzxcv1234",//16位随机字符串
"method":"ConnectAccount",//支持的方法参考以下文档
"network":"eth",//参数 ChainTab 表
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
| Ethereum | ethereum |
|----------|----------|
| Endless  | endless  |
| Tron     | tron     |
| Bitcoin  | bitcoin  |
| Bsc      | bsc      |

---
### luffa_connectAccount 
###### Requests that the user provide an address.
##### request()
##### return()
```
{
"account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155",
"publicKey":"0x611aee782334d189d7d4cf89f092c55b08194876366d44b21c9679e29f66edad"
}
```
---
### luffa_currentAccount
###### requests that the user provide account info
##### request()
```
{"account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155"}
```
##### return()
```
 {
 "uId":"mfmuYLZTSSa",
 "uName":"bob",
 "cId":""// nft头像文件
 "avatar":""//base64的图片
 }
```
---
### luffa_disconnectAccount
##### request()
```
{"account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155"}
```
##### return()

---

### luffa_accountChange

---
### luffa_chainChange

---
### AuthorizePaymentLimit

---
### CurrentAuthorizeLimit

---
### luffa_signData
##### request()
```
 {
 "message":"hello,my name is luffa",
 "account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155"
 }
```
##### return()
```
{"signData":"0x0adcac10c273c1081f503b1d23ec45ff7bbc3933ce54e73afd89c1293570f21442b58adc13299ca7b1b51ed27920441a012e01df19cf333ea03c20d279c00"}
```
---
### luffa_signTransaction
##### request()
```
 {
 "transactionData":"0x506c65617365207369676e2074686973206d65737361676520746f20636f6e6669726d20796f7572206964656e746974792e0xdad87572446bc87c82ea2ff2b65cbc8ca04e44fe",
 "account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155"
 }
```
##### return()
```
{"signData":"0x0adcac10c273c1081f503b1d23ec45ff7bbc3933ce54e73afd89c1293570f21442b58adc13299ca7b1b51ed27920441a012e01df19cf333ea03c20d279c00"}
```
---
### luffa_sendTransaction
###### Initiates a new transaction

---
### luffa_sendRawTransaction
##### request()
```
{
"account":"0xb60e8dd61c5d32be8058bb8eb970870f07233155",
"serializedData":"0x23cafb69ed49ac2539ba8c6bac16266d3a8b6232375c4f62904ab122762d6a994d0000000000000
00200000000000000000000000000000000000000000000000000000000000000010f656e646c6573735f6163636f756e740
87472616e7366657200022023cafb69ed49ac2539ba8c6bac16266d3a8b6232375c4f62904ab122762d6a991000e1f505000
000000000000000000000400d0300000000006400000000000000d2bba56700000000dd00"
}
```
##### return()
```
{"txId":"ArcxDi1anRnTeH61g1XpqrQhtRRAmZYoFATpBNt7gL3b"}
```
---

### //获取当前链
### //调用链合约方法
