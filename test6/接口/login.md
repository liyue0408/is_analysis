# 接口：login  [返回](../README.md)
用例： [登录](../用例/登录.md)

- 功能：用户登录到GitHub在线实验管理平台。

- 权限：用户。

- API请求地址：接口基本地址/v1/api/login

- 请求方式 ：POST

- 请求实例：

        {
            "id":"201510414408",
            "password":"201510414408",
            "type":"学生"
        }

- 请求参数说明:

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |id|学生学号、老师的工号或管理员的工号，由type决定。|
  |password|用户的密码|
  |type|用户类型，学生、老师、管理员|

- 返回实例：

        {
            "status": true,
            "info": null,
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|