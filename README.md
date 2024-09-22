## 本项目实现的最终作用是基于SSH学生网络选课管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 专业管理
 - 修改密码
 - 管理员登录
 - 统计信息
 - 课程管理
### 第2个角色为用户角色，实现了如下功能：
 - 修改登录密码
 - 查询基本信息
 - 查询已选课程
 - 用户角色
 - 选择新课程
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_xuanke

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [tb_course](#tb_course) |  |
| [tb_specialty](#tb_specialty) |  |
| [tb_stucourse](#tb_stucourse) |  |
| [tb_stuuser](#tb_stuuser) |  |
| [tb_userlogin](#tb_userlogin) |  |

**表名：** <a id="tb_course">tb_course</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 课程编号  |
|  2   | name |   varchar   | 255 |   0    |    N     |  N   |       | 课程名称  |
|  3   | schooltime |   varchar   | 255 |   0    |    N     |  N   |       | 上课时间  |
|  4   | addr |   varchar   | 255 |   0    |    N     |  N   |       | 上课地点  |
|  5   | credit |   decimal   | 4 |   0    |    N     |  N   |       | 课程学分  |
|  6   | courseInfo |   varchar   | 255 |   0    |    N     |  N   |       | 课程介绍  |
|  7   | teacherName |   varchar   | 255 |   0    |    N     |  N   |       | 授课教师  |
|  8   | teacherInfo |   varchar   | 255 |   0    |    N     |  N   |       | 教师介绍  |
|  9   | isFinish |   bit   | 1 |   0    |    N     |  N   |       | 是否结课  |
|  10   | specialtyId |   int   | 10 |   0    |    N     |  N   |       | 专业编号  |

**表名：** <a id="tb_specialty">tb_specialty</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 专业编号  |
|  2   | enterYear |   varchar   | 4 |   0    |    N     |  N   |       | 入学年份  |
|  3   | name |   varchar   | 255 |   0    |    N     |  N   |       | 专业名称  |
|  4   | langthYear |   varchar   | 255 |   0    |    N     |  N   |       | 学制  |
|  5   | isFinish |   bit   | 1 |   0    |    N     |  N   |       | 是否毕业  |

**表名：** <a id="tb_stucourse">tb_stucourse</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | stuID |   int   | 10 |   0    |    N     |  N   |       | 学生编号  |
|  2   | courseID |   int   | 10 |   0    |    N     |  N   |       | 课程编号  |
|  3   | id |   int   | 10 |   0    |    N     |  Y   |       |   |

**表名：** <a id="tb_stuuser">tb_stuuser</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 学生编号  |
|  2   | stuName |   varchar   | 255 |   0    |    N     |  N   |       | 学生姓名  |
|  3   | stuNo |   varchar   | 15 |   0    |    N     |  N   |       | 学号  |
|  4   | specialtyId |   int   | 10 |   0    |    N     |  N   |       | 专业编号  |
|  5   | stuSex |   varchar   | 2 |   0    |    N     |  N   |       | 性别  |
|  6   | birthday |   varchar   | 255 |   0    |    N     |  N   |       | 出生日期  |
|  7   | homeAddr |   varchar   | 255 |   0    |    N     |  N   |       | 家庭住址  |
|  8   | tel |   varchar   | 255 |   0    |    N     |  N   |       | 联系电话  |
|  9   | addr |   varchar   | 255 |   0    |    N     |  N   |       | 现住址  |

**表名：** <a id="tb_userlogin">tb_userlogin</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 用户编号  |
|  2   | loginName |   varchar   | 255 |   0    |    N     |  N   |       | 登录名称  |
|  3   | pwd |   varchar   | 255 |   0    |    N     |  N   |       | 登录密码  |
|  4   | type |   varchar   | 1 |   0    |    N     |  N   |       | 用户类型  |
|  5   | mail |   varchar   | 255 |   0    |    N     |  N   |       |   |

