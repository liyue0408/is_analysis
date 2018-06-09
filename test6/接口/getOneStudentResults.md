# 接口：getOneStudentResults  [返回](../README.md)
用例： [查看成绩](../用例/查看成绩.md)，[评定成绩](../用例/评定成绩.md)

- 功能：返回一个学生的所有实验成绩和实验评价。

- 权限：
    学生：只能查看自己的成绩，即接口参数student_id必须等于登录学生的student_id
    老师：可以查看所有学生的成绩。

- API请求地址： 接口基本地址/v1/api/getOneStudentResults/<student_id>

- 请求方式 ：GET

- 请求参数说明:

  |参数名称|说明|
  |:--:|:--|
  |student_id|学生的学号|

- 返回实例：

        {
            "status": true,
            "info": null,
            "student_id": "201510414408",
            "github_username": "liyue",
            "class": "软件(本)15-4",
            "name": "李玥",
            "total": 6,
            "avgresult":95,
            "data": [
                {
                "test_id":1,
                "web_exists": true,
                "score": 90,
                "mark":"基本准确，有些小错误，望细心",
                "update_date": "2018-02-16 15:20:08"
                },
                {
                ...其他实验
                }
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:---:|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |student_id|学号|
  |github_username|学生的gitHub用户名|
  |class|班级|
  |name|真实姓名|
  |total|实验总数|
  |avgresult|实验平均成绩|
  |data|所有实验的成绩和评语|
  |test_id|实验编号|
  |web_exists|本实验的GitHub网页是否存在|
  |result|本实验成绩，可以为空和为0是不一样的。|
  |memo|本实验老师的评价，可以为空|
  |update_date|本实验老师的批改日期，可以为空|