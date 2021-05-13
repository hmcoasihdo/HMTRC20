### 请求参数

##### 请求URL
-  ` http://{url}/Payment/CreateTrade `
  
##### 请求方式
- ` P ` 

##### 参数

|参数名|参数示例|参数说明|
|:----|:----|:-----
|route | GetScoreTT |  路由
|useruin | afZDTYgn3pvsX1Wi | 用户uinId
|time | 1619059980 | 时间戳(精确到毫秒)
|sign | MD5加密32位大写 | 签名规则如下

##### 签名规则

- ` MD5(useruin + time + 密钥)`

##### 请求参数
- 
``` 
http://{url}/interface/tp?route=GetScoreTT&useruin=3971f3a9a18947779eecfbde3da7cc7&time=1619074527080
&sign=D6884FF02E3636B4C42365DE07BAC60E
```

##### 返回参数说明 

|参数名|参数示例|参数说明|
|:-----  |:-----|-----|
|code | 0 | 返回码|
|msg | 请求成功 | 返回信息|
|data |  | 返回数据|

##### 返回示例 

``` 

```



