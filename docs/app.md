---
layout: docs
title: 应用类API
prev_section: installation
next_section: structure
permalink: /docs/app/
---

### 应用类API

>全球通讯录中搜索用户信息

**方法说明：**

>该方法用于搜索全球通讯录中的用户信息

**服务器端接口方法：**  
    ```/user/searchGlobalUser.do```

**HTTP请求方式：**  
    ```GET```

**参数：**  
    ```KAMS_TOKEN,keyword```

参数说明：
|参数名|参数说明|是否必须|
|---|---|---|
|KAMS_TOKEN|标识用户是否登录的Token|是|
|keyword|搜索用户信息的关键字|是|


**服务器返回：**

**返回值类型：**  
```json```

示例：  
```json
{
  "users": [
    {
      "id": null,
      "email": "zhengzhiwei@wxm.com",
      "password": null,
      "status": null,
      "createDate": null,
      "modifyDate": null,
      "nick": "郑志伟",
      "title": null,
      "position": null,
      "userType": null,
      "businessPhone": null,
      "name": "郑志伟",
      "corporation": null,
      "company": null,
      "deptFirst": null,
      "deptSec": null,
      "img": null,
      "mobilePhone": "13966691711",
      "sex": null,
      "username": null,
      "corporationId": null,
      "new": true
    },
    .....
  ],
  "success": "true"
}
```

>"success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"users": 搜索到的用户信息列表；

