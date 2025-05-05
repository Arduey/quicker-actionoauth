## 查询授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/query
        
    返回格式: Json
        
    请求方式: Post
        
    接口功能:  用于动作里调用检测该动作是否对该用户有授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|userunionid|是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid    |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|authoremail|是|String|你的Email<br>购买授权提交的Email|

### 返回示例

```json
{
	"success": false,
	"message": "参数不能为空",
	"user_expirationtime": "",
	"author_expirationtime": ""
}
```

### 返回详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success              |Boolean|true<br>false| **true代表动作已授权** <br>false详情请查看message参数值|
|message              |String |参数值不能为空<br>无权限, 请联系作者授权<br>授权已过期, 请续费授权<br>动作未授权<br>动作已授权<br>动作授权已过期<br>请使用post请求|对应参数success值的详细信息|
|user_expirationtime  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expirationtime|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 添加授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/db
        
    返回格式: Json
        
    请求方式: Post
        
    接口功能:  用于作者为用户创建某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|method        |是|String|操作类型  **只能为add** |
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
	"message": "expirationtime参数格式为YYYY-mm-dd HH:MM:SS",
	"user_expirationtime": "",
	"author_expirationtime": "2025-12-31 23:59:59"
}
```

### 返回详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success              |Boolean|true<br>false| **true代表动作授权添加成功** <br>false详情请查看message参数值|
|message              |String |method不能为空<br>authoremail和authorunionid不能为空<br>无权限, 请联系作者授权<br>授权已过期, 请联系作者续费授权<br>非法method参数值<br>除contact外, 其他参数不能为空<br>创建失败, 请联系作者<br>授权信息创建成功<br>授权信息已存在, 请使用update或delete<br>expirationtime参数格式为YYYY-mm-dd HH:MM:SS|
|user_expirationtime  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expirationtime|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 更新授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/db
        
    返回格式: Json
        
    请求方式: Post
        
    接口功能:  用于作者为用户更新某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|method        |是|String|操作类型  **只能为update** |
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
	"message": "expirationtime参数格式为YYYY-mm-dd HH:MM:SS",
	"user_expirationtime": "",
	"author_expirationtime": "2025-12-31 23:59:59"
}
```

### 返回详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success              |Boolean|true<br>false| **true代表动作授权更新成功** <br>false详情请查看message参数值|
|message              |String |method不能为空<br>authoremail和authorunionid不能为空<br>无权限, 请联系作者授权<br>授权已过期, 请联系作者续费授权<br>非法method参数值<br>除contact外, 其他参数不能为空<br>授权信息不存在, 请使用add<br>授权信息已更新<br>expirationtime参数格式为YYYY-mm-dd HH:MM:SS|
|user_expirationtime  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expirationtime|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 删除授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/db
        
    返回格式: Json
        
    请求方式: Post
        
    接口功能:  用于作者为用户删除某个动作的授权

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|method        |是|String|操作类型  **只能为delete** |
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid       |是|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|userunionid   |是|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|contact       |否|String|用户联系方式, 或者备注, 可填可不填, 可用来备注|
|expirationtime|否|String|用户动作的授权过期时间<br>格式 **YYYY-mm-dd HH:MM:SS** |

### 返回示例

```json
{
	"success": True,
	"message": "授权信息已删除",
	"user_expirationtime": "",
	"author_expirationtime": "2025-12-31 23:59:59"
}
```

### 返回详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success              |Boolean|true<br>false| **true代表动作授权删除成功** <br>false详情请查看message参数值|
|message              |String |method不能为空<br>authoremail和authorunionid不能为空<br>无权限, 请联系作者授权<br>授权已过期, 请联系作者续费授权<br>非法method参数值<br>除contact和expirationtime外, 其他参数不能为空<br>授权信息不存在, 无需删除<br>授权信息已删除<br>授权信息删除失败, 请联系作者|
|user_expirationtime  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expirationtime|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 获取所有授权接口

### 接口介绍

    接口地址: https://quickeroauth.top/db
        
    返回格式: Json
        
    请求方式: Post
        
    接口功能:  用于作者获取所有动作的详细授权信息

### 请求参数

|参数名|是否必填|接口类型|参数说明|
|:---:|:---:|:---:|---|
|method        |是|String|操作类型  **只能为queryall** |
|authoremail   |是|String|你的Email<br>购买授权提交的Email|
|authorunionid |是|String|你的Unionid<br>来源模块 **获取系统或动作信息**|
|shareid       |否|String|动作库ID<br>来源模块 **获取系统或动作信息** |
|expirationtime|否|String|用户动作的授权过期时间<br>格式 **YYYY-mm-dd HH:MM:SS** |
|userunionid   |否|String|用户的Unionid<br>来源模块 **获取系统或动作信息**|
|contact       |否|String|用户联系方式, 或者备注, 可填可不填, 可用来备注|

### 返回示例

```json
{
	"success": false,
	"message": "当前无任何授权信息",
	"user_expirationtime": "",
	"author_expirationtime": "2025-12-31 23:59:59"
}
```

### 返回详解
|参数名|类型|可能值|参数说明|
|:---:|:---:|:---:|---|
|success              |Boolean|true<br>false| **true代表动作授权信息获取成功** <br>false详情请查看message参数值|
|message              |String |method不能为空<br>authoremail和authorunionid不能为空<br>无权限, 请联系作者授权<br>授权已过期, 请联系作者续费授权<br>非法method参数值<br>当前无任何授权信息<br>包含所有授权信息的json|
|user_expirationtime  |String |格式 **YYYY-mm-dd HH:MM:SS** |用户动作的授权过期时间|
|author_expirationtime|String |格式 **YYYY-mm-dd HH:MM:SS** |你的授权过期时间|

------------------------------------------------------------------------------
------------------------------------------------------------------------------

## 联系方式

| 名称      | 详情                  |
|---------|---------------------|
| QQ      | 395508874           |
| 微信      | ASCII98-108-117-101 |
| Quicker | 乐昂岚【接定制】            |

## 赞赏码

![赞赏码](https://deskpad.oss-cn-shanghai.aliyuncs.com/_sitefiles/donationimages/81137_20220907_173102_%E6%9C%AA%E6%A0%87%E9%A2%98-2.jpg)
