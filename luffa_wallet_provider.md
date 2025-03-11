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

### luffa_switchChain()
##### request()
```
{ "targetNet":"eth"//切换的目标链 }
```
##### response()
```
{ "address":"0xb60e8dd61c5d32be8058bb8eb970870f07233155" }
```
