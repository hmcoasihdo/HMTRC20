## 下单请求

##### 请求URL
-  ` http://{url}/Payment/CreateTrade `
  
##### 请求方式
- ` Post ` 

##### 参数

|参数名|参数示例|参数说明|
|:----|:----|:-----
|mchid | 10000 |  商户Id
|outorderno | afZDTYgn3pvsX1Wi | 商户订单号
|amount | 100 | 金额(单位为分,整型)
|type | USDT_TRC20 | 合约
|mode | CNY | 货币类型（CNY，USD）
|notifyurl | http://127.0.0.1/notifyurl | 回调地址
|attach | Test | 备注
|sign | MD5加密32位小写 | 签名规则如下

##### 签名规则

- ` MD5(mchid + outorderno + amount + type + mode + notifyurl + attach + Md5Key)`

##### 请求参数
- 
``` 
{
	"mchid": "10000",
	"outorderno": "afZDTYgn3pvsX1Wi",
	"amount": 100,
	"type": "USDT_TRC20",
	"mode": "CNY",
	"notifyurl": "http://127.0.0.1/notifyurl",
	"attach": "Test",
	"sign": "3b1f2c2132f24256ab4dcb030c397dd5"
}
```

##### 返回参数说明 

|参数名|参数示例|参数说明|
|:-----  |:-----|-----|
|result | ok |返回值 |
|msg | 创建成功 | 返回信息|
|url |  | 收银台地址|
|data |  | 返回数据|

##### 返回示例 

``` 
{
	"result": "ok",
	"msg": "创建成功",
	"url": "http://127.0.0.1/cash.html?p=eyJvaWQiOiJBWTEzMTIwMDA2MzA",
	"data": {
		"oid": "AY1312000630729477",(系统订单号)
		"sid": "TCVaHWyxYyixWh8gtek4GSNnu8E44eGdvx",(接受地址)
		"amt": "10",(订单金额)
		"ramt": "1.55",(实收数量)
		"mode": "CNY",(货币类型)
		"cr": 6.46,(下单汇率)
		"t": "2021-05-13 12:10:06"(订单过期时间)
	}
}
```

## 回调通知

##### 请求URL
-  ` {notifyurl} `
  
##### 请求方式
- ` Get ` 

##### 参数

|参数名|参数示例|参数说明|
|:----|:----|:-----
|mchid | 10000 |  商户Id
|orderno | RP1311200898053056 | 商户订单号
|outorderno | afZDTYgn3pvsX1Wi | 商户订单号
|amount | 100 | 金额(单位为分,整型)
|attach | Test | 备注
|sign | MD5加密32位小写 | 签名规则如下

##### 签名规则

- ` MD5(mchid + orderno + outorderno + amount + attach + Md5Key)`

##### 请求示例
- 
``` 
{notifyurl} + ?mchid=10000&orderno=RP1311200898053056&outorderno=afZDTYgn3pvsX1Wi
&amount=100&attach=Test&sign=3b1f2c2132f24256ab4dcb030c397dd5
```

##### 返回参数说明 

成功返回  ok
失败返回  err

##### 返回示例 

```
ok
```




