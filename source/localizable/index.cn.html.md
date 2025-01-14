---
title: title

language_tabs: # must be one of https://git.io/vQNgJ


toc_footers:
  - <a href='https://www.kucoin.com'>Sign Up for KuCoin</a>

includes:

---

# 快速开始

## 基本介绍 

欢迎来到KuCoin交易员和开发者文档。 这些文档概述了交易功能，市场行情和其他应用开发接口。

API分为两部分：**REST API和Websocket 实时数据流**

 -  REST API包含四个类别：**[用户模块](#b6935b918b)（私有），[交易模块](#484936af01)（私有），[市场数据](#841ec28ecd)（公共），[其他接口](#cd67660573)（公共）**
 -  Websocket包含两类：**公共频道和私人频道**

私有API需要身份验证，并提供下单和帐户相关信息的访问权限。

Websocket API提供市场数据，其中大部分都是公开的。

## 阅读顺序

1.  [沙盒环境](#2d9a68bcb2) 帮助您在测试环境更好地了解和使用API。
2.  [REST&nbsp;API](#rest-nbsp-api) 如何创建一个REST&nbsp;API。
3.  [服务器时间](#89b4aa6364) 无需身份验证的情况下，发起一个请求并获取返回结果值（可用作连接测试）。
4.  [接口认证](#e6a574d26d) 如何创建一个有身份验证的请求。
5.  [内部资金划转](#c08ac949fb) 储蓄账户和交易账户之间资产的相互划转。
6.  [账户列表](#f0f7ae469d) 获取个人的账户详情指南。
7.  [下单](#fd6ce2a756) 获取下单操作指南。
8.  [委托买卖盘](#ab5235c05c) 获取买卖盘的快照信息。
9.  [Websocket](#42f0e0ea9d) 如何创建Websocket 连接
10. [Level-2 市场行情](#level-2-3) 如何使用Websocket 构建一个实时的买卖盘。 
11. [余额变更](#5a9519dabe) Websocket私人频道指南，实时获取账户余额变更信息

## 做市激励计划

KuCoin为专业做市商提供做市激励计划。
参与该计划，可以获得以下激励：

- 做市商返佣
- 每个月奖励高达30,000 KCS，来回馈最优秀的做市商
- 直接市场接入和主机托管服务

具有良好做市策略和大交易量的用户欢迎参与此长期做市激励计划。如果您的账户在过去30天内的交易量超过5000 BTC，请提供以下信息以发送电子邮件至mm@kucoin.com，邮件主题为“Spot Market Maker Application”：

- 提供平台帐户（需要电子邮件，无需推荐关系）
- 过去30天内在任何交易所交易的交易量证明或VIP级别的证明
- 请简要说明做市的方法（不需要详细说明）以及估算做市订单量的百分比。

  
## VIP快速通道 

具有良好做市策略和大交易量的用户欢迎参与长期做市商计划。 如果您的帐户资产大于10BTC，请提供以下信息以发送电子邮件至：

**vip@kucoin.com**（现货）进行做市商申请;

- 提供平台帐户（需要电子邮件，无需推荐关系）;
- 提供其他交易平台做市商交易量的截图（例如30天内的交易量，或VIP级别等）;
- 请简要说明做市的方法，不需要详细说明。

## 子账号
子账号需要在Web端进行创建，并配置子账号的API。
子账号可以用作隔离资金和交易。资金可以在母账号和子账号之间相互划转。
子账户的资金仅用于子账号交易，不可以提现。

子账号的API可以访问所有公共接口。此外，通过API-KEY可以访问以下私有接口。

接口名称 | 描述
---------- | -------
[账户列表](#f0f7ae469d) | 获取所有账户信息
[单个账户详情](#7f8d035c7d) | 获取单个账户信息
[创建账户](#9ec360d41d) | 创建账户
[账户流水记录](#c8122540e1) | 获取账户流水记录
[账户冻结记录](#8092434cb7) | 获取账户冻结记录
[内部资金划转](#c08ac949fb) | 储蓄账户和交易账户资金相互划转
[下单](#fd6ce2a756) | 下单
[单个撤单](#fc69531f52) | 取消单个订单
[全部撤单](#f175a031e7) | 取消所有订单
[订单记录](#23e02e24af) | 获取订单记录
[最近订单记录](#35acc0041f) | 获取最近24小时内的订单列表（最多获取1000条记录）
[单个订单详情](#d86507e2dd) | 获取单个订单详情
[成交记录](#6a30a471cf) | 获取成交记录
[最近成交记录](#5abc068b38) | 获取最近24小时内的成交记录（最多1000条记录）

子账号与母账号共享同一手续费等级（根据子账号与母账号交易额/KCS持有量累加求和计算划分）。
子账号在交易之前需要将资金从储蓄账户转到交易账户。

<aside class="notice">子账号不支持提现和充值</aside>

# 更新内容

为了您能获取到最新的API 变更的通知，请在 [KuCoin Docs Github](https://github.com/Kucoin/kucoin-api-docs)添加关注【Watch】


**6/19/19**: 

- 修改 [子母账号划转接口](#108b1a50d2)

**6/13/19**: 

- 添加 对接Open API[常见问题](#765f554c38)
- 添加 [Level-3的优势](#34b637869b).

**5/28/19**: 

- 修改 [交易市场列表](#b8f118fefc) SC改名为USDS。
- 添加 [内部资金划转](#c08ac949fb) 新增接口，原来的接口于三个月后（28/8/19）过期。
- 添加 [申请提现](#6eaf6b9ae0) **指定收藏地址提现** 描述。
- 添加 [24小时统计](#24) 添加字段 **averagePrice** 昨日24小时平均成交价格。

**5/8/19**: 

- 添加 [申请提现](#6eaf6b9ae0)，[获取提现额度](#c46f4b3b8e)，[申请充值地址](#9277fb3f66)，[获取充值地址](#b3114995fd)，[币种详情](#cb79285fc3)，添加**chain**字段。
- 添加 [内部资金划转](#c08ac949fb) 添加资金划转操作步骤。
- 添加 对接[Level-3撮合引擎数据](#level-nbsp-3)的[go-level-3-demo](#level-nbsp-3)
- 修改 [请求频率限制](#26435b04cf)


**4/24/19**: 

- 删除 [完整的撮合引擎数据(Level&nbsp;3)](#level-nbsp-3) 为了保护隐藏订单信息，在**received** 消息中删除 **size**  和 **funds** 字段，私人频道字段保持不变。
- 删除 [完整的撮合引擎数据(Level&nbsp;3)](#level-nbsp-3) 为了保护隐藏订单信息，在 **open** 消息中删除 **remainSize** 字段，私人频道字段保持不变。
- 新增 [获取所有子账号信息](#a0bc1cb873)接口。
- 新增 [获取单个子账户信息](#db03191132)接口。
- 新增 [获取所有子账户信息](#93f3f96acd)接口。
- 新增 [子母账号资金划转](#108b1a50d2)接口。

**3/27/19** : 

- 添加 [交易对列表](#a17b4e2866) **feeCurrency** 字段。

**3/25/19** : 

- 添加 [全局行情快照](#f3027c9902) **volValue** 字段。
- 添加 [完整的撮合引擎数据(Level&nbsp;3)](#level-nbsp-3) **received**消息中  **clientOid** 字段，您可以通过 **clientOid** 来筛选订单信息。
- 添加 私人频道[余额变更](#5a9519dabe) **accountId** 字段，您可以通过 **accountId** 来跟踪账户余额变更信息。

**3/13/19** : 

- 修改 一个账户中单个交易对的最大匹配订单为200（包括止损订单）。

**3/6/19** : 

- 添加 订单系统和撮合引擎时间单位为  **nanoseconds**。

**2/28/19** : 

- 修改 [交易对列表](#a17b4e2866) 返回值描述。
- 新增 [获取V1历史充值列表](#v1)接口。
- 新增 [获取V1历史提现列表](#v1-2)接口。
- 新增 [获取V1历史订单列表](#v1-3)接口。
- 添加 部分API JSON 字段描述。
- 删除 [撮合执行数据](#c7f054198c) 删除 **sn** 字段 。 
- 修改 [法币换算价格](#a2e56e9e0e) 参数描述。
- 添加 创建Websocket连接时 **acceptUsermessage** 字段的描述。

**2/22/19** : 

- 添加 [24小时统计](#24) 添加**volValue**字段。

**2/21/19** : 

- 新增 [全部买卖盘(价格合并)](#level-2-2) 
- 添加 Level-1,2,3 数据添加 **time** 字段
- 新增 [法币换算价格](#a2e56e9e0e)接口。

**2/20/19** : 

- 添加 [全局行情快照](#f3027c9902)和[行情快照](#b784c68bd3)添加 **time** 字段

**2/19/19** : 

- 添加 [全局行情快照](#f3027c9902)

**2/18/19** : 

- 新增 [最近订单列表](#23e02e24af)接口
- 新增 [最近成交记录](#5abc068b38)接口

**2/16/19** : 

- 添加 公共频道添加[全部交易对瞬时行情](#251e3b7813) 订阅
- 修改 [权限](#api-2)描述

**1/30/19** : 

- 新增 官方SDK [CCXT](#client-libraries)

**1/25/19** : 

- 添加 [Get Market List](#get-market-list)
- 添加 [交易对行情快照](#396f791c4d)
- 添加 [按市场的交易对行情快照](#1240da64f2)
- 添加 官方的 [Java & Go SDK](#level-nbsp-3)


# 基本介绍
Kucoin 系统 和 API 介绍.


# 撮合引擎 

## 订单生命周期

当订单进入撮合引擎时，订单状态为 **received** 。如果一个订单与另外一个订单完全撮合，订单状态为 **done** 。一个订单可以部分被撮合也可以全部被撮合，没有被撮合的订单状态为 **open**。当订单被取消（ **canceled** ）或成交（ **filled** ），订单状态为 **done**, 否则订单会一直保持 **open** 状态

## 自成交保护（STP）

**自成交保护**（**Self-Trade Prevention**） 默认为空。当您下单时指定了 **STP**，您的订单将不会发生自成交。如果您下单前没有指定 **STP**，您的订单可能会被自己的订单成交。

### 减量和取消(DC)

目前，**市价单不支持减量和取消（DECREMENT AND CANCEL）**。针对同一个用户，同一个交易对，买卖订单同时存在，数量少的订单取消，数量多的订单减去少的一方的数量，继续执行撮合。如果数量相同，两个订单都会取消。

### 取消旧的订单(CO)

**Cancel Old** 全部取消旧的订单，新的订单继续执行撮合。

### 取消新的订单(CN)

**Cancel New** 全部取消新的订单，旧的订单仍然在买卖盘中。

### 双方都取消(CB)

**Cancel Both** 买卖方都取消。

## 撮合引擎数据

### Level-3 市场数据（推荐使用）

撮合引擎推送的数据，是每一个订单的信息，即Level-3的市场数据。<br/>
Level-3市场数据更适合高频交易者<br/>
您通过WebSocket订阅[Level-3市场数据](#level-nbsp-3):

* 更快速获取到市场实时的行情信息，推送速度Level-3 >= Level-2
* 可以用于构建维护买卖盘
* 可以获取单笔订单的数量变动原因
* 更实时的获取到订单的成交情况
* 可以完全取代Rest API的大部分拉取信息功能(Rest请求有严格的请求频率限制)

不同的类型信息的处理可以参考[Level-3 demo](#4623bd9386)或参考下方Level-3的[Message Type](#level-nbsp-3)


# 客户端开发库

客户端库可以帮助您快速集成我们的API。

**官方**

- [Java SDK](https://github.com/Kucoin/KuCoin-Java-SDK)
- [PHP SDK](https://github.com/Kucoin/KuCoin-PHP-SDK)
- [Go SDK](https://github.com/Kucoin/KuCoin-Go-SDK)
- [Level3-Demo](https://github.com/Kucoin/kucoin-go-level3-demo)

CCXT 是我们官方SDK提供方，您可以使用CCXT来对接Kucoin API。
更多信息, 请访问: [https://ccxt.trade](https://ccxt.trade).

**非官方**

感谢社区贡献者，这些是社区开发人员提供的开源SDK。由于每个库都经常更新，因此KuCoin不会审查所有源代码，也不会对其进行严格测试。KuCoin不对SDK的安全性负责。请在使用前进行基本的代码审查并评估风险。请在使用前，浏览一下pull request以及issue。

- Python [sammchardy/python-kucoin](https://github.com/sammchardy/python-kucoin)
- .NET [mscheetz/KuCoinApi.Net](https://github.com/mscheetz/KuCoinApi.Net/tree/v2.0)

欢迎各位开发者 [提交](https://github.com/Kucoin) 您的SDK给我们，优秀者会获得KCS作为奖励。

**代码样例**

- PHP 单个文件样例 (GET & POST & DELETE)  [Github Link](https://github.com/Kucoin/kucoin-api-docs/tree/master/examples/php)

- - -

# 沙盒测试环境

**沙盒是测试环境**，用于测试API连接和Web交易，并提供交易的所有功能。在沙盒中，您可以使用虚假资金来测试交易功能。
 
沙盒环境中的登录会话和API密钥与生产环境完全分离。您可以使用沙盒环境中的Web界面来创建API密钥。

注意：在沙盒环境中注册后，您将收到系统在您的帐户中自动充值的一定数量的测试资金（BTC，ETH或KCS）。如果您想**交易**，请将资产从**储蓄**账户转移到**交易**账户。这些资金仅用于测试目的，不能提现。

用于API测试的沙盒URL：

网址：
**[https://sandbox.kucoin.com](https://sandbox.kucoin.com)**

REST&nbsp;API 连接地址:
**https://openapi-sandbox.kucoin.com**


# 请求频率限制

当请求频率超过限制频率时，系统将返回 **429 Too Many Request** 提示。如果请求次数多次超过频率限制，你的IP或账户会被限制使用1分钟。请求返回中包含当前类型的剩余请求次数。

# 申请提高频率限制
做市商或专业交易员，如需提高请求频率，请将您的账户信息、申请原因，及交易量发送至[api@kucoin.com](mailto:api@kucoin.com)。

###REST API

我们通过 **API-KEY** 限制 REST API： **每分钟1800次请求**，一个账号最多可以[创建](#api-key)10个API-KEY。

####硬性限制
[获取成交记录](#6a30a471cf): **每十秒100次请求**（超过会被禁用10秒）
[获取订单列表](#23e02e24af): **每十秒200次请求**（超过会被禁用10秒）


###WEBSOCKET


### 连接数量
每个用户ID同时建立的连接数： ≤ 10个

### 连接次数
连接请求次数限制：每分钟 30次 请求

### 上行消息条数
向服务器发送指令条数限制：每10秒 100条

### 订阅topic数量 
每个连接最大可订阅topic数量限制：100个topics


# REST&nbsp;API

## API服务器地址

REST API 对于账户、订单、和市场数据都有有自己的接口端点。

基本URL: **https://api.kucoin.com**。 

请求URL 由基本URL和接口端点组成。 

## 接口端点(Endpoint)

每一个接口都有一个端点（Endpoint） 

对于**GET** 请求, 端点需要要包含请求参数。

比如，"[账户列表](#f0f7ae469d)"，默认的端点是 **/api/v1/accounts**。
如果您传递“currency” 请求参数为BTC，那么端点为 **/api/v1/accounts?currency=BTC**，最终的请求URL为**https://openapi-v2.kucoin.com/api/v1/accounts?currency=BTC**。


# 请求
所有的POST请求和返回内容类型都是 **application/json**.  


## 请求参数

对于 **GET, DELETE** 请求, 请求URL需要包含所有的请求参数。(**例如， /api/v1/accounts?currency=BTC**)

对于 **POST, PUT** 请求, 所有的请求参数以JSON的格式放在请求体中，JSON字符串中不要包含额外的空格。 (**例如， {"currency":"BTC"}**).

## 数据字段

所有接口可能会在将来添加字段，现有字段不会改变，在对接API时，请注意兼容性。

## 错误返回

请求报错会返回错误信息，返回对象包含错误码code（HTTP错误码或系统错误码）,以及信息msg（可排查错误原因）。

### HTTP错误码

```
{
  "code": "400100",
  "msg": "Invalid Parameter."
}

```

代码 | 意义
---------- | -------
400 | Bad Request -- 无效的请求格式
401 | Unauthorized -- 无效的API-KEY，请检查签名
403 | Forbidden -- 请求被禁止
404 | Not Found -- 找不到请求资源
405 | Method Not Allowed -- 请求行中指定的请求方法不能被用于请求相应的资源
415 | Content-Type: application/json -- [请求类型](#请求)必须为application/json
429 | Too Many Requests -- 超过[请求频率限制](#26435b04cf)
500 | Internal Server Error -- 服务器的内部程序错误，请稍后重试
503 | Service Unavailable -- 服务器维护或者过载，服务器当前无法处理请求，请稍后重试



### 系统错误码

代码 | 意义
---------- | -------
400001 | Any of KC-API-KEY, KC-API-SIGN, KC-API-TIMESTAMP, KC-API-PASSPHRASE is missing in your request header -- 请求头中缺少[验签参数](#35e3a383b3)
400002 | KC-API-TIMESTAMP Invalid -- 请求时间与服务器时间相差超过5秒
400003 | KC-API-KEY not exists -- API-KEY 不存在
400004 | KC-API-PASSPHRASE error -- API-PASSPHRASE 不正确
400005 | Signature error -- [签名](#消息签名)错误
400006 | The requested ip address is not in the api whitelist -- 请求IP不在API白名单中，请在web端API管理配置IP白名单
400007 | Access Denied -- 您的API没有足够的权限访问这个URI
404000 | Url Not Found -- 找不到请求资源
400100 | Parameter Error -- 您的请求参数不合法
411100 | User are frozen -- 用户被冻结，请联系[帮助中心](https://kucoin.zendesk.com/hc/zh-cn/requests/new)
500000 | Internal Server Error -- 服务器的内部程序错误，请稍后重试

如果系统返回HTTP状态码为200，但业务失败，系统会报错。您可根据返回的参数消息排查错误。



## 成功返回

HTTP状态代码为200和 系统代码为 200000 标示一次成功的响应。成功请求的有效返回如下：

```
{
  "code": "200000",
  "data": "1544657947759"
}
```

## 分页

对于多数REST查询请求，返回对象为分页的数组形式，使用currentPage和pageSize来获取分页结果。比如,像接口，/api/v1/trades, /api/v1/fills, /api/v1/orders, 默认返回第一页，共50条数据。要获取更多数据信息，后续请求可按需设置分页获取数据。


### 请求参数

参数名称| 类型 | 默认值 | 描述
---------- |  ------- |------- | ------
currentPage| int | 1 | 当前页码
pageSize | int |50 | 每页记录数

### 示例
**GET /api/v1/orders?currentPage=1&pageSize=50**


# 类型说明 

## 时间戳 

所有时间戳参数都应以毫秒为单位，除非另有说明。例如， **1544657947759**。

撮合引擎和订单系统的时间戳使用的是纳秒为单位。

## 数字 

为了保证跨平台的数字的精确度，Decimal 需要转化为字符串返回。请在发出请求时，将数字转换为字符串来避免数字被截断或者精度错误。




# 接口认证

## 创建API-KEY

在请求私有端点（private endpoints）之前，您需要在Web端创建API-KEY。

成功创建API后，您需妥善保管好以下三条信息：

* Key
* Secret
* Passphrase

Key和Secret将由KuCoin随机生成并提供。Passphrase（密码）将在您创建API时填写，如果忘记后无法恢复，需要重新创建API。

## API权限

您可以在Web端 - API管理，限制API的权限。
API 权限有以下:

* **通用权限** - 允许API访问大部分的GET请求。
* **交易权限** - 允许API具有下单和获取交易数据权限。
* **转账权限** - 允许API划转资金，包含充值和提现。子账号没有转账权限。
  授权转账权限时请注意，不需要邮箱验证和谷歌验证就可以使用API进行转账。
  

请参考下方API文档，看接口具体需要哪些权限。

## 创建请求

私有的Rest请求头必须包含以下内容:

* **KC-API-KEY** API-KEY以字符串传递
* **KC-API-SIGN** [签名](#8ba46c43fe)
* **KC-API-TIMESTAMP** 请求的时间戳
* **KC-API-PASSPHRASE** 创建API时填的API密码

## 签名

```php
    <?php
    class API {
        public function __construct($key, $secret, $passphrase) {
          $this->key = $key;
          $this->secret = $secret;
          $this->passphrase = $passphrase;
        }

        public function signature($request_path = '', $body = '', $timestamp = false, $method = 'GET') {
          
          $body = is_array($body) ? json_encode($body) : $body; // Body must be in json format
          
          $timestamp = $timestamp ? $timestamp : time() * 1000;

          $what = $timestamp . $method . $request_path . $body;

          return base64_encode(hash_hmac("sha256", $what, $this->secret, true));
        }
    }
    ?> 
```

```python
    #Example for get balance of accounts in python
    
    api_key = "api_key"
    api_secret = "api_secret"
    api_passphrase = "api_passphrase"
    url = 'https://openapi-sandbox.kucoin.com/api/v1/accounts'
    now = int(time.time() * 1000)
    str_to_sign = str(now) + 'GET' + '/api/v1/accounts'
    signature = base64.b64encode(
        hmac.new(api_secret.encode('utf-8'), str_to_sign.encode('utf-8'), hashlib.sha256).digest())
    headers = {
        "KC-API-SIGN": signature,
        "KC-API-TIMESTAMP": str(now),
        "KC-API-KEY": api_key,
        "KC-API-PASSPHRASE": api_passphrase
    }
    response = requests.request('get', url, headers=headers)
    print(response.status_code)
    print(response.json())
    
    #Example for create deposit addresses in python
    url = 'https://openapi-sandbox.kucoin.com/api/v1/deposit-addresses'
    now = int(time.time() * 1000)
    data = {"currency": "BTC"}
    data_json = json.dumps(data)
    str_to_sign = str(now) + 'POST' + '/api/v1/deposit-addresses' + data_json
    signature = base64.b64encode(
        hmac.new(api_secret.encode('utf-8'), str_to_sign.encode('utf-8'), hashlib.sha256).digest())
    headers = {
        "KC-API-SIGN": signature,
        "KC-API-TIMESTAMP": str(now),
        "KC-API-KEY": api_key,
        "KC-API-PASSPHRASE": api_passphrase,
        "Content-Type": "application/json" # specifying content type or using json=data in request
    }
    response = requests.request('post', url, headers=headers, data=data_json)
    print(response.status_code)
    print(response.json())
```
请求头中的 **KC-API-SIGN**: 

* 使用 API-Secret 对
{timestamp + method+ endpoint  + body} 拼接的字符串进行HMAC-sha256加密。
* 再将加密内容使用 base64 加密。

Notice：
* 加密的 timestamp 需要和请求头中的KC-API-TIMESTAMP保持一致
* 用于加密的body需要和请求中的Request Body的内容保持一致
* 请求方法需要大写
* 对于 GET, DELETE 请求，endpoint 需要包含请求的参数（/api/v1/deposit-addresses?currency=BTC）。如果没有请求体（通常用于GET请求），则请求体使用空字符串””。



```python
#Example for Create Deposit Address

curl -H "Content-Type:application/json" -H "KC-API-KEY:5c2db93503aa674c74a31734" -H "KC-API-TIMESTAMP:1547015186532" -H "KC-API-PASSPHRASE:Abc123456" -H "KC-API-SIGN:7QP/oM0ykidMdrfNEUmng8eZjg/ZvPafjIqmxiVfYu4=" 
-X POST -d '{"currency":"BTC"}' http://openapi-v2.kucoin.com/api/v1/deposit-addresses

KC-API-KEY = 5c2db93503aa674c74a31734
KC-API-SECRET = f03a5284-5c39-4aaa-9b20-dea10bdcf8e3
KC-API-PASSPHRASE = Abc123456
TIMESTAMP = 1547015186532
METHOD = POST
ENDPOINT = /api/v1/deposit-addresses
STRING-TO-SIGN = 1547015186532POST/api/v1/deposit-addresses{"currency":"BTC"}
KC-API-SIGN = 7QP/oM0ykidMdrfNEUmng8eZjg/ZvPafjIqmxiVfYu4=
```

<aside class="spacer16"></aside>
<aside class="spacer8"></aside>

## 选择时间戳

请求头中的 **KC-API-TIMESTAMP** 必须为[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)，精确到毫秒。例如，1547015186532

您服务器请求的时间戳与API服务器时间相差必须在五秒以内，否则您的请求会过期，导致您的请求被拒绝。如果您认为您的服务器和API服务器之间有很多时间偏差，我们推荐您使用我们[服务器时间](#获取服务器时间)。

# 常见问题

## 签名错误

* 检查API-KEY，API-SECRET，API-PASSPHRASE是否正确
* 检查签名内容顺序 timestamp + method + requestEndpoint + body
* 检查header中timestamp是否与生成signature一致
* 检查签名生成是否为base64编码
* get请求是否以表单方式提交
* post请求的数据格式是否是json格式（application/json; charset=utf-8）
  
## 申请提现
* memo字段<br/>
对于不同的币种有些有memo字段，有些没有memo字段，其他平台可能会使用tag或paymentId<br/>
对于没有 memo 的币种，在使用API提现的时候是不能传递memo值，否则，接口会返回 kucoin incorrect withdrawal address
* amount字段<br/>
amount需要符合该币种提现的precision，可以通过[获取提现额度](#5bd567d526)获取<br/>
提现金额必须为提现精度的整数倍，如果为0表示只能为整数。

## .net SDK
* POST请求验签错误<br/> 
"{\"code\":\"400005\",\"msg\":\"Invalid KC-API-SIGN\"}"<br/>
代码有bug<br/>
 var response = body == null ? await _restRepo.PostApi<ApiResponse<T>, SortedDictionary<string, object>>(url, body, headers) : await _restRepo.PostApi<ApiResponse<T>>(url, headers);<br/>
修改为:<br/>
 var response = body != null ? await _restRepo.PostApi<ApiResponse<T>, SortedDictionary<string, object>>(url, body, headers) : await _restRepo.PostApi<ApiResponse<T>>(url, headers);

## WebSocket 限制
* 一个连接最多订阅100个topic；
* token有效期24小时；
* 一个用户最多10个连接；
* 客户端每10秒最多上行100个消息；
* 一个symbol 就是一个topic; e.g.Topic: /market/level3:{symbol},{symbol}... 

## 返回 403 问题
403 "The request could not be satisfied. Bad Request" from Amazon CloudFront<br/>

* 检查请求是否为HTTPS
* 移除GET请求中的RequestBody


# 用户模块

以下请求需要校验[签名](#8ba46c43fe)。

# 账号
## 获取所有子账号信息



```json
[{
		"userId": "5cbd31ab9c93e9280cd36a0a",  //subUserId子账号用户ID
		"subName": "kucoin1",
		"remarks": "kucoin1"
	},
	{
		"userId": "5cbd31b89c93e9280cd36a0d",
		"subName": "kucoin2",
		"remarks": "kucoin2"
	}
]
```
使用母账号的API访问这个接口获取母账号下所有的子账号信息。

###HTTP请求

**Get /api/v1/sub/user**

### 请求参数
无

### 返回值

字段名称 | 描述
--------- | ------- 
userId | 子账号的用户ID
subName | 子账号的用户名
remarks | 备注信息

###API权限
此端点需要**通用权限**。
##
# 账户

## 账户列表

```json
[{
    "id": "5bd6e9286d99522a52e458de",  //accountId
    "currency": "BTC",  //币种代码
    "type": "main",     //该币种下的账户类型，储蓄（main）账户和交易(trade)账户
    "balance": "237582.04299",  //资金总额
    "available": "237582.032",  //可用金额
    "holds": "0.01099". //冻结金额
},
{
    "id": "5bd6e9216d99522a52e458d6",
    "currency": "BTC",
    "type": "trade",
    "balance": "1234356",
    "available": "1234356",
    "holds": "0"
}]

```
获取账号下所有的账户列表。
<aside class="notice">一个币种对应两个账户，一个储蓄账户，一个交易账户。
储蓄账户（main）会在第一次划转资产时创建，如果未划转过资产则不会有储蓄账户。如果账户不存在，需要[创建账户](#9ec360d41d)</aside>

请在交易之前请先[充值](#fa03c46253)到储蓄账户，再使用[内部资金划转](#c08ac949fb)划转将资金从储蓄账户划转到交易账户。

### HTTP请求
**GET /api/v1/accounts**

### 请求参数

请求参数 | 类型 | 描述
--------- | -------| ------- 
currency | String | [可选] 币种代码](#ebcc9fbb02)
type | String |[可选] 账户类型 **main** 或 **trade**

### 返回值
字段名称 | 描述
--------- | ------- 
id | accountId 账户ID 
currency | 账户对应的币种
type |账户类型 ，**main**（储蓄账户） or **trade**（交易账户）
balance | 账户资金总额 
available | 账户可用的资金 
holds | 账户冻结的资金

###账户类型
对于一个币种而言，一个账号可以拥有两个账户。一个为储蓄账户，一个为交易账户。
储蓄账户和交易账户资金相互划转不需要手续费。

储蓄账户主要用于资金的提现和充值，储蓄账户里面的资金不可以直接用于交易。交易之前需要将资金从储蓄账户转到交易账户。

交易账户主要用于交易。下单扣除的是交易账户里面的资金，交易账户里面的资金不可以直接提现，必须要转到储蓄账户才可以提现。

储蓄账户和交易账户资金划转请参考[内部资金划转](#c08ac949fb)。

###冻结资金
当下单时，您用于下单的资金会被冻结。冻结的资金不可以用作再次下单或者提现。当订单取消或成交后，资金才能解冻回退或解冻支付。


###API权限
此端点需要**通用权限**。

## 单个账户详情
```json
{
    "currency": "KCS", //币种
    "balance": "1000000060.6299", //资金总额
    "available": "1000000060.6299", //可用资金
    "holds": "0" //冻结资金
}
```
此接口返回单个账户的详情。

### HTTP请求
**GET /api/v1/accounts/{accountId}**

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- 
accountId | String | 路径参数，[账户ID](#f0f7ae469d)

### 返回值
字段名称 | 描述
--------- | ------- 
currency | 币种
balance | 账户资金总额
holds | 冻结资金
available | 可用资金

###API权限
此端点需要**通用权限**。



## 创建账户

此接口可以用于创建账户

```json
{
    "id": "5bd6e9286d99522a52e458de" //accountId
}
```

### HTTP请求
**POST /api/v1/accounts**

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- 
type | String | 账户类型，**main** 或 **trade** 
currency | String |[币种代码](#ebcc9fbb02)

### 返回值
字段名称 | 描述
--------- | ------- 
id | 新创建的账户ID -- accountId

### API权限
此端点需要**通用权限**。





## 账户流水记录

此接口返回账户的出入账流水记录。
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

```json
{
	"currentPage": 1,
	"pageSize": 10,
	"totalNum": 2,
	"totalPage": 1,
	"items": [{
			"currency": "KCS", //币种
			"amount": "0.0998", //资金变动值
			"fee": "0", //充值或提现费率
			"balance": "1994.040596", //变动后的资金总额
			"bizType": "withdraw", //业务类型
			"direction": "in", // 出入账方向 in 入账 out 出账
			"createdAt": 1540296039000, // 创建时间
			"context": { // 业务核心参数
				"orderId": "5bc7f080b39c5c03286eef8a",
				"currency": "BTC"
			}
		},
		{
			"currency": "KCS",
			"amount": "0.0998",
			"fee": "0",
			"balance": "1994.140396",
			"bizType": "trade exchange",
			"direction": "in",
			"createdAt": 1540296039000,
			"context": {
				"orderId": "5bc7f080b39c5c03286eef8e",
				"tradeId": "5bc7f080b3949c03286eef8a",
				"symbol": "BTC-USD"
			}
		}
	]
}
```

### HTTP请求
**GET /api/v1/accounts/{accountId}/ledgers**

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- 
accountId | String | 路径参数，[账户ID](#f0f7ae469d)
startAt | long |[可选] 开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选] 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。


### 返回值
字段名称 | 描述
--------- | ------- 
currency | 币种 
amount | 资金变动值
fee | 充值或提现费率
balance | 变动后的资金总额
bizType | 业务类型，比如交易，提现等
direction | 出入账 **out** 或 **in**
createdAt | 创建时间
context | 业务核心参数

###context
如果 **bizType** 是trade exchange，那么 **context** 字段会包含交易的额外信息（订单id，交易id，交易对）。

###API权限
此端点需要**通用权限**。

<aside class="notice">这个接口需要使用分页</aside>

## 账户冻结记录

```json
{
    "currentPage": 1,
    "pageSize": 10,
    "totalNum": 2,
    "totalPage": 1,
    "items": [
        {
            "currency": "ETH", //币种
            "holdAmount": "5083", //冻结金额
            "bizType": "Withdraw", //业务类型
            "orderId": "5bc7f080b39c5c03286eef8e", //资金冻结业务ID
            "createdAt": 1545898567000, //创建时间
            "updatedAt": 1545898567000 //修改时间
        },
        {
            "currency": "ETH",
            "holdAmount": "1452",
            "bizType": "Withdraw",
            "orderId": "5bc7f518b39c5c033818d62d",
            "createdAt": 1545898567000,
            "updatedAt": 1545898567000
        }
    ]
}
```

此接口返回的是在途冻结记录。当下单或申请提现时，会冻结账户资金，生成冻结记录。当订单成交或取消资金会解冻支付或会解冻回退，冻结记录移除。当提现完成，冻结记录移除。

### HTTP请求
**GET /api/v1/accounts/{accountId}/holds**

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
accountId | String | 路径参数，[账户ID](#f0f7ae469d)



### 返回值

字段名称 | 描述
--------- | -------
currency | 币种
holdAmount | 冻结资金
bizType | 业务类型，比如交易，提现 等
orderId | 资金冻结订单ID（只用作唯一标识）
createdAt | 创建时间
updatedAt | 修改时间

###orderId
**orderId** 字段用于下单或提现生成的订单ID，用作唯一标识。

###API权限
此端点需要**通用权限**。

<aside class="notice">这个接口需要使用分页</aside>

## 获取单个子账户信息

```json
{
	"subUserId": "5caefba7d9575a0688f83c45", 
	"subName": "sdfgsdfgsfd",
	"mainAccounts": [{
		"currency": "BTC",
		"balance": "8",
		"available": "8",
		"holds": "0"
	}],
	"tradeAccounts": [{
		"currency": "BTC",
		"balance": "1000",
		"available": "1000",
		"holds": "0"
	}]
}
```

此接口，使用母账号API-KEY，可获取单个子账号的账户信息。

###HTTP请求

**GET /api/v1/sub-accounts/{subUserId}**

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------  
subUserId | String | 路径参数，[子账号的用户Id](#a0bc1cb873)

### 返回值

字段名称 | 描述
--------- | ------- 
subUserId | 子账号的用户Id
subName | 子账号的用户名
currency | 币种
balance | 资金总额
available | 可用资金
holds | 冻结资金
 
###API权限
此端点需要**通用权限**。

## 获取所有子账户信息


```json
[{
		"subUserId": "5caefba7d9575a0688f83c45",
		"subName": "kucoin1",
		"mainAccounts": [{
			"currency": "BTC",
			"balance": "6",
			"available": "6",
			"holds": "0"
		}],
		"tradeAccounts": [{
			"currency": "BTC",
			"balance": "1000",
			"available": "1000",
			"holds": "0"
		}]
	},
	{
		"subUserId": "5caf0e2fd9575a0688f83ceb",
		"subName": "kucoin2",
		"mainAccounts": [{
			"currency": "BTC",
			"balance": "13",
			"available": "13",
			"holds": "0"
		}],
		"tradeAccounts": []
	}
]
```

此接口，使用母账号API-KEY，可获取所有子账号的账户信息。


###HTTP请求

**GET /api/v1/sub-accounts**

### 请求参数

无

### 返回值

字段名称 | 描述
--------- | ------- 
subUserId | 子账号的用户ID
subName | 子账号的用户名
currency | 币种
balance | 资金总额
available | 可用资金
holds | 冻结资金
 
###API权限
此端点需要**通用权限**。

## 子母账号资金划转


```json
{
	"orderId": "5cbd870fd9575a18e4438b9a"
}
```
此接口，用于子母账号之间资金的划转，母账号的储蓄账户支持向子账号的储蓄账户或交易账户划转。


###HTTP请求

**POST /api/v1/accounts/sub-transfer** 

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- 
clientOid | String | Client Order Id，客户端创建的唯一标识，建议使用UUID
currency | String | [币种代码](#ebcc9fbb02)
amount | String | 转账金额，精度为[币种精度](#ebcc9fbb02)正整数倍
direction | String | OUT — 母账号转子账号<br/>IN — 子账号转母账号
accountType | String | [可选] 母账号账户类型**MAIN**
subAccountType | String | 子账号账户类型**MAIN** 或 **TRADE**
subUserId | String | [子账号的用户Id](#a0bc1cb873)

### 返回值

字段名称 | 描述
--------- | ------- 
orderId | 子母账号转账的订单ID，作为唯一标识
 
###API权限
此端点需要**交易权限**。


## 内部资金划转

```json
{
    "orderId": "5bd6e9286d99522a52e458de"
}
```

此接口用于平台内部账户资金划转，用户可以将资金在储蓄账户和交易账户之间免费划转。



### HTTP请求
**POST /api/v1/accounts/inner-transfer**  
<aside class="notice">此接口于2019年08月29日停止使用，请使用下方提供的划转接口。</aside>

###划转指南
账户不能自动创建（只有当一笔资金充值入账时，储蓄账户会自动创建），储蓄账户和交易账户相互划转指南:

- 首先，按需求[创建](#9ec360d41d)一个储蓄账户或交易账户；
- 其次，[获取accountId](#f0f7ae469d)，记录返回的Id（即accountId)；
- 最后，调用[内部资金划转](#c08ac949fb)接口，发起转账请求；
  
### 请求参数

请求参数 | 类型 | 描述
--------- | ------- |  ------- 
clientOid | String | Client Order Id，客户端创建的唯一标识，建议使用UUID
payAccountId | String | 付款方的accountId [账户ID](#f0f7ae469d)
recAccountId | String | 收款方的accountId [账户ID](#f0f7ae469d)
amount | String | 转账金额，精度为[币种精度](#ebcc9fbb02)正整数倍

### HTTP请求
**POST /api/v2/accounts/inner-transfer**
<aside class="notice">推荐使用，于2019年06月05日生效。</aside>
  
### 请求参数

请求参数 | 类型 | 描述
--------- | ------- |  ------- 
clientOid | String | Client Order Id，客户端创建的唯一标识，建议使用UUID
currency | String | [币种代码](#ebcc9fbb02)
from | String |  付款账户类型**main** 或 **trade**
to | String |  收款账户类型**main** 或 **trade**
amount | String | 转账金额，精度为[币种精度](#ebcc9fbb02)正整数倍



### 返回值
字段名称 | 描述
--------- | ------- 
orderId | 内部资金划转的订单ID，作为唯一标识

###API权限
此端点需要**交易权限**。



# 充值

## 申请充值地址

```json
{
	"address": "0x78d3ad1c0aa1bf068e19c94a2d7b16c9c0fcd8b1",
	"memo": "5c247c8a03aa677cea2a251d",   //标签
	"chain": "OMNI"
}
```

此接口可用于申请充值地址

### HTTP请求
**POST /api/v1/deposit-addresses**

### API权限
此端点需要**转账权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- |  ------- 
currency | String | [币种代码](#ebcc9fbb02)

### 返回值
字段名称 | 描述
--------- | ------- 
address | 充值地址
memo | 地址标签，如果返回为空，则该币种没有memo。当您在其他平台申请提现到Kucoin的时候，如果该币种有memo(tag)，需要填写memo，确保能准确入账到您到账户。


## 获取充值地址

```json
{
	"address": "0x78d3ad1c0aa1bf068e19c94a2d7b16c9c0fcd8b1",
	"memo": "5c247c8a03aa677cea2a251d",        //标签
	"chain": "OMNI"
}
```

此接口，可获取某一币种的充值地址，如果返回数据为空，请先[申请充值地址](#9277fb3f66)。

### HTTP请求
**GET /api/v1/deposit-addresses**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | -------  | ------- 
currency | String |[币种代码](#ebcc9fbb02)
chain | String | [可选] 币种的链名。例如，对于USDT，现有的链有OMNI、ERC20、TRC20。默认值为OMNI。这个参数用于区分多链的币种，单链币种不需要。

### 返回值
字段名称 | 描述
--------- | ------- 
address | 充值地址
memo | 地址标签memo(tag)，如果返回为空，则该币种没有memo。对于没有memo的币种，在[提现](#6eaf6b9ae0)的时候不可以传递memo
chain | 币种的链名。例如，对于USDT，现有的链有OMNI、ERC20、TRC20。默认值为OMNI。

## 获取充值列表

```json
{
  "currentPage": 1,
  "pageSize": 5,
  "totalNum": 2,
  "totalPage": 1,
	"items": [{
		"address": "0x5f047b29041bcfdbf0e4478cdfa753a336ba6989",
		"memo": "5c247c8a03aa677cea2a251d",
		"amount": 1,
		"fee": 0.0001,
		"currency": "KCS",
		"isInner": false,
		"walletTxId": "5bbb57386d99522d9f954c5a@test004",
		"status": "SUCCESS",
		"createdAt": 1544178843000,
		"updatedAt": 1544178891000
	}, {
		"address": "0x5f047b29041bcfdbf0e4478cdfa753a336ba6989",
		"memo": "5c247c8a03aa677cea2a251d",
		"amount": 1,
		"fee": 0.0001,
		"currency": "KCS",
		"isInner": false,
		"walletTxId": "5bbb57386d99522d9f954c5a@test003",
		"status": "SUCCESS",
		"createdAt": 1544177654000,
		"updatedAt": 1544178733000
	}]
}
```

此端点，可获取充值分页列表。
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

### HTTP请求
**GET /api/v1/deposits**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- 
currency | String |[可选] [币种代码](#ebcc9fbb02)
startAt | long | [可选] 开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long |  [可选] 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。
status | String | [可选] 状态。可选值: PROCESSING, SUCCESS, FAILURE

### 返回值
字段名称 | 描述
--------- | ------- 
address | 充值地址
memo | memo标记充值地址
amount | 充值金额
fee | 充值手续费
currency | 币种代码
isInner | 是否为平台内部充值
walletTxId | 钱包交易Id
status | 状态
createdAt | 创建时间
updatedAt | 修改时间

<aside class="notice">这个接口需要使用分页</aside>

## 获取V1历史充值列表

```json
{
"currentPage": 1,
"pageSize": 1,
"totalNum": 9,
"totalPage": 9,
"items": [{
"currency": "BTC",
"createAt": 1528536998,
"amount": "0.03266638",
"walletTxId": "55c643bc2c68d6f17266383ac1be9e454038864b929ae7cee0bc408cc5c869e8@12ffGWmMMD1zA1WbFm7Ho3JZ1w6NYXjpFk@234",
"isInner": false,
"status": "SUCCESS"
}]
}
```

此接口，可获取KuCoin V1的充值记录。
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

<aside class="notice">默认查询一个月的数据</aside>

###HTTP请求
**GET /api/v1/hist-deposits**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------  
currency | String | [可选] [币种代码](#ebcc9fbb02)
status | String | [可选] 状态。可选值: PROCESSING, SUCCESS, and FAILURE
startAt | long | [可选]  开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选] 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。 


### 返回值
字段名称 | 描述
--------- | ------- 
amount | 充值金额
currency | 币种代码
isInner | 是否为平台内充值
walletTxId | 钱包交易Id
status | 状态
createAt | 创建时间

<aside class="notice">这个接口需要使用分页</aside>

# 提现

## 获取提现列表

```json
{
  "currentPage": 1,
  "pageSize": 10,
  "totalNum": 1,
  "totalPage": 1,
	"items": [{
	  "id": "5c2dc64e03aa675aa263f1ac",
		"address": "0x5bedb060b8eb8d823e2414d82acce78d38be7fe9",
		"memo": "",
		"currency": "ETH",
		"amount": 1.0000000,
        "fee": 0.0100000,
		"walletTxId": "3e2414d82acce78d38be7fe9",
		"isInner": false,
		"status": "FAILURE",
		"createdAt": 1546503758000,
		"updatedAt": 1546504603000
	}]
}
```

### HTTP请求
**GET /api/v1/withdrawals**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
currency | String | [可选] [币种代码](#ebcc9fbb02)
status | String | [可选]  状态。可选值: PROCESSING, WALLET_PROCESSING, SUCCESS, FAILURE
startAt | long | [可选] 开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选] 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。

### 返回值
字段名称 |  描述
--------- | ------- 
id | 唯一标识
address | 提现地址
memo | 提现地址标识
currency | 币种 
amount | 提现金额
fee | 提现手续费
walletTxId | 钱包交易Id
isInner | 是否为平台内部提现
status | 状态 
createdAt | 创建时间
updatedAt | 修改时间

<aside class="notice">这个接口需要使用分页</aside>

## 获取V1历史提现列表

```json
{
  "currentPage": 1,
  "pageSize": 1,
  "totalNum": 2,
  "totalPage": 2,
	"items": [{
	  "currency": "BTC",
    "createAt": 1526723468,
    "amount": "0.534",
    "address": "33xW37ZSW4tQvg443Pc7NLCAs167Yc2XUV",
    "walletTxId": "aeacea864c020acf58e51606169240e96774838dcd4f7ce48acf38e3651323f4",
    "isInner": false,
    "status": "SUCCESS"
	}]
}

```

此接口，可获取KuCoin V1的提现记录。
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

<aside class="notice">默认查询一个月的数据</aside>

###HTTP请求
**GET /api/v1/hist-withdrawals**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------  
currency | String | [可选] [币种代码](#ebcc9fbb02)
status | String | [可选] 状态。可选值: PROCESSING, SUCCESS, FAILURE
startAt | long | [可选]  开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选] 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。



### 返回值
字段名称 | 描述
--------- | ------- 
amount | 提现金额
currency | 币种
isInner | 是否为平台内部提现
walletTxId | 钱包交易Id
createAt |  创建时间
status | 状态

<aside class="notice">这个接口需要使用分页</aside>

##  获取提现额度

```json
{
	"currency": "KCS",
	"limitBTCAmount": "2.0",
	"usedBTCAmount": "0",
	"limitAmount": "75.67567568",
	"remainAmount": "75.67567568",
	"availableAmount": "9697.41991348",
	"withdrawMinFee": "0.93000000",
	"innerWithdrawMinFee": "0.00000000",
	"withdrawMinSize": "1.4",
	"isWithdrawEnabled": true,
	"precision": 8,   //提现金额精度
	"chain": "OMNI"
}
```

### HTTP请求
**GET /api/v1/withdrawals/quotas**

### API权限
此端点需要**通用权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | ---------
currency | String | [币种代码](#ebcc9fbb02)
chain | String | [可选] 币种的链名。例如，对于USDT，现有的链有OMNI、ERC20、TRC20。默认值为OMNI。这个参数用于区分多链的币种，单链币种不需要。

### 返回值
字段名称 | 描述
--------- | ------- 
currency | 币种
availableAmount | 可提现的金额
remainAmount | 当日剩余可提现的额度
withdrawMinSize | 最小提现金额
limitBTCAmount | 当日剩余可提现的额度，折合为BTC
innerWithdrawMinFee | 内部提现手续费
usedBTCAmount | 当日BTC折合提现
isWithdrawEnabled | 是否可提现
withdrawMinFee | 最小提现金额
precision | 提现的精度
chain | 币种的链名。例如，对于USDT，现有的链有OMNI、ERC20、TRC20。默认值为OMNI。

## 申请提现

```json
{
  "withdrawalId": "5bffb63303aa675e8bbe18f9"
}
```

### HTTP请求
**POST /api/v1/withdrawals**
<aside class="notice">在WEB端可以开启指定收藏地址提现，开启后会校验你的提现地址是否为收藏地址。</aside>

###API权限
此端点需要**转账权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | -------  | -------
currency  | String | 币种
address   | String | 提现地址
amount | number | 提现总额，必须为提现精度的正整数倍
memo   | String | [可选]  提现[地址标识](#b3114995fd)，没有memo(tag)的币种，不可传这个字段。
isInner | boolean | [可选] 是否为平台内部提现。默认为false
remark | String | [可选] 备注信息
chain | String | [可选] 针对一币多链的币种，可通过chain获取币种详情。比如， USDT存在的链有 OMNI, ERC20, TRC20。

### 返回值
字段名称 | 描述
--------- | ------- 
withdrawalId | 提现Id 唯一标识

KuCoin支持外扣手续费和内扣手续费。当您的储蓄账户的余额足以支持支付提现手续费时，首先从您的储蓄账户中扣除手续费，反之，从您的提现金额中扣除手续费。

比如，您从KuCoin提现 1 个BTC(提现手续费为：0.0001BTC)，如果您储蓄账户里的余额不支持支付手续费，系统将会自动从您的提现金额中扣除手续费，您实际到账金额为0.9999个BTC。


## 取消提现

提现状态为提现中才可以取消。


### HTTP请求
**DELETE /api/v1/withdrawals/{withdrawalId}**

###API权限
此端点需要**转账权限**。

### 请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
withdrawalId | String | 路径参数，[提现Id](#c46f4b3b8e) 唯一标识

# 交易模块

以下请求需要校验[签名](#8ba46c43fe)。


# 订单

## 下单

```json
{
  "orderId": "5bd6e9286d99522a52e458de"
}
```

订单有两种类型：
限价单（**limit**）: 指定价格和数量进行交易。
市价单(**market**) : 指定资金或数量进行交易。

在下单前，请确保您的[交易账户](#f0f7ae469d)有足够的资金。一旦下单成功，您下单的金额会被冻结。[冻结金额](#HOLDS)的多少取决于您下单的类型和具体的请求参数。

请悉知，当您的订单进入买卖盘，系统会提前扣除[订单的手续费](#6a30a471cf)。

在下单之前，请充分了解每一个[交易对](#a17b4e2866)的参数的意义。


**请求体中的JSON字符串中不要有多余的空格**

###下单限制

对于一个账号，每一个交易对最大撮合订单数量 **50** （包含止损单）。

### HTTP 请求

**POST /api/v1/orders**

###API权限
此端点需要**交易权限**。

### 请求参数

下单公有的请求参数

请求参数 | 类型 | 描述
--------- | -------  | ---------
clientOid | String |  Client Order Id，客户端创建的唯一标识，建议使用UUID
side      | String |  **buy**（买） 或 **sell**（卖） 
symbol    | String |  [交易对](#a17b4e2866) 比如，ETH-BTC                    
type      | String | [可选] 订单类型 **limit** 和  **market** (默认为 **limit**)
remark    | String | [可选] 下单备注，长度不超过100个字符（UTF-8）
stop      | String | [可选] 止盈止损单，触发条件， **loss**（小于等于） 或 **entry**（大于等于）需要设定触发价格。
stopPrice | String | [可选] 触发价格，只有设定了止盈止损触发条件就必须要设定触发价格。
stp       | String | [可选] [自成交保护](#80920cd667)（self trade prevention）**CN**, **CO**, **CB** , **DC**

#### **limit** 限价单额外所需请求参数

请求参数 | 类型 | 描述
--------- | -------  | ---------
price       | String  | 指定货币的价格                             
size        | String  | 指定货币的数量                      
timeInForce | String  | [可选] 订单过期策略 **GTC**, **GTT**, **IOC**, **FOK** (默认为**GTC**)
cancelAfter | long    | [可选] **n** 秒之后取消，订单过期策略为 **GTT**                   
postOnly    | boolean | [可选] 只挂单的标识, 当订单过期策略为 **IOC** 或 **FOK** 时无效
hidden      | boolean | [可选] 是否隐藏（买卖盘中不展示）             
iceberg    | boolean | [可选] 冰山单中是否仅显示订单的可见部分
visibleSize | String  | [可选] 冰山单最大的展示数量  

#### **market** 市价单额外所需请求参数

请求参数 | 类型 | 描述
--------- | ------- | ------- | ---------
size | String | 否（size和funds 二选一） | 下单数量
funds | String |  否（size和funds 二选一）| 下单资金

* 下市价单，要么指定买卖数量或资金买卖指定的商品/货币。

###术语解释

###交易对(Symbol)

交易对必须是KuCoin支持的[交易对](#a17b4e2866)。

###Client Order Id(clientOid)

clientOid字段必须是唯一的Id，由客户端创建(推荐使用UUID)。这个字段会在获取订单信息时返回，您可以用clientOid来标识您的订单。

clientOid不同于服务端创建的orderId(下单后返回的orderId)。您同时需要记录服务端创建的orderId，以便获取订单的更新状态。

<aside class="notice">请不要使用同一个clientOid发起请求，clientOid最长不超过40个英文字符</aside>

###订单类型(type)

当下单的时候，您需要定义订单类型。不同的订单类型需要不同的请求参数，同时也会影响到撮合引擎的执行。如果没有传递订单类型这个字段，默认为 **限价单**（limit)。

**限价单（limit order）** 是默认的订单类型。当您下限价单时，需要指定 **price** （价格）和 **size** （数量）。size是指您想要买卖货币的数量，price是指单位计价币种的价格。限价单会根据您下单的价格、数量和市场条件来进行撮合。当买方出价大于等于卖方或卖方出价小于等于买方价格，则会按照市价单撮合可成交部分，如果订单不能立马成交（吃单），那么订单会进入买卖盘中，直到订单被成交或被取消。



**市价单(market order)**与限价单不同，市价单不确定成交价格，您可以指定具体的**funds**(资金)或**amount**(数量)它会立即与买卖盘的挂单成交。当您下一个市价单时，无需指定价格就可以买卖特定数量或资金的数字货币。当您下市价单时，在市价买单中如果您指定资金，我们会冻结您的下单资金+对应的taker手续费，如果您指定数量，我们将冻结全部数量，在市价卖单中，如果您指定资金，我们将冻结全部金额，如果您指定数量我们将冻结您的下单数量。请注意，市价单作为一个taker，会按照taker收取手续费。

###止盈止损单(STOP ORDER)
当您下一个止盈止损单时，请设置一个触发价（stopPrice)，当发生交易并且交易价格达到触发价后，会生成一个订单（限价/市价），并立即进行撮合。触发顺序为价格优先，然后时间优先。
**stop: 'loss'(止损):** 当最新交易价格小于等于**stopPrice**时成交。

**stop: 'entry'(止盈):** 当最新交易价格大于等于**stopPrice**时成交。

最新交易价格是指最新成交价格，这个价格可以在最新[撮合执行数据](#c7f054198c)里面获取。注意，由于Websocket消息有丢失的可能，无法接收所有撮合执行数据。

当您下一个止损单时，系统会提前冻结您的交易账户资金。所以，**当您下一个止损市价单时，我们推荐您使用金额下单**。

###价格(Price)
下限价单时，price 必须以交易对的[价格增量 priceIncrement](#a17b4e2866)为基准，价格增量是交易对的价格的精度。比如，对BTC-USDT 这个交易对, 它的 priceIncrement 为0.00001000，那么你下单的 price 不可以小于0.00001000。您下单的价格必须为 priceIncrement 的正整数倍，否则下单时会报错，invalid prioceIncrement。

###数量(Size)
下限价单时，size 是指交易对的交易对象(即写在靠前部分的资产名)的数量。size 必须以交易对中的[数量增量 baseIncrement](#a17b4e2866)为基准，数量增量是交易对的数量的精度。下单的 size 为 baseIncrement 的正整数倍并且必须在 baseMinSize 和 baseMaxSize 之间。

###资金(Funds)
下市价单时，funds 字段是指交易对的定价资产(即写在靠后部分资产名)的资金。funds 必须以交易对中的[资金增量quoteIncrement](#a17b4e2866)为基准，资金增量是交易对的资金的精度。下单的 funds 为 quoteIncrement 的正整数倍且必须在 quoteMinSize 和 quoteMaxSize 之间。

###订单过期策略(TimeInForce)
订单过期策略可以控制订单的生命周期，订单过期策略有以下四种。

| 缩写   | 全称        | 含义         |
| ----  | ---------   | ----------  |
| GTC   | Good Till Canceled |主动取消才过期|
| GTT   | Good Till Time  |指定时间后过期|
| IOC   | Immediate Or Cancel |立即成交可成交的部分，然后取消剩余部分，不进入买卖盘|
| FOK   | Fill Or Kill |如果下单不能全部成交，则取消|


* 注意，成交也包含自成交。

###只挂单(PostOnly)
postOnlys只是一个标识，如果下单有能立即成交的对手方，则取消。

###隐藏单和冰山单(Hidden & Iceberg)

当下限价单的时候，可指定 **hidden** 或 **iceberg** 这两个字段。（冰山单是一种特殊的隐藏单）。

当您下隐藏单时，需要指定**hidden**为true，您的订单不会展示在买卖盘中，但是其他用户在成交历史记录中可以看见。

冰山单与隐藏单不同之处是，冰山单分为可见和隐藏两个部分。下冰山单，需要指定**iceberg**为true，且设定**visibleSize**的大小。买卖盘中仅可见visibileSize数量，当visibleSize被撮合之后，从隐藏部分中填充，直到可见和隐藏都为0则结束。冰山单最大可拆分为**20**等份，根据您设置的visibleSize进行拆分。也就是说，您的冰山单最小可见数量是总订单量的1/20。

冰山单和隐藏单不是默认为 taker 订单。当冰山单或隐藏单进入生命周期，并且立即被撮合成交，那么订单为taker。但是，如果订单没有被撮合，那么这个订单被看作 maker，等待被成交。成交后，这个订单就是 maker 订单了，但是我们只收取taker的手续费。



**注意**: 
- 最小可见数量必须大于[最小下单数量](#a17b4e2866)。
- 对于**隐藏单**和**冰山单**，系统收取taker费用。
- 如果同时设定 **iceberg** 和 **hidden** 为true，会作为冰山单处理。 

###冻结策略(Hold)
对于限价买单，我们会从您的资金里面冻结您买单的金额(price * size)。同样，对于限价卖单，我们也会冻结您卖单的资产。在成交那一刻评估实际的手续费。如果您取消了一个部分成交或未成交的订单，那么剩余金额会解冻会退到您的账户。
对于市价买/卖单，需要指定**funds(资金)**，我们会根据funds来冻结您账户里的资金。如果只指定了**size**，在成交或取消之前，您的账户所有资金会被冻结（通常冻结时间非常短）。


###自成交保护(SelfTradePrevention)

**stp(SelfTradePrevention)**，自成交保护，默认为空。当您下单时指定了 **STP**，您的订单将不会发生自成交。如果您下单前没有指定 **STP**，您的订单可能会被自己的订单成交。


**市价单现不支持 DC**，当*timeInForce* 为**FOK**， 那么stp会指定为**CN**。

| 缩写 | 全称              | 含义                        |
| ---- | ---------------  | ----------------------------- |
| DC   | Decrease and Cancel  | 数量少的一方取消，数量多的一方减去少的一方的数量，继续执行撮合
| CO   | Cancel old           |取消旧的订单
| CN   | Cancel new           |取消新的订单
| CB   | Cancel both          |双方都取消

###订单生命周期(ORDER LIFECYCLE)

下单请求，要么被拒绝(余额不足(insufficient funds)，参数不合法(invalid parameters)等)，要么请求成功，进入撮合引擎。
返回code为**200**意味着，下单成功，订单状态为**active**。订单会根据价格和市场条件来成交，要么全部成交，要么部分成交，没有成交的订单状态为**open**。直到订单被成交或被取消，订单状态为**done**
用户可以订阅市场数据，通常使用 orderId 这个字段来获取自己的订单信息。


### 返回值
字段名称 | 描述
--------- | ------- 
orderId | 订单Id 唯一标识
下单成功后，会返回一个orderId字段，意味这订单顺利进入撮合引擎。

<aside class="notice">订单状态为open，订单不会过期，直到订单被成交或被取消。</aside>

## 单个撤单

```json
{
     "cancelledOrderIds": [
      "5bd6e9286d99522a52e458de"   //orderId
    ]
}
```

此端点，可以取消一个订单。

一旦系统收到取消请求，您将收到返回值。取消请求将由匹配引擎按顺序处理。要知道请求是否已处理（成功与否），您可以检查订单状态或推送更新的消息。


### HTTP请求
**DELETE /api/v1/orders/{orderId}**

### 请求参数

请求参数 | 类型 | 描述
--------- | -------  | -------
orderId | String | 路径参数，[订单Id](#23e02e24af) 唯一标识

### 返回值

字段名称 | 描述
--------- | ------- 
cancelledOrderIds | 取消的订单id

### API权限
此端点需要**交易权限**。

<aside class="notice">The <b>orderId</b> 是服务器生成的订单唯一标识，不是客户端生成的clientOId</aside>

### 撤单被拒
如果订单不能撤销（已经成交或已经取消），会返回错误信息，可根据返回的msg获取原因。

## 全部撤单

```json
{
   "cancelledOrderIds": [
      "5c52e11203aa677f33e493fb",  //orderId
      "5c52e12103aa677f33e493fe",
      "5c52e12a03aa677f33e49401",
      "5c52e1be03aa677f33e49404",
      "5c52e21003aa677f33e49407",
      "5c6243cb03aa67580f20bf2f",
      "5c62443703aa67580f20bf32",
      "5c6265c503aa676fee84129c",
      "5c6269e503aa676fee84129f",
      "5c626b0803aa676fee8412a2"
    ]
}
```
此接口，可以取消所有状态为**open**的订单，返回值是是已取消订单的ID列表。


### HTTP请求
**DELETE /api/v1/orders**

###示例
**DELETE /api/v1/orders?symbol=ETH-BTC**

###API权限
此端点需要**交易权限**。

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | ---------
symbol | String | [可选] 取消指定[交易对](#a17b4e2866)的open订单

### 返回值

字段名称 | 描述
--------- | ------- 
cancelledOrderIds | 取消的订单id

## 获取订单列表

```json
{
    "currentPage": 1,
    "pageSize": 1,
    "totalNum": 153408,
    "totalPage": 153408,
    "items": [
      {
        "id": "5c35c02703aa673ceec2a168",
        "symbol": "BTC-USDT",
        "opType": "DEAL",
        "type": "limit",
        "side": "buy",
        "price": "10",
        "size": "2",
        "funds": "0",
        "dealFunds": "0.166",
        "dealSize": "2",
        "fee": "0",
        "feeCurrency": "USDT",
        "stp": "",
        "stop": "",
        "stopTriggered": false,
        "stopPrice": "0",
        "timeInForce": "GTC",
        "postOnly": false,
        "hidden": false,
        "iceberg": false,
        "visibleSize": "0",
        "cancelAfter": 0,
        "channel": "IOS",
        "clientOid": "",
        "remark": "",
        "tags": "",
        "isActive": false,
        "cancelExist": false,
        "createdAt": 1547026471000
      }
    ]
 }
```

此接口，可获取订单列表
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

### HTTP请求
**GET /api/v1/orders**


### 示例
请求 **/api/v1/orders?status=active** 以获取所有活跃订单

###API权限
此端点需要**通用权限**。

###请求参数

请求参数 | 类型 | 描述
--------- | -------  | ---------
status | String | [可选] **active（活跃）** 或 **done（完成）** 默认为done。只返回指定状态的订单信息
symbol |String| [可选] 只返回指定[交易对](#a17b4e2866)的订单信息
side | String | [可选] **buy（买）** 或 **sell（卖）** 
type | String | [可选] 订单类型: **limit（限价单）**, **market(市价单)**, **limit_stop(限价止盈止损单)**, **market_stop（市价止盈止损单）** 
startAt | long | [可选]  开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选]  结束时间，[Unix 时间](http://en.wikipedia.org/wikiUnix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。

<aside class="notice">这个接口需要使用分页</aside>

### 返回值

字段名称 | 描述
--------- | ------- 
id | 订单id，订单唯一标识
symbol | 交易对
opType |  操作类型: DEAL(挂买卖单), CANCEL(撤销)
type | 订单类型
side | 买或卖
price |  成交价格
size |  下单数量
funds | 下单金额
dealFunds |  成交额
dealSize | 成交数量
fee | 手续费
feeCurrency | 计手续费币种
stp |  自成交保护
stop |  止盈止损类型， entry:止盈; loss:止损
stopTriggered |  是否触发止盈止损
stopPrice |  止盈止损触发价格
timeInForce | 订单过期策略
postOnly | 是否为只挂单
hidden | 是否为隐藏单
iceberg | 是否为冰山单
visibleSize | 冰山单在买卖盘可见数量
cancelAfter | timeInForce 为 GTT n秒后过期
channel | 下单来源
clientOid | 客户端生成的标识
remark | 订单说明
tags | 订单标签
isActive | 订单状态是否为active
cancelExist | 订单是否存在取消记录
createdAt | 创建时间

### 订单状态和结算
在买卖盘中的**open**的订单状态为**active**，从买卖盘中移除的订单标记为**done**。

订单簿中的未结订单标记为活动状态。订单簿上不再有订单，将标记为已完成状态。订单完成和结算之间有一个空窗期。所有订单明细都已经成交并且还有冻结金额的话，会做冻结回退。


当您查询订单时，您可以搜索任何一种状态的订单，如果您没有指定status，那么系统默认返回所有状态为**done**的订单。


**查询时间范围**
查询**active**订单，没有时间范围限制，但是查询**done**订单，您只能获取到一周以内的数据(即开始和结束时间范围不能超过24*7小时)。如果超过了一周的时间，系统会提示您超过查询时间限制范围。如果查询订单只指定了开始时间并未指定结束时间，系统默认返回一周的数据，反之亦然。


取消订单的历史记录仅保留**一个月**。您将无法查询一个月以前已取消的订单。




###订单轮询(Polling)
对于高频交易的客户，建议您在本地维护一份自己的**open**订单，并且使用市场数据流来更新自己的订单信息。您应该在您开始交易前，轮训查询下本地**open**订单的当前状态。


<aside class="notice">根据市场条件，open的订单可能会在请求和响应之间，状态发生改变。</aside>

## 获取V1历史订单列表

```json
{
    "currentPage": 1,
    "pageSize": 1,
    "totalNum": 1,
    "totalPage": 1,
    "items": [
      {
        "symbol": "SNOV-ETH",
        "dealPrice": "0.0000246",
        "dealValue": "0.018942",
        "amount": "770",
        "fee": "0.00001137",
        "side": "sell",
        "createdAt": 1540080199
      }
    ]
 }
```

此接口，可获取KuCoin V1历史订单列表
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

<aside class="notice">默认查询一个月的订单数据</aside>

###HTTP请求
**GET /api/v1/hist-orders**

###API权限
此端点需要**通用权限**。

###请求参数

请求参数 | 类型 | 描述
--------- | -------  | --------- 
symbol |String| [可选] 只返回指定[交易对](#a17b4e2866)的订单信息
side | String | [可选] **buy（买）** 或 **sell（卖）** 
startAt | long | [可选]  开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选]  结束时间，[Unix 时间](http://en.wikipedia.org/wikiUnix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。

### 返回值

字段名称 | 描述
--------- | ------- 
symbol | 交易对
dealPrice |  成交价格
dealValue | 成交额
amount | 成交量
fee |  手续费费
side |  买或卖
createdAt | 创建时间
<aside class="notice">这个接口需要使用分页</aside>

## 最近订单记录

```json
{
    "currentPage": 1,
    "pageSize": 1,
    "totalNum": 153408,
    "totalPage": 153408,
    "items": [
      {
        "id": "5c35c02703aa673ceec2a168",
        "symbol": "BTC-USDT",
        "opType": "DEAL",
        "type": "limit",
        "side": "buy",
        "price": "10",
        "size": "2",
        "funds": "0",
        "dealFunds": "0.166",
        "dealSize": "2",
        "fee": "0",
        "feeCurrency": "USDT",
        "stp": "",
        "stop": "",
        "stopTriggered": false,
        "stopPrice": "0",
        "timeInForce": "GTC",
        "postOnly": false,
        "hidden": false,
        "iceberg": false,
        "visibleSize": "0",
        "cancelAfter": 0,
        "channel": "IOS",
        "clientOid": "",
        "remark": "",
        "tags": "",
        "isActive": false,
        "cancelExist": false,
        "createdAt": 1547026471000
      }
    ]
 }
```
此接口，可获取最近24小时的1000条订单数据。
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

### HTTP请求
**GET /api/v1/limit/orders**

### 请求参数
不需要传递参数，默认返回最近1000条。

### 返回值

字段名称 | 描述
--------- | ------- 
id | 订单id，订单唯一标识
symbol | 交易对
opType |  操作类型: DEAL(挂买卖单), CANCEL(撤销)
type | 订单类型
side | 买或卖
price |  成交价格
size |  成交数量
funds | 下单金额
dealFunds |  成交额
dealSize | 成交数量
fee | 手续费
feeCurrency | 计手续费币种
stp |  自成交保护
stop |  止盈止损类型， entry:止盈; loss:止损
stopTriggered |  是否触发止盈止损
stopPrice |  止盈止损触发价格
timeInForce | 订单过期策略
postOnly | 是否为只挂单
hidden | 是否为隐藏单
iceberg | 是否为冰山单
visibleSize | 冰山单在买卖盘可见数量
cancelAfter | timeInForce 为 GTT n秒后过期
channel | 下单来源
clientOid | 客户端生成的标识
remark | 订单说明
tags | 订单标签
isActive | 订单状态是否为active
cancelExist | 订单是否存在取消记录
createdAt | 创建时间


###API权限
此端点需要**通用权限**。

<aside class="notice">此端点需要使用分页</aside>


<aside class="spacer4"></aside>
<aside class="spacer2"></aside>

## 单个订单详情

```json
{
    "id": "5c35c02703aa673ceec2a168",
    "symbol": "BTC-USDT",
    "opType": "DEAL",
    "type": "limit",
    "side": "buy",
    "price": "10",
    "size": "2",
    "funds": "0",
    "dealFunds": "0.166",
    "dealSize": "2",
    "fee": "0",
    "feeCurrency": "USDT",
    "stp": "",
    "stop": "",
    "stopTriggered": false,
    "stopPrice": "0",
    "timeInForce": "GTC",
    "postOnly": false,
    "hidden": false,
    "iceberg": false,
    "visibleSize": "0",
    "cancelAfter": 0,
    "channel": "IOS",
    "clientOid": "",
    "remark": "",
    "tags": "",
    "isActive": false,
    "cancelExist": false,
    "createdAt": 1547026471000
 }
```

此接口，可以通过订单id获取单个订单信息。

### HTTP请求
**GET /api/v1/orders/{orderId}**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
orderId | String | 路径参数，[订单Id](#23e02e24af) 唯一标识

### 返回值

字段名称 | 描述
--------- | ------- 
id | 订单id，订单唯一标识
symbol | 交易对
opType |  操作类型: DEAL(挂买卖单), CANCEL(撤销)
type | 订单类型
side | 买或卖
price |  成交价格
size |  成交数量
funds | 下单金额
dealFunds |  成交额
dealSize | 成交数量
fee | 手续费
feeCurrency | 计手续费币种
stp |  自成交保护
stop |  止盈止损类型， entry:止盈; loss:止损
stopTriggered |  是否触发止盈止损
stopPrice |  止盈止损触发价格
timeInForce | 订单过期策略
postOnly | 是否为只挂单
hidden | 是否为隐藏单
iceberg | 是否为冰山单
visibleSize | 冰山单在买卖盘可见数量
cancelAfter | timeInForce 为 GTT n秒后过期
channel | 下单来源
clientOid | 客户端生成的标识
remark | 订单说明
tags | 订单标签
isActive | 订单状态是否为active
cancelExist | 订单是否存在取消记录
createdAt | 创建时间


###API权限
此端点需要**通用权限**。


<aside class="notice">根据市场条件，open的订单可能会在请求和响应之间，状态发生改变。</aside>
<aside class="spacer4"></aside>
<aside class="spacer2"></aside>

# 成交明细

## 成交记录

```json
{
    "currentPage":1,
    "pageSize":1,
    "totalNum":251915,
    "totalPage":251915,
    "items":[
        {
            "symbol":"BTC-USDT",
            "tradeId":"5c35c02709e4f67d5266954e",
            "orderId":"5c35c02703aa673ceec2a168",
            "counterOrderId":"5c1ab46003aa676e487fa8e3",
            "side":"buy",
            "liquidity":"taker",
            "forceTaker":true,
            "price":"0.083",
            "size":"0.8424304",
            "funds":"0.0699217232",
            "fee":"0",
            "feeRate":"0",
            "feeCurrency":"USDT",
            "stop":"",
            "type":"limit",
            "createdAt":1547026472000
        }
    ]
}
```

此接口，可获取最近的成交明细列表
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

### HTTP请求
**GET /api/v1/fills**

###API权限
此端点需要**通用权限**。

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
orderId | String |[可选] 查询该[订单Id](#23e02e24af) 的成交明细（如果指定了orderId，请忽略其他查询条件）
symbol | String |[可选] 查询指定[交易对](#a17b4e2866)的成交明细
side | String | [可选] **buy（买）** 或 **sell（卖）** 
type | String | [可选] 订单类型: **limit（限价单）**, **market(市价单)**, **limit_stop(限价止盈止损单)**, **market_stop（市价止盈止损单）** 
startAt | long | [可选]  开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | [可选]  结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。

**查询时间范围**
您只能获取到一周以内的数据(即开始和结束时间范围不能超过24*7小时)。如果超过了一周的时间，系统会提示您超过查询时间限制范围。如果查询订单只指定了开始时间并未指定结束时间，系统默认返回一周的数据，反之亦然。

### 返回值

字段名称 | 描述
--------- | ------- 
symbol | 交易对
tradeId |  交易Id
orderId | 订单Id
counterOrderId |  对手方订单Id
side | 买或卖
forceTaker | 是否强制作为taker处理
liquidity | 流动性: taker 或 maker
price |  成交价格
size |  成交数量
funds | 成交额
fee |  手续费
feeRate | 手续费率
feeCurrency | 计手续费币种
stop |  止盈止损类型，entry:止盈; loss:止损
type |  订单类型limit 或 market
createdAt |  创建时间

**结算**
结算分为两部分，一部分是成交结算，一部分是费用结算。当撮合完成后，这些数据将立即更新到我们的数据存储区。一旦数据被更新，系统将启动结算并从您的预冻结资金中进行扣除。

**手续费**
KuCoin交易引入市场领先的撮合引擎系统并将下单用户分为taker和maker。taker作为市场深度的提取者我们会收取较高的手续费，而maker作为市场深度的提供者，我们会收取较低的手续费甚至负手续费（您会获得平台补贴）。
 
当您在KuCoin交易市场的某一个交易对下创建一个订单时，为保证您的订单能在市场上成交，我们会按照taker费用预冻结您的资金（这是因为我们无法预估您的订单将以哪种形式成交），请注意您进入买卖盘的订单资金会预扣除手续费。

假设您的订单是市价单，我们将收取您taker费用。

假设您的订单是限价单，当您下单后在撮合引擎中被立即撮合，我们将收取您taker费用，而如果您的订单没有被立即撮合或有部分剩余未被撮合都会进入买卖盘，进入买卖盘的订单在未被取消前成交都会收取您maker手续费。

进入撮合后与对手盘订单撮合，当指令订单剩余金额为0，交易完成，如果剩余资金不足以购买最低数量（0.00000001）的商品，则取消指令订单。

如果您的订单作为maker被成交，我们会将剩余预冻结的taker费用返还给您。

但需要注意的是，当您创建了一个隐藏委托/冰山委托订单时，即使它未被撮合引擎立即成交而被被动成交，仍然会收取taker费用。


举例：

以BTC/USDT为例，假设您想市价买入1BTC，手续费率为0.1%，市场买卖盘数据如下：

| Price（USDT） | Size（BTC） | Side |
| ------------- | ----------- | ---- |
| 4200.00       | 0.18412309  | sell |
| 4015.60       | 0.56849308  | sell |
| 4011.32       | 0.24738383  | sell |
| 3995.64       | 0.84738383  | buy  |
| 3988.60       | 0.20484000  | buy  |
| 3983.85       | 1.37584908  | buy  |

 当您下一个买入市价单时，市场会立即成交，成交明细将分为3笔，如下图所示：

| Price（USDT） | Size（BTC） | Fee（BTC） |
| ------------- | ----------- | ---------- |
| 4011.32       | 0.24738383  | 0.00024738 |
| 4015.60       | 0.56849308  | 0.00056849 |
| 4200.00       | 0.18312409  | 0.00018312 |

###流动性（Liquidity）
从**liquidity** 这个字段，可以看出这笔成交是市场深度的提取者taker还是提供者maker。


<aside class="notice">这个接口需要使用分页</aside>

## 最近成交记录

```json
{
    "currentPage":1,
    "pageSize":1,
    "totalNum":251915,
    "totalPage":251915,
    "items":[
        {
            "symbol":"BTC-USDT",
            "tradeId":"5c35c02709e4f67d5266954e",
            "orderId":"5c35c02703aa673ceec2a168",
            "counterOrderId":"5c1ab46003aa676e487fa8e3",
            "side":"buy",
            "liquidity":"taker",
            "forceTaker":true,
            "price":"0.083",
            "size":"0.8424304",
            "funds":"0.0699217232",
            "fee":"0",
            "feeRate":"0",
            "feeCurrency":"USDT",
            "stop":"",
            "type":"limit",
            "createdAt":1547026472000
        }
    ]
}
```

此接口，可以获取最近24小时1000条成交明细的列表
返回值是[分页](#88b6b4f79a)后的数据，根据时间降序排序，您可以获取到最新的数据。

<aside class="notice">这个接口需要使用分页</aside>

### HTTP请求
**GET /api/v1/limit/fills**

###API权限
此端点需要**通用权限**。

### 请求参数
不需要传递参数，默认返回最近1000条。

### 返回值

字段名称 | 描述
--------- | ------- 
symbol | 交易对
tradeId |  交易Id
orderId | 订单Id
counterOrderId |  对手方订单Id
side | 买或卖
forceTaker | 是否强制作为taker处理
liquidity | 流动性: taker 或 maker
price |  成交价格
size |  成交数量
funds | 成交额
fee |  手续费
stop |  止盈止损类型， entry:止盈; loss:止损
type |  订单类型，limit 或 market
createdAt |  创建时间

<aside class="spacer4"></aside>
<aside class="spacer2"></aside>

# 市场数据

市场数据是公共的，不需要验证签名。

# 交易对 & 行情快照

## 交易对列表

```json
[
  {
    "symbol": "BTC-USDT",
    "name": "BTC-USDT",
    "baseCurrency": "BTC",
    "quoteCurrency": "USDT",
    "baseMinSize": "0.00000001",
    "quoteMinSize": "0.01",
    "baseMaxSize": "10000",
    "quoteMaxSize": "100000",
    "baseIncrement": "0.00000001",
    "quoteIncrement": "0.01",
    "priceIncrement": "0.00000001",
    "feeCurrency": "USDT",
    "enableTrading": true
  }
]
```

此接口，可获取交易对列表。如果您想获取更多交易对的市场信息，可在[全局行情快照](#f3027c9902中获取)。


### HTTP请求
**GET /api/v1/symbols**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
market | String | [可选] [交易市场](#b8f118fefc): BTC, ETH, KCS, SC, NEO

### 返回值

字段名称 | 描述
--------- | ------- 
symbol | 交易对唯一标识码，重命名后不会改变
name |  交易对名称，重命名后会改变
baseCurrency | 商品货币，指一个交易对的交易对象，即写在靠前部分的资产名
quoteCurrency |  计价币种，指一个交易对的定价资产，即写在靠后部分资产名
baseMinSize | 下单，size的最小值
quoteMinSize |  下市价单，funds的最小值
baseMaxSize |  下单，size的最大值
quoteMaxSize |  下市价单，funds的最大值
baseIncrement |  数量增量
quoteIncrement | 市价单：资金增量，funds必须为资金增量的整数倍
priceIncrement |  限价单：价格增量，price必须为价格增量的整数倍
feeCurrency | 交易计算手续费的币种
enableTrading |  是否可以用于交易

- **baseMinSize** 和 **baseMaxSize** 这两个字段规范了下单size的最小值和最大值。
- **priceIncrement** 字段规范了下单的price的最小值和价格增量。

下单的price必须为必须是价格增量的整数倍（如果增量为 0.01，下单价格是0.001或0.021的请求会被拒绝，返回invalid priceIncrement）

**priceIncrement** 和 **quoteIncrement** 以后可能会调整，调整前我们会提前以邮件和全站通知的方式进行通知。

<aside class="notice">返回值中的symbol一旦生成，永远不会改变。但是，base/quote 的 min/max sizes 和 base/quote/price increments 以后可能会变更</aside>

## 行情快照

```json
//Get Ticker
{
    "sequence": "1550467636704",
    "bestAsk": "0.03715004",
    "size": "0.17",
    "price": "0.03715005",
    "bestBidSize": "3.803",
    "bestBid": "0.03710768",
    "bestAskSize": "1.788",
    "time": 1550653727731

}
```


此接口，会返回level-1市场行情快照，买/最佳卖一价，买/卖一数量，最近成交价，最近成交数量。

### HTTP请求
**GET /api/v1/market/orderbook/level1**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值
字段名称 | 描述
--------- | ------- 
sequence | 序列号
bestAsk |  最佳卖一价
size | 最新成交数量
price |  最新成交价格
bestBidSize | 最佳买一数量
bestBid |  最佳买一价
bestAskSize |  最佳卖一数量
time |  时间戳


<aside class="spacer2"></aside>


## 全局行情快照

```json
{
    "time": 1550653727731,
    "ticker": [
      {
        "symbol": "LOOM-BTC",
        "buy": "0.00001191",
        "sell": "0.00001206",
        "changeRate": "0.057",
        "changePrice": "0.00000065",
        "high": "0.0000123",
        "low": "0.00001109",
        "vol": "45161.5073",
        "last": "0.00001204"
      },
      {
        "symbol": "BCD-BTC",
        "buy": "0.00018564",
        "sell": "0.0002",
        "changeRate": "-0.0753",
        "changePrice": "-0.00001522",
        "high": "0.00021489",
        "low": "0.00018351",
        "vol": "72.99679763",
        "last": "0.00018664"
      }
    ]
  }
```

此接口，可获取所有交易对的tickers(包含24h成交量)

### HTTP请求
**GET /api/v1/market/allTickers**

### 返回值
字段名称 | 描述
--------- | ------- 
symbol | 交易对
buy |  最佳买一价
sell | 最佳卖一价
changeRate |  涨跌幅
changePrice | 涨跌价
high |  最高价
low |  最低价
vol |  以基础币种计量的交易量
last |  最新成交价
<aside class="spacer8"></aside>

## 24小时统计

```json
//Get 24hr Stats
{
    "symbol": "ETH-BTC",    // 交易对
    "high": "0.03736329",   // 24h最高价 
    "vol": "2127.286930263025",  // 24h成交量
    "volValue": "43.58567564",  // 24h成交金额
    "last": "0.03713983",   // 最新成交价
    "low": "0.03651252",    // 24h最低价
    "buy": "0.03712118",    // 最佳买一价
    "sell": "0.03713983",   // 最佳卖一价
    "changePrice": "0.00037224",  //24h 涨跌价
    "averagePrice": "8699.24180977",//昨日24小时平均成交价格
    "time": 1550847784668,  //时间戳
    "changeRate": "0.0101" // 24h涨跌幅
}
```  

此接口，可获取指定交易对的最近24小时的ticker


### HTTP请求
**GET /api/v1/market/stats**

###请求参数

请求参数 | 类型 | 描述
--------- | -------| -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值

字段名称 | 描述
--------- | ------- 
symbol | 交易对
high | 24h最高价
vol | 24h成交量，以基础币种计量的交易量
volValue | 24h 成交金额
last | 最新成交价
low |  24h最低价
buy |  最佳买一价
sell | 最佳卖一价
changeRate |  24h涨跌幅
averagePrice | 昨日24小时平均成交价格
changePrice | 24h涨跌价格
time |  时间戳
<aside class="spacer2"></aside>

## 交易市场列表

```json
//Get Market List
{
	"data":[
    "BTC",
    "ETH",
    "KCS",
    "SC",  //SC已更名为USDS
    "NEO"
  ]
}
```  

此接口，可以获取整个交易市场的交易币种
<aside class="notice"> SC已更名为USDS，但您依然可以使用SC作为查询参数。</aside>
### HTTP请求
**GET /api/v1/markets**



<aside class="spacer2"></aside>

# 委托买卖盘 

## Level-2部分买卖盘(价格聚合)

```json
{
    "sequence": "3262786978",
    "time": 1550653727731,
    "bids": [["6500.12", "0.45054140"],
             ["6500.11", "0.45054140"]],  //[price，size]
    "asks": [["6500.16", "0.57753524"],
             ["6500.15", "0.57753524"]]   
}
```
此接口，可获取指定交易对的买卖盘数据。

Level-2 买卖盘是指根据价格合并的买单和卖单，返回一个价格下的挂单量（根据价格聚合）。

此接口，只会返回部分的买卖盘数据，level2_20 返回买卖方各20条数据，level_100 返回买卖方各100条数据。推荐您使用这个接口，因为响应速度更快，流量消耗小。

维护一个本地的实时买卖盘，建议使用[Websocket](#level-2-3)。



### HTTP请求

**GET /api/v1/market/orderbook/level2_20** 

**GET /api/v1/market/orderbook/level2_100** 

###请求参数

请求参数 | 类型 | 描述
--------- | -------  | -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值

字段名称 | 描述
--------- | ------- 
sequence | 序列号
time | 时间戳
bids | 买盘
asks | 卖盘

###数据排序方式 

**Asks**: 买盘，根据价格从低到高

**Bids**: 卖盘，根据价格从高到低


## Level-2全部买卖盘(价格聚合)

```json
{
    "sequence": "3262786978",
    "time": 1550653727731,
    "bids": [["6500.12", "0.45054140"],
             ["6500.11", "0.45054140"]],  //[price，size]
    "asks": [["6500.16", "0.57753524"],
             ["6500.15", "0.57753524"]]  
}
```
此接口，可获取指定交易对的买卖盘数据。

Level-2 买卖盘是指根据价格合并的买单和卖单，返回一个价格下的挂单量（根据价格聚合）。

此接口，返回根据价格聚合的全部的买卖盘数据，这个接口适合专业的交易员调用，因为这个接口会消耗更多的服务器资源和数据流量。

维护一个本地的实时买卖盘，建议使用[Websocket](#level-2-3)。


### HTTP请求

**GET /api/v1/market/orderbook/level2**  (将于2019年12月31日弃用)

**GET /api/v2/market/orderbook/level2**  (推荐使用)

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值

字段名称 | 描述
--------- | ------- 
sequence | 序列号
time | 时间戳
bids | 买盘
asks | 卖盘

###数据排序方式 

**Asks**: 买盘，根据价格从低到高（v2）

**Asks**:买盘， 根据价格从高到低（v1）

**Bids**: 卖盘，根据价格从高到低（v1 & v2）



## Level-3全部买卖盘(非聚合)


```json
 {
        "sequence": "1545896707028",
        "time": 1550653727731,
        "bids": [
            [
                "5c2477e503aa671a745c4057",           //orderId
                "6",                                  //price
                "0.999"                               //size
            ],
            [
                "5c2477e103aa671a745c4054",
                "5",
                "0.999"
            ]
        ],
        "asks": [
            [
                "5c24736703aa671a745c401e",           
                "200",                               
                "1"                                 
            ],
            [
                "5c2475c903aa671a745c4033",
                "201",
                "1"
            ]
        ]
    }
```

此接口，可获取指定交易对的Level-3数据。Level-3返回的是整个买卖盘所有的数据（没有根据价格聚合，返回的每一个item是单个订单）。

此接口，返回没有根据价格聚合的全部的买卖盘数据，这个接口适合专业的交易员调用，因为这个接口会消耗更多的服务器资源和数据流量。

维护一个本地的实时买卖盘，建议使用[Websocket](#level-nbsp-3)。


### HTTP请求
**GET /api/v1/market/orderbook/level3**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值

字段名称 | 描述
--------- | ------- 
sequence | 序列号
time | 时间戳
bids | 买盘
asks | 卖盘

###数据排序方式 

**Asks**: 卖盘，根据价格从低到高

**Bids**: 买盘，根据价格从高到低


<aside class="spacer4"></aside>

# 历史数据

## 成交历史

```json
[
  {
      "sequence": "1545896668571",
      "price": "0.07",                      //Filled price
      "size": "0.004",                      //Filled amount
      "side": "buy",                        //Filled side. The filled side is set to the taker by default.
      "time": 1545904567062140823           //Transaction time
  },
  {
      "sequence": "1545896668578",
      "price": "0.054",
      "size": "0.066",
      "side": "buy",
      "time": 1545904581619888405
  }
]
```
此接口，可获取指定交易对的成交历史列表。

### HTTP请求
**GET /api/v1/market/histories**

###请求参数

请求参数 | 类型 | 描述
--------- | -------  | -------
symbol | String |  [交易对](#a17b4e2866)

### 返回值

字段名称 | 描述
--------- | ------- 
sequence | 序列号
time | 交易时间戳
price | 成交价格
size | 成交数量
side |卖方 或 买方

###SIDE
**side** 字段是指 taker 订单的交易方向。 对于 taker 订单，会与买卖盘中的订单进行撮合。
如果taker订单是买单**buy**，意味着上涨，因为这个taker是买单而且进入撮合引擎，反之 **sell** 卖单意味着下跌。


<aside class="spacer2"></aside>

## 历史蜡烛图数据

```json
[
  [
      "1545904980",             //k线周期的开始时间
      "0.058",                  //开盘价
      "0.049",                  //收盘价
      "0.058",                  //最高价
      "0.049",                  //最低价
      "0.018",                  //成交量
      "0.000945"                //成交额
  ],
  [
      "1545904920",
      "0.058",
      "0.072",
      "0.072",
      "0.058",
      "0.103",
      "0.006986"
  ]
]
```
此接口，返回指定交易对的kline(蜡烛图）。

<aside class="notice"> 历史蜡烛图数据可能不完整，可以通过Websocket订阅实时数据</aside>


### HTTP请求
**GET /api/v1/market/candles**

###请求参数

请求参数 | 类型 | 描述
------------- | ------- | -------
symbol | String |  [交易对](#a17b4e2866)
startAt | long | 开始时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在开始时间之后创建的数据。
endAt | long | 结束时间，[Unix 时间](http://en.wikipedia.org/wiki/Unix_time)以毫秒为单位，只会返回在结束时间以前创建的数据。 
type | String | 返回数据时间粒度，也就是每根蜡烛的时间区间:<br/>**1min, 3min, 5min, 15min, 30min, 1hour, 2hour, 4hour, 6hour, 8hour, 12hour, 1day, 1week**

<aside class="notice"> 每次查询系统最多返回1500条数据。要获得更多数据，请按时间分页数据。</aside>

###返回值

* **time** k线周期的开始时间
* **open** 开盘价
* **close** 收盘价
* **high** 最高价
* **low** 最低价
* **volume** 成交量
* **turnover** 成交额


### HTTP请求
**GET /api/v1/market/stats**


# 币种

## 币种列表

```json

[{
    "currency": "BTC",
    "name": "BTC",
    "fullName": "Bitcoin",
    "precision": 8,
    "withdrawalMinSize": "0.002",
    "withdrawalMinFee": "0.0005",
    "isWithdrawEnabled": true,
    "isDepositEnabled": true
},
{

    "currency": "ETH",
    "name": "ETH",
    "fullName": "Ethereum",
    "precision": 8,
    "withdrawalMinSize": "0.02",
    "withdrawalMinFee": "0.01",
    "isWithdrawEnabled": true,
    "isDepositEnabled": true
  
}]

```

此接口，返回币种详情列表。

### HTTP请求
**GET /api/v1/currencies**

<aside class="notice">并不是所有的币种可以用于交易</aside>

### 返回值

字段名称 | 描述
--------- | ------- 
|currency| 币种唯一标识，不会改变|
|name| 币种名，可变更|
|fullName| 币种全称，可变更|
|precision| 币种精度 |
|withdrawalMinSize| 提现最小值 |
|withdrawalMinFee| 提现最小手续费 |
|isWithdrawEnabled| 是否可提现 |
|isDepositEnabled| 是否可充值|

### 币种标识(currency code)

币种标识（code）会尽可能符合 ISO 4217 的标准，在ISO 4217中无法标识的币种，会采取自定义标识


Code | 描述
--------- | -------  
BTC | Bitcoin
ETH | Ethereum
KCS | Kucoin Shares

币种的**currency**是不会改变的，它一经确定将会变为该币种的唯一标识，而币种的name、fullname、precision等都可能会变动，当一个币种更换name时，您仍然需要使用currency去获取该币种。

例如：XRB更名后变为Nano，但它的currency仍然是XRB，而它的name变更为Nano，此时您仍然需要通过XRB去查询该币种。

## 币种详情

此接口，可获取通过单个币种标识的币种详情

```json
{
    "currency": "BTC",
    "name": "BTC",
    "fullName": "Bitcoin",
    "precision": 8,
    "withdrawalMinSize": "0.002",
    "withdrawalMinFee": "0.0005",
    "isWithdrawEnabled": true,
    "isDepositEnabled": true
  }
```

### HTTP请求
**GET /api/v1/currencies/{currency}**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
currency | String |  路径参数，[币种标识](#ebcc9fbb02)
chain | String | [可选] 针对一币多链的币种，可通过chain获取币种详情。比如， USDT存在的链有 OMNI, ERC20, TRC20。

### 返回值

字段名称 | 描述
--------- | ------- 
|currency| 币种唯一标识，不会改变|
|name| 币种名，可变更|
|fullName| 币种全称，可变更|
|precision| 币种精度 |
|withdrawalMinSize| 提现最小值 |
|withdrawalMinFee| 提现最小手续费 |
|isWithdrawEnabled| 是否可提现 |
|isDepositEnabled| 是否可充值|

## 法币换算价格
此接口，返回法币换算后的价格Get fiat price for currency

```json
{
    "code": "200000",
    "data": {
        "BTC": "3911.28000000",
        "ETH": "144.55492453",
        "LTC": "48.45888179",
        "KCS": "0.45546856"
    }
}
```
###HTTP 请求
**GET /api/v1/prices**

###请求参数

请求参数 | 类型 | 描述
--------- | ------- | -------
 base | String | [可选] 输入法币货币代码。比如，USD，EUR 默认为USD |
 currencies | String  |[可选] 使用,分割需要转换的货币。比如，BTC，ETH 默认为所有|


# 其他接口


# 时间

## 获取服务器时间

```json
{  
  "code":"200000",
  "msg":"success",
  "data":1546837113087
}
```

此接口，可获取服务器时间。

### HTTP请求
**GET /api/v1/timestamp**



# Websocket 实时数据

Websocket相对于REST API数据更加实时，而且REST API有严格的频率限制。

<aside class="notice">推荐您只创建一个Websocket连接，使用多路复用的方式去订阅数据</aside>

## 申请连接令牌

```json
{
    "code": "200000",
    "data": {
        "instanceServers": [
            {
                "pingInterval": 50000,
                "endpoint": "wss://push1-v2.kucoin.net/endpoint",
                "protocol": "websocket",
                "encrypt": true,
                "pingTimeout": 10000
            }
        ],
        "token": "vYNlCtbz4XNJ1QncwWilJnBtmmfe4geLQDUA62kKJsDChc6I4bRDQc73JfIrlFaVYIAE0Gv2--MROnLAgjVsWkcDq_MuG7qV7EktfCEIphiqnlfpQn4Ybg==.IoORVxR2LmKV7_maOR9xOg=="
    }
}
```

在您创建Websocket连接之前，需要申请一个令牌 token。

### 公共令牌 (不需要验证签名):

如果您只订阅公共频道的数据，可使用下面的bullet-public请求，获取公共令牌。

#### HTTP请求

**POST /api/v1/bullet-public**




```json
{
    "code": "200000",
    "data": {
        "instanceServers": [
            {
                "pingInterval": 50000,
                "endpoint": "wss://push1-v2.kucoin.com/endpoint",
                "protocol": "websocket",
                "encrypt": true,
                "pingTimeout": 10000
            }
        ],
        "token": "vYNlCtbz4XNJ1QncwWilJnBtmmfe4geLQDUA62kKJsDChc6I4bRDQc73JfIrlFaVYIAE0Gv2--MROnLAgjVsWkcDq_MuG7qV7EktfCEIphiqnlfpQn4Ybg==.IoORVxR2LmKV7_maOR9xOg=="
    }
}
```
### 私有令牌 (需要验证签名):

如果您想订阅私有频道的数据，可使用下面的bullet-private请求，获取私有令牌。

#### HTTP请求

**POST /api/v1/bullet-private**


### 返回值

字段名称 | 描述
--------- | ------- 
|pingInterval| 间隔 n 毫秒发送ping 消息
|pingTimeout| n 毫秒后，没有收到pong消息，那么连接断开
|endpoint| Websocket 建立连接的服务地址
|protocol| 支持的协议
|encrypt| 是否使用SSL加密

## 建立连接

```javascript
var socket = new WebSocket("wss://push1-v2.kucoin.com/endpoint?token=xxx&[connectId=xxxxx]");
```

成功建立连接之后，系统会发送welcome的信息。


```json
{
  "id":"hQvf8jkno",
  "type":"welcome"
}
```

connectId 是连接Id，由客户端生成的唯一标识。连接成功后，系统发送的welcome消息的id以及错误消息的id都是connectId。

当连接参数 acceptUserMessage=true 时, 无需订阅任何topic则会接收与用户相关的推送数据(自动包含所有私有频道，订单的变化，账户余额变更，登录信息)。例如，wss://push1-v2.kucoin.com/endpoint?token=xxx&connectId=xxxxx&acceptUserMessage=true


<aside class="spacer2"></aside>

## Ping
```json
{
  "id":"1545910590801",
  "type":"ping"
}
```
为了防止服务器断开TCP连接，客户端需要向服务器发送 ping 消息以保持连接的活跃。

ping 消息发送到服务器后，系统会向客户端返回 pong 消息。

如果服务器 **60** 秒后都没有收到 ping 消息，则服务器将断开连接。


```json
{
  "id":"1545910590801",
  "type":"pong"
}
```
<aside class="spacer3"></aside>

## 订阅数据 & 取消订阅数据

```json
// 订阅
{
    "id": "123456789",         //要求唯一
    "type": "subscribe",      //类型: subscribe / unsubscribe
    "topic": "/market/ticker:BTC-USDT,ETH-USDT",
    "privateChannel": true,   //是否使用该频道的私有频道，默认为false
    "response": true          //是否需要服务端返回本次订阅的回执信息，默认为false
}
```

```json
// 取消订阅
{
    "id": "1545910840805",      //要求唯一
    "type": "unsubscribe",     //类型: subscribe / unsubscribe
    "topic": "/market/ticker:BTC-USDT,ETH-USDT",
    "privateChannel": true,   //是否使用该频道的私有频道，默认为false
    "response": true          //是否需要服务端返回本次订阅的回执信息，默认为false
}

```
客户端需要发送订阅消息到服务端，获取指定topic的消息。

但系统会将相应topic的消息发送到客户端，详情返回值请参照指定的topic。



### 请求参数

参数以json 的格式发送

请求参数 | 类型 | 描述
--------- | ------- | -------
id | String |  请求id，唯一标识
type | String | subscribe: 订阅；unsubscribe: 取消订阅
privateChannel | Boolean | [可选] 对于一些特殊的topic，比如，/market/level3，是否使用该频道的私有频道，默认为false。设置为true后，有userId字段的信息为私有
response | Boolean |  [可选] 设置为true，成功订阅后，服务端返回本次订阅 **ack** 消息，默认为false




```json
// 回执信息
{
  "id":"1545910660739",
  "type":"ack"
}
```





## 多路复用


多路复用：在一条物理连接上，开启多个多路复用通道，可以分别订阅不同的topic，接收不同的数据。

### 开启

开启一个多路复用通道，如{"id": "1Jpg30DEdU", "type": "openTunnel", "newTunnelId": "bt1", "response": true}开启一个名为bt1的多路复用通道;

 在指令中增加tunnelId，即可使用多路复用通道，如：{"id": "1JpoPamgFM", "type": "subscribe", "topic": "/market/ticker:KCS-BTC"，"tunnelId": "bt1", "response": true}

### 返回值
收到的消息里多了相应的tunnelIId，如：{"id": "1JpoPamgFM", "type": "message", "topic": "/market/ticker:KCS-BTC", "subject": "trade.ticker", "tunnelId": "bt1", "data": {...}}

### 关闭
关闭一个多路复用通道：{"id": "1JpsAHsxKS", "type": "closeTunnel", "tunnelId": "bt1", "response": true}

### 限制
- api用户使用；
- 最多开启5个多路复用通道；





## 定序编号
买卖盘数据，成交历史数据，快照信息中会默认返回 **sequence** 字段。您可以从Level-2和Level-3市场行情数据中的sequence来判断数据是否丢失，连接是否稳定。



## 消息处理逻辑

- 判断消息的type: 目前有三类消息，message（常用的推送消息），notice（一般的通知），command（连接的命令）

- 判断消息userId: 有userId表示私有消息，没有userId的表示共有消息

- 判断消息topic: 通过topic判断是哪一类消息

- 判断subject: 同一个topic的不同类型消息用subject区分。例如level3的5类分别为trade.l3received,trade.l3changed等


# 公共频道

## 交易瞬时行情

```json

{
    "id": 1545910660739,                          
    "type": "subscribe",
    "topic": "/market/ticker:BTC-USDT",
    "response": true                              
}
```
Topic: **/market/ticker:{symbol},{symbol}...**

```json
{
  "type":"message",
  "topic":"/market/ticker:BTC-USDT",
  "subject":"trade.ticker",
  "data":{
    "sequence":"1545896668986",  //序列号
    "bestAsk":"0.08",            //最佳卖一价
    "size":"0.011",             // 最近成交数量
    "bestBidSize":"0.036",      //最佳买一数量
    "price":"0.08",             // 最近成交价格
    "bestAskSize":"0.18",       // 最佳卖一数量
    "bestBid":"0.049"           //最佳买一价
  }
}
```
订阅此topic可获取指定[交易对](#a17b4e2866)的BBO(最佳买一和卖一)数据的推送，每隔**一秒**推送一次。
此topic对带宽要求低。

以后会在这个渠道中推送更多的信息。


<aside class="spacer2"></aside> 
<aside class="spacer4"></aside> 


## 全部交易对瞬时行情

```json

{
    "id": 1545910660739,                          
    "type": "subscribe",
    "topic": "/market/ticker:all",
    "response": true                              
}
```
Topic: **/market/ticker:all**

```json
{
  "type":"message",
  "topic":"/market/ticker:all",
  "subject":"BTC-USDT",
  "data":{
    "sequence":"1545896668986",  //序列号
    "bestAsk":"0.08",            //最佳卖一价
    "size":"0.011",             // 最近成交数量
    "bestBidSize":"0.036",      //最佳买一数量
    "price":"0.08",             // 最近成交价格
    "bestAskSize":"0.18",       // 最佳卖一数量
    "bestBid":"0.049"           //最佳买一价ß
  }
}
```
订阅此topic可获取所有的BBO(最佳买一和卖一)数据的推送，每隔**一秒**推送一次。


<aside class="spacer2"></aside> 
<aside class="spacer4"></aside> 


## 交易对行情快照

```json
{
	"data": {
		"sequence": "1545896669291",
		"data": [{
			"trading": true,
			"symbol": "KCS-BTC",
			"buy": 0.00011,
			"sell": 0.00012,
			"sort": 100,
			"volValue": 3.13851792584,
			"baseCurrency": "KCS",
			"market": "BTC",         
			"quoteCurrency": "BTC",  
			"symbolCode": "KCS-BTC",
			"datetime": 1548388122031,
			"high": 0.00013,
			"vol": 27514.34842,
			"low": 0.0001,
			"changePrice": -1.0e-5,
			"changeRate": -0.0769,
			"lastTradedPrice": 0.00012,
			"board": 0,
			"mark": 0
		}]
	},
	"subject": "trade.snapshot",
	"topic": "\/market\/snapshot:BTC",
	"type": "message"
}
```

Topic: **/market/snapshot:{symbol}**

订阅此topic对可以获取单个[交易对](#a17b4e2866)的行情快照信息，每隔**两秒**推送一次。


<aside class="spacer4"></aside> 
<aside class="spacer4"></aside> 
<aside class="spacer"></aside> 

## 按市场的交易对行情快照

```json
{
	"data": {
		"sequence": "1545896669291",
		"data": {
			"trading": true,
			"symbol": "KCS-BTC",
			"buy": 0.00011,
			"sell": 0.00012,
			"sort": 100,
			"volValue": 3.13851792584,
			"baseCurrency": "KCS",
			"market": "BTC",
			"quoteCurrency": "BTC",
			"symbolCode": "KCS-BTC",
			"datetime": 1548388122031,
			"high": 0.00013,
			"vol": 27514.34842,
			"low": 0.0001,
			"changePrice": -1.0e-5,
			"changeRate": -0.0769,
			"lastTradedPrice": 0.00012,
			"board": 0,
			"mark": 0
		}
	},
	"subject": "trade.snapshot",
	"topic": "\/market\/snapshot:KCS-BTC",
	"type": "message"
}
```

Topic: **/market/snapshot:{market}**

订阅此topic可获取指定[交易市场](#b8f118fefc)的所有交易对的行情快照，每隔**2秒**推送一次。


<aside class="spacer4"></aside> 
<aside class="spacer4"></aside> 
<aside class="spacer"></aside> 

## Level-2市场行情

```json
{
    "id": 1545910660740,                          
    "type": "subscribe",
    "topic": "/market/level2:BTC-USDT",
    "response": true                              
}
```

Topic: **/market/level2:{symbol},{symbol}...**

订阅此topic可获取指定[交易对](#a17b4e2866)Level-2的买卖盘数据，每隔**2秒**推送一次。



```json
{
  "type":"message",
  "topic":"/market/level2:BTC-USDT",
  "subject":"trade.l2update",
  "data":{
    "sequenceStart":1545896669105,
    "sequenceEnd":1545896669106,
    "symbol":"BTC-USDT",
    "changes":{
      "asks":[["6","1","1545896669105"]],           //price, size, sequence
      "bids":[["4","1","1545896669106"]]
    }
  }
}
```

校准流程：

接收并缓存收到的update数据流

回放缓存的l2update数据流

校准流程:

1.成功订阅后，请将Websocket推送的l2update数据流缓存在本地。

2.通过REST请求拉取[Level-2买卖盘](#Level-2部分买卖盘(价格聚合))的快照信息。

3.轮训缓存的l2update数据流，获取到快照信息中的sequence（查询范围，sequenceStart和sequenceEnd)，摒弃掉sequenceStart之前的数据，更新l2update数据流。

4.将更新的l2update数据流回放到缓存中，以确保新的Level-2买卖盘数据的sequenceStartt与前一个Level-2买卖盘数据sequenceEnd连续。

5.根据size和sequence来更新l2update数据流。如果 price为0，请忽略这条消息并更新sequence; 如果收到size为0的数据，需要将指定price的记录移除买卖盘。对于其他情况，请更买卖。

 返回值对应的是[price，size，sequence]的数组。 请注意，size是该price下的size，而不是指增量。 如果收到size为0的数据，需要将指定price的记录移除买卖盘。



   

**案例**

以BTC/USDT为例，假设level 2当前买卖盘数据如下:

1. 成功订阅此topic，您会收到如下买卖盘数据流:


"asks":[

  ["3988.62","8", 15], // 摒弃 sequence <16

  ["3988.61","0", 18], // 移除 price 为 3988.61 的数据

  ["3988.59","3", 16], // 摒弃 sequence = 16

]

"bids":[

  ["3988.50", "44", "17"] // 更新 price 为 3988.50 的size

]

<aside class="notice">消息展示为[“价格”,“数量”,“sequence”]</aside>

2. 通过REST请求拉取[Level-2买卖盘快照信息](#Level-2部分买卖盘(价格聚合))

Sequence：**16**

Data：

"asks":[

  ["3988.62","8"],

  ["3988.61","32"],

  ["3988.60","47"],

  ["3988.59","3"],

]

"bids":[

  ["3988.51","56"],

  ["3988.50","15"],

  ["3988.49","100"],

  ["3988.48","10"]

]

<aside class="notice">消息展示为[“价格”,“数量”]</aside>

当前拉取的买卖盘的快照数据如下:

| Price   | Size | Side |
| ------- | ---- | ---- |
| 3988.62 | 8    | Sell |
| 3988.61 | 32   | Sell |
| 3988.60 | 47   | Sell |
| 3988.59 | 3    | Sell |
| 3988.51 | 56   | Buy  |
| 3988.50 | 15   | Buy  |
| 3988.49 | 100  | Buy  |
| 3988.48 | 10  | Buy  |


当前买卖盘快照信息的sequence 为 **16**，摒弃买卖盘数据流中sequence <= 16的数据，回放sequence为**17，18**的数据，更新买卖盘快照信息。现在，您本地的sequence为**18**。

**变更：**

1.**更新价格为 3988.50 的size为 44 (Sequence 17)**

2.**移除价格为 3988.61 的数据 (Sequence 18)**

下方的买卖盘为更新后的买卖盘:

| Price   | Size | Side |
| ------- | ---- | ---- |
| 3988.62 | 8    | Sell |
| 3988.60 | 47   | Sell |
| 3988.59 | 3    | Sell |
| 3988.51 | 56   | Buy  |
| 3988.50 | 44   | Buy  |
| 3988.49 | 100  | Buy  |
| 3988.48 | 10  | Buy  |

## 撮合执行数据

```json
{
    "id": 1545910660741,                          
    "type": "subscribe",
    "topic": "/market/match:BTC-USDT",
    "privateChannel": false,                      
    "response": true                              
}
```
Topic: **/market/match:{symbol},{symbol}...**

此topic，提供 **privateChannel** 

订阅此topic，可获取撮合执行数据。


```json
{
  "id":"5c24c5da03aa673885cd67aa",
  "type":"message",
  "topic":"/market/match:BTC-USDT",
  "subject":"trade.l3match",
  "sn":1545896669145,
  "data":{
    "sequence":"1545896669145",
    "symbol":"BTC-USDT",
    "side":"buy",
    "size":"0.01022222000000000000",
    "price":"0.08200000000000000000",
    "takerOrderId":"5c24c5d903aa6772d55b371e",
    "time":"1545913818099033203",
    "type":"match",
    "makerOrderId":"5c2187d003aa677bd09d5c93",
    "tradeId":"5c24c5da03aa673885cd67aa"
  }
}
```
<aside class="spacer8"></aside>
<aside class="spacer"></aside>

## 完整的撮合引擎数据(Level&nbsp;3)

```json
{
    "id": 1545910660742,                          
    "type": "subscribe",
    "topic": "/market/level3:BTC-USDT",
    "privateChannel": false,                      
    "response": true                              
}
```

Topic: **/market/level3:{symbol},{symbol}...**

此topic，提供 **privateChannel** 

订阅此topic，可获取Level-3完整的撮合引擎数据。

可获取订单和交易的实时数据，这些数据流可用于维护一个本地的Level-3买卖盘。

<aside class="notice">注意: 如果您想维护一个本地的Level-2买卖盘，请订阅Level-2市场行情</aside>

下面是如何构建一个Level-3买卖盘的算法。 

1. 订阅 Topic: /market/level3:{symbol},{symbol}... 获取数据流
2. 对接收到的数据流进行排序
3. 发送一个REST请求拉取[Level-3买卖盘](#Level-3全部买卖盘(非聚合))的快照
4. 舍弃sequence <= 快照信息的sequence，回放数据流
5. 按需将回放消息应用于快照（参见下文）
6. 回放完成后，再次循环以上步骤，更新买卖盘数据


###MESSAGE TYPE

返回信息的type有: **RECEIVED, OPEN, DONE, MATCH, CHANGE**
<aside class="notice">
所有的 open 和 match 消息会导致变卖盘变更，但并非所有的 done 或 change 消息会变更买卖盘。
有些 received 消息会推送给您但是不会存在在买卖盘中，请勿因为此类消息更新买卖盘，否则会影响您的买卖盘的准确性。
</aside>





###RECEIVED

```json
{
	"type": "message",
	"topic": "/market/level3:BTC-USDT",
	"subject": "trade.l3received",
	"data": {
		"sequence": "1545896669147",
		"symbol": "BTC-USDT",
		"side": "sell",  //买卖方向, buy and sell
		"orderId": "5c24c72503aa6772d55b378d",  //order id
		"price": "4.00000000000000000000", 
		"time": "1545914149935808589",  //timestamp, 时间戳是纳秒
		"clientOid": "",   //客户端生成的唯一订单标识 e.g. UUID
		"type": "received",  //L3 消息类型	
		"orderType": "limit" // 订单类型 limit,markrt,stop_limit
	}
}
```

```json
{
	"type": "message",
	"topic": "/market/level3:BTC-USDT",
	"subject": "trade.l3received",
	"data": {
		"sequence": "1545896669100",
		"symbol": "BTC-USDT",
		"side": "sell",
		"orderId": "5c24c72503aa6772d55b178d",
		"time": "1545914149835808589",
		"clientOid": "",
		"type": "received",
		"orderType": "market"
	}
}
```
当匹配引擎接收到订单指令时，系统将向用户发送确认消息，type为**received**。

这意味着，订单进入撮合引擎且订单状态为active。一旦撮合引擎收到这个订单信息，无论它是否立即成交，都会向用户发送确认信息。

**received**消息并不是指在买卖盘挂单，而是指这个订单进入撮合引擎。如果订单能够立即成交，（taker订单），会发送**match**消息。如果自成交保护被触发，size会调整，会发送**change**消息。订单没有全部成交的或由于自成交保护取消了的订单会展示在买卖盘中，发送信息中的type为**open**。


<aside class="notice">您可以使用您自定义的clientOid来跟踪订单信息，但是特别的clientOid可能会暴露您的策略，所以推荐您使用UUID
</aside>

<aside class="spacer8"></aside>
<aside class="spacer4"></aside>


###OPEN

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3open",
  "data":{
    "sequence":"1545896669148",
    "symbol":"BTC-USDT",
    "side":"sell",  //买卖方向, buy and sell
    "size":"1", //order 数量
    "orderId":"5c24c72503aa6772d55b378d",  //order id
    "price":"6.00000000000000000000",
    "time":"1545914149935808632", //timestamp, 时间戳是纳秒
    "type":"open"  //L3 messege type. 如果是open, 会返回price 和 size
  }
}
```

当限价订单中的剩余部分进入订单簿时，系统将向用户发送**open**消息。

这意味着这个订单现已在订单簿上，没有立即成交的订单才会推送此消息。 
privateChannel=true，还会返回remaining_size这个字段，指订单中有多少没有成交的数量


<aside class="notice">当接收到 price="", size="0" 的消息时，意味着这是隐藏单</aside>

<aside class="spacer4"></aside>
<aside class="spacer"></aside>

###DONE

一个订单生命周期结束时，订单将不会展示在买卖盘中，系统会推送**done**信息。

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3done",
  "data":{
    "sequence":"1545896669226",
    "symbol":"BTC-USDT",
    "reason":"filled", //成交
    "side":"buy",
    "orderId":"5c24c96103aa6772d55b380b",
    "time":"1545914730696727106",
    "type":"done"
  }
}
```

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3done",
  "data":{
    "sequence":"1545896669227",
    "symbol":"BTC-USDT",
    "reason":"canceled",  //取消
    "side":"buy",  //买卖方向, buy and sell
    "orderId":"5c24c96103aa6772d55b381b",  //order id
    "time":"1545914730696797106",  //timestamp, 时间戳是纳秒
    "type":"done", //L3 messege 类型. 
    "size": "1.12340000000000000000"  //order 数量
  }
}
```

推送**done**消息，意味着订单从买卖盘中移除，这要有推送过**received**消息的，都会收到**done**消息。 **done**可能指订单被成交或被取消。收到done消息后，就不会在收到关于这个订单的其他的信息了。
privateChannel=true，还会返回remainSize这个字段，指订单中有多少没有成交的数量，如果为0，则意味着全部成交。市价单不会有remainSize，因为市价单是不会出现在买卖盘中的。


<aside class="spacer8"></aside>
<aside class="spacer3"></aside>

###MATCH

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3match",
  "data":{
    "sequence":"1545896669291",
    "symbol":"BTC-USDT",
    "side":"buy",  //买卖方向, buy and sell
    "size":"0.07600000000000000000",  //order 数量
    "price":"0.08300000000000000000",  
    "takerOrderId":"5c24ca2e03aa6772d55b38bf",  //深度提取者 order id
    "time":"1545914933083576866",  //timestamp, 时间戳是纳秒
    "type":"match",  //L3 messege type. 如果是match, 通过makerOrderId减少订单数量
    "makerOrderId":"5c20492a03aa677bd099ce9d",  //深度提供者 order id
    "tradeId":"5c24ca3503aa673885cd67ef"  //match_id，成功撮合后生成的tradeId
  }
}
```
当两个订单成功撮合后，系统会推送match信息。

两个订单成功撮合，会生成一个tradeId

当进入撮合引擎后，taker单会立即与maker单(买卖盘中剩余的订单)开始撮合。side字段是指maker单的成交方向，如果 side 为sell，则表明marker单是卖单且上涨，反之，下跌。

 

<aside class="notice">在进入买卖盘之前，冰山单或隐藏单和普通的订单一样，撮合成功后作为taker</aside>

<aside class="spacer4"></aside>
<aside class="spacer2"></aside>

###CHANGE

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3change",
  "data":{
    "sequence":"1545896669656",
    "symbol":"BTC-USDT",
    "side":"buy",  //买卖方向, buy and sell
    "orderId":"5c24caff03aa671aef3ca170",  //order id
    "price":"1.00000000000000000000",
    "newSize":"0.15722222000000000000",  //变更后 order 数量
    "time":"1545915145402532254",  //timestamp, 时间戳是纳秒
    "type":"change",  //L3 messege type.如果是change消息，通过orderId修改数量
    "oldSize":"0.18622222000000000000"  //变更前的订单量
  }
}
```

当订单信息因为STP(自成交保护)变更，系统会给您推送**chenge**消息。
由于自成交保护，需要调整订单数量或资金。订单只会在数量或资金上减少。当一个订单size发生变化会向您推送**change**消息。在买卖盘中订单（**open**）和收到**received**消息但没有进入买卖盘的订单，都可能向您推送**chaneg**消息。新的市价单由于自成交保护导致的导致资金变化也会向您推送**change**消息。

<aside class="spacer8"></aside>
<aside class="spacer4"></aside>

### 构建Level-3买卖盘


如何构建本地OrderBook level-3数据

1.使用websocket订阅 /market/level3:{symbol} 频道订阅level3的增量数据，并缓存收到的所有增量数据。

2.通过rest接口 https://openapi-v2.kucoin.com/api/v1/market/orderbook/level3?symbol={symbol} 获取level3的快照数据。

3.数据检验：获取快照的sequence不小于缓存的所有增量的最小sequence。如果不满足此条件，从第一步从头开始。

4.回放所有缓存的增量数据:

    4.1. 如果增量数据的sequence <= 当前快照的sequence，则舍弃增量数据，并结束本次更新; 否则进行4.2。

    4.2 如果增量数据的sequence = 当前快照的sequence+1，则进行4.2.1逻辑更新，否则进行4.3步骤。

      4.2.1 更新当前快照的sequence为增量数据的sequence.
      4.2.2 如果是received消息，结束更新逻辑。（因为现在received消息不影响level3数据）
      4.2.3 如果是open消息，增加orderid,price,size构建的相应买单或卖单
      4.2.4 如果是done消息，移除对应orderid对应的买单或者卖单
      4.2.5 如果是change消息，修改对应orderid对应的买单或者卖单的数量
      4.2.6 如果是match消息，减少对应markerOrderId对应的订单数量

    4.3 此种情况为sequence不连续，执行步骤2，重新拉取快照数据，以便保证sequence不缺失。

5 接收新的增量数据推送，执行步骤4。


如果您在维护一个本地Level-3买卖盘过程中，有不理解的地方，您可以参考用 Go Language 写的[demo](#level-nbsp-3)，里面包含了不同type信息的处理逻辑。

<aside class="spacer4"></aside>
<aside class="spacer2"></aside>

# 私有频道

## 止损单放置事件

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3received",
  "data": {
    "sequence":"1545738118241",
    "symbol":"BTC-USDT",
    "side":"buy",
    "orderId":"5c21e80303aa677bd09d7dff",
    "stopType":"entry",
    "funds":"1.00000000000000000000",
    "time":"1545743136994328401",
    "type":"stop"
  }
}
```
Topic: /market/level3:{symbol},{symbol}...

当系统收到止盈止损订单时，您将收到一条'stop'消息，表示此订单已进入队列并等待触发。

<aside class="spacer4"></aside>
<aside class="spacer"></aside>

## 止损单触发事件

```json
{
  "type":"message",
  "topic":"/market/level3:BTC-USDT",
  "subject":"trade.l3received",
  "data": {
    "sequence":"1545738118241",
    "symbol":"BTC-USDT",
    "side":"buy",
    "orderId":"5c21e80303aa677bd09d7dff",
    "stopType":"entry",
    "funds":"1.00000000000000000000",
    "time":"1545743136994328401",
    "type":"activate"
  }
}
```
Topic: /market/level3:{symbol},{symbol}...
触发止盈止损单后，您将收到一条'activate'消息，表示此订单开始进入撮合引擎匹配的生命周期。

<aside class="spacer4"></aside>
<aside class="spacer"></aside>

## 余额变更事件
```json
{
  "type":"message",
  "topic":"/account/balance",
  "subject":"account.balance",
  "data":{
    "total": "88",
    "available": "88",
    "availableChange": "88",
    "currency": "KCS",
    "hold": "0",
    "holdChange": "0",
    "relationEvent": "main.deposit",
    "relationEventId": "5c21e80303aa677bd09d7dff",
    "time": "1545743136994"
  }
}

```
Topic: **/account/balance**

当您的账户余额变更时，您会收到详细的账户变更信息。

<aside class="notice">您可以通过accountId监控您的资产变更</aside>