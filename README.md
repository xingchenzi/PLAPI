# PLAPI
交易所平台常用接口
关于apikey申请，请在“个人中心 - API管理”页面进行相关操作。
开放交易对的信息查询接口，与币币交易的接口.

账号API相关说明:

**1交易列表：** 

**请求URL：** 
- `https://api.5yg.com/api/markrt/symbols`
  
**请求方式：**
- GET

**参数：** 
无

 **返回示例**

``` 
  {
	"status": 1,
	"msg": "success",
	"data": [
		{
		"symbol_id": 2,
		"symbol": "STC_ETH"
		},
		{
		"symbol_id": 4,
		"symbol": "ETH_BTC"
		},
		{
		"symbol_id": 7,
		"symbol": "STC_CNYT"
		}
	]
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|status |int   |0:失败 1：成功  |
|msg |string   |描述  |
|data |array  |数据  |
|data['symbol_id'] |int  |交易对id  |
|data['symbol'] |string  |交易对名称  |


**2取交易对价格：** 

**请求URL：** 
- `https://api.5yg.com/api/markrt/symbol_price`
  
**请求方式：**
- GET

**参数：** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|symbol_id |int   |交易对id  |

 **返回示例**

``` 
 {
	"status": 1,
	"msg": "success",
	"data": {
		"symbol_id": "2",
		"symbol": "STC_ETH",
		"CNY": 1.0055629226647,
		"USD": 0.14586270799761
	}
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|status |int   |0:失败 1：成功  |
|msg |string   |描述  |
|data |array  |数据  |
|data['symbol_id'] |int  |交易对id  |
|data['symbol'] |string  |交易对名字  |
|data['CNY'] |string  |中文名  |
|data['USD'] |string  |英文名  |

**3取交易记录：** 

**请求URL：** 
- ` https://api.5yg.com/api/markrt/trade`
  
**请求方式：**
- GET

**参数：** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|symbol_id |int   |交易对id  |
|size |number   |数量 0-1000，默认1000 |

 **返回示例**

``` 
  {
    "status": 1,
	"msg": "success",
    "data": [
		{
		"id": 92372,
		"price": 1.0055629226647,
		"amount": "120.9998000000000",
		"time": 1544597275
		},
		{
		"id": 92371,
		"price": 1.0055629226647,
		"amount": "0.0001000000000",
		"time": 1544595037
		},
		{
		"id": 92368,
		"price": 1.17863636833,
		"amount": "0.0000100000000",
		"time": 1544593347
		},
		{
		"id": 92367,
		"price": 1.0055629226647,
		"amount": "0.0000100000000",
		"time": 1544593328
		},
		{
		"id": 92364,
		"price": 1.17863636833,
		"amount": "0.0000100000000",
		"time": 1544593187
		}
	]
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|status |int   |0:失败 1：成功  |
|msg |string   |描述  |
|data |array  |数据  |
|data['id'] |int  |id  |
|data['price'] |array  |成交价  |
|data['amount'] |array  |成交量  |
|data['time'] |array  |成交时间  |

**4取K线数据：** 

**请求URL：** 
- ` https://api.5yg.com/api/markrt/kline`
  
**请求方式：**
- GET

**参数：** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|symbol_id |int   |交易对id  |
|size |number   |数量 0-1000，默认1000 |

 **返回示例**

``` 
  {
	"status": 1,
	"msg": "success",
	"data": [
	{
		"id": 35176,
		"symbol": "STC_ETH",
		"close": "0.0016210000",
		"open": "0.0016210000",
		"high": "0.0016210000",
		"low": "0.0016210000",
		"volumefrom": "120.9998000000"
		},
		{
		"id": 35175,
		"symbol": "STC_ETH",
		"close": "0.0016210000",
		"open": "0.0016210000",
		"high": "0.0016210000",
		"low": "0.0016210000",
		"volumefrom": "0.0001000000"
		},
		{
		"id": 35173,
		"symbol": "STC_ETH",
		"close": "0.0019000000",
		"open": "0.0016210000",
		"high": "0.0019000000",
		"low": "0.0016210000",
		"volumefrom": "0.0000200000"
		},
		{
		"id": 35169,
		"symbol": "STC_ETH",
		"close": "0.0019000000",
		"open": "0.0019000000",
		"high": "0.0019000000",
		"low": "0.0019000000",
		"volumefrom": "0.0000100000"
		},
		{
		"id": 35167,
		"symbol": "STC_ETH",
		"close": "0.0019000000",
		"open": "0.0019000000",
		"high": "0.0019000000",
		"low": "0.0019000000",
		"volumefrom": "0.0000110000"
		}
	]
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|status |int   |0:失败 1：成功  |
|msg |string   |描述  |
|data |array  |数据  |
|data['id'] |int  |id  |
|data['symbol'] |string  |交易对  |
|data['close'] |number  |关盘价  |
|data['open'] |number  |开盘价  |
|data['high'] |number  |最高价  |
|data['low'] |number  |最低价  |
|data['volumefrom'] |number  |交易量  |
