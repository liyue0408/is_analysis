
## GItHub试验管理平台数据库设计 [首页](../README.md)

<div id="Users"></div>

- ### Users表（用户表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |user_id|INT|主键|否| | | 用户ID|
    |name|VARCHAR| |否| | | 用户真实姓名|
    |github_username|VARCHAR| |是|空| | GitHUB用户名|
    |password|VARCHAR)| |是|空| | 密码|


<div id="Teachers"></div>

- ### Teachers表（老师表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |teacher_id|VARCHAR|主键|否| | | 老师编号|
    |user_id|NUMBER|外键|是| | Users.user_id| 老师的用户ID|
    |teacher_name|VARCHAR| |是| | | 老师姓名|
    |sex|VARCHAR| |是| | | 老师性别|
    |age|INT| |是| | | 老师年龄|
    |department|VARCHAR| |否| | | 老师属于的部门|

<div id="Students"></div>

- ### Students表（学生表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |student_id|VARCHAR|主键|否| | | 学号|
    |user_id|NUMBER|外键|是| | | 学生的用户ID|
    |student_name|VARCHAR| |否| | | 学生姓名|
    |sex|VARCHAR| |是| | | 学生性别|
    |age|| |是| | | 学生年龄|
    |class_id|VARCHAR| |否| | | 班级|

<div id="Class"></div>

- ### Class表（班级表）
    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |Class_id|VARCHAR|主键|否| | |班级|
    |major|VARCHAR||否| | |专业|
    |grade|NUMBER||否| | |年级|    

<div id="Courses"></div>

- ### Courses表（课程表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |course_id|VARCHAR|主键|否| | |课程编号|
    |course_name|VARCHAR| |否| | |课程名|
    |date|DATE||否| | |开课学年|
    |term|NUMBER||否| | |开课学期|
    |college|VARCHAR| |否| | |开课学院|


<div id="CourseInfo"></div>

- ### CourseInfo表（学生排课表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |courseInfo_id|VARCHAR|主键|否| | |学生排课编号|
    |student_id|VARCHAR|外键|否| | |学号|

<div id="Tests"></div>

- ### Tests表（实验项目表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |test_id|NUMBER|主键|否| | | 实验编号|
    |course_id|VARCHAR| |否| | | 课程编号|
    |test_name|VARCHAR| |否| | | 实验名称|
    |time|ATE| |否| | | 发布时间|
    |endtime|DATE| |否| | | 截止时间|

<div id="Score"></div>

- ### Score表（学生实验成绩表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |student_id|VARCHAR|主键|否| | | 学生学号|
    |test_id|NUMBER|外键|否| | | 实验编号|
    |score|NUMBER| |否|空| 取值0-100| 分数|
    |mark|VARCHAR| |否|空| | 实验评价|
    |date|DATE| |否|空| |批改日期|
    
<div id="teacher_Score"></div>

- ### teacher_Score表（老师评分表）

    |字段|类型|主键|是否为空|默认值|约束|注释|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |teacher_id|VARCHAR|主键|否| | | 老师编号|
    |student_id|VARCHAR| |否| | | 学生学号|
    |student_name|VARCHAR| |否| | | 学生姓名|
    |course_id|VARCHAR| |否| | |课程编号|
    |test_id|NUMBER| |否| | | 实验编号|
    |score|NUMBER| |否|空| 取值0-100| 分数|
    |mark|VARCHAR| |否|空| | 实验评价|
    |date|DATE| |否|空| |批改日期|
    
    




