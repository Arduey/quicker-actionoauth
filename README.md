## 查询授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/query
        
    返回格式: Json
        
    请求方式: Post

    请求类型: 文本表单

    请求格式: 参数1=值1&参数2=值2......
        
    接口功能: 用于动作里调用检测该动作是否对该用户授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|userunionid|是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid    |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |

### 返回示例

```json
{
	"success": True,
	"code": "0",
	"message": "动作已授权",
	"user_expiry": "2025-06-11 13:45:23",
	"author_expiry": "2025-12-31 16:47:43"
}
```

### 返回参数详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success      |Boolean|true<br>false| **true代表动作已授权** <br>false具体请参考返回值详解|
|code         |String |具体请参考返回值详解|对应的message编号|
|message      |String |具体请参考返回值详解|对应参数success值的详细信息|
|user_expiry  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expiry|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

### 返回值详解
|success|code|message|
|:---:|:---:|:---|
| True  | 0 | 动作已授权 |
| False | 1 | 请使用post请求 |
| False | 2 | 必填参数的值不能为空 |
| False | 3 | 动作未授权 |
| False | 4 | 动作授权已过期 |
| False | 5 | 作者无授权信息,请联系管理员授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 6 | 作者授权已过期,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 添加授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/add
        
    返回格式: Json
        
    请求方式: Post

    请求类型: 文本表单

    请求格式: 参数1=值1&参数2=值2......
        
    接口功能: 用于作者为用户创建某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid       |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|expirationtime|是|String|用户动作的授权过期时间<br>格式 **YYYY-mm-dd HH:MM:SS** |
|userunionid   |是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|contact       |否|String|用户联系方式, 或者备注, 可填可不填, 可用来备注|

### 返回示例

```json
{
	"success": false,
	"code": "1",
	"message": "请使用post请求",
	"user_expiry": "",
	"author_expiry": ""
}
```

### 返回参数详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success      |Boolean|true<br>false| **true代表动作授权添加成功** <br>具体请参考返回值详解|
|code         |String |具体请参考返回值详解|对应的message编号|
|message      |String |具体请参考返回值详解|对应参数success值的详细信息|
|user_expiry  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expiry|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

### 返回值详解
|success|code|message|
|:---:|:---:|:---|
| True  | 0 | 授权信息创建成功 |
| False | 1 | 请使用post请求 |
| False | 2 | 必填参数的值不能为空 |
| False | 3 | 作者无权限或参数值有误,请联系管理员授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 4 | 作者授权已过期,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 5 | 创建失败,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 6 | expirationtime参数值格式有误 |
| False | 7 | 授权信息已存在,请使用update或delete接口 |

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 更新授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/update
        
    返回格式: Json
        
    请求方式: Post

    请求类型: 文本表单

    请求格式: 参数1=值1&参数2=值2......
        
    接口功能: 用于作者为用户更新某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid       |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|expirationtime|是|String|用户动作的授权过期时间<br>格式 **YYYY-mm-dd HH:MM:SS** |
|userunionid   |是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|contact       |否|String|用户联系方式, 或者备注, 可填可不填, 可用来备注|

### 返回示例

```json
{
	"success": false,
	"code": "5",
	"message": "授权信息不存在,请使用add接口",
	"user_expiry": "",
	"author_expiry": "2025-12-31 16:47:43"
}
```

### 返回参数详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success      |Boolean|true<br>false| **true代表动作授权更新成功** <br>具体请参考返回值详解|
|code         |String |具体请参考返回值详解|对应的message编号|
|message      |String |具体请参考返回值详解|对应参数success值的详细信息|
|user_expiry  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expiry|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

### 返回值详解
|success|code|message|
|:---:|:---:|:---|
| True  | 0 | 授权信息已更新 |
| False | 1 | 请使用post请求 |
| False | 2 | 必填参数的值不能为空 |
| False | 3 | 作者无权限或参数值有误,请联系管理员授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 4 | 作者授权已过期,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 5 | 授权信息不存在,请使用add接口 |
| False | 6 | expirationtime参数值格式有误 |

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 删除授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/delete
        
    返回格式: Json
        
    请求方式: Post

    请求类型: 文本表单

    请求格式: 参数1=值1&参数2=值2......
        
    接口功能: 用于作者为用户删除某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid       |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|userunionid   |是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|

### 返回示例

```json
{
	"success": True,
	"code": "0",
	"message": "授权信息不存在,无需删除",
	"user_expiry": "",
	"author_expiry": "2025-12-31 16:47:43"
}
```

### 返回参数详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success      |Boolean|true<br>false| **true代表动作授权删除成功** <br>具体请参考返回值详解|
|code         |String |具体请参考返回值详解|对应的message编号|
|message      |String |具体请参考返回值详解|对应参数success值的详细信息||
|user_expiry  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expiry|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

### 返回值详解
|success|code|message|
|:---:|:---:|:---|
| True  | 0 | 授权信息已更新 |
| True  | 0 | 授权信息不存在,无需删除 |
| False | 1 | 请使用post请求 |
| False | 2 | 必填参数的值不能为空 |
| False | 3 | 作者无权限或参数值有误,请联系管理员授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 4 | 作者授权已过期,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 5 | 授权信息删除失败,请联系管理员QQ:395508874 微信:ASCII98-108-117-101 |

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 获取所有授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/queryall
        
    返回格式: Json
        
    请求方式: Post

    请求类型: 文本表单

    请求格式: 参数1=值1&参数2=值2......
        
    接口功能: 用于作者获取所有动作的详细授权信息

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|

### 返回示例

```json
{
	"success": false,
	"code": "5",
	"message": "当前无任何授权信息",
	"user_expiry": "",
	"author_expiry": "2025-12-31 16:47:43"
}
```

### 返回参数详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success      |Boolean|true<br>false| **true代表动作授权信息获取成功** <br>具体请参考返回值详解|
|code         |String |具体请参考返回值详解|对应的message编号|
|message      |String |具体请参考返回值详解|对应参数success值的详细信息|
|user_expiry  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expiry|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

### 返回值详解
|success|code|message|
|:---:|:---:|:---|
| True  | 0 | 一个包含所有授权信息的json |
| False | 1 | 请使用post请求 |
| False | 2 | 必填参数的值不能为空 |
| False | 3 | 作者无权限或参数值有误,请联系管理员授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 4 | 作者授权已过期,请联系管理员续费授权QQ:395508874 微信:ASCII98-108-117-101 |
| False | 5 | 当前无任何授权信息 |

## 联系方式

| 名称      | 详情                  |
|---------|---------------------|
| QQ      | 395508874           |
| 微信    | ASCII98-108-117-101 |
| Quicker | 乐昂岚【接定制】     |

## 赞赏码

![赞赏码](https://deskpad.oss-cn-shanghai.aliyuncs.com/_sitefiles/donationimages/81137_20220907_173102_%E6%9C%AA%E6%A0%87%E9%A2%98-2.jpg)

