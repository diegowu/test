** 领队申请表 **`yxk_leader_apply` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | mediumint(8) unsigned |  |NO | 是 | 编号 |
| lid | int(11) | 0 | NO |  | 领队id |
| cat | varchar(20) |  | yes |  | 申请的分类 |
| mdd | text |  | yes |  | 申请的目的地 |
| beizhu | varchar(11) |  | yes |  | 待删除 |
| op | varchar(20) |  | yes |  | 操作者 |
| status | int(11) | 0 | yes |  | 0,未处理 1,已通过 -1,	已拒绝 -2,已取消 |
| op_id | int(11) | 0 | yes |  | 操作者ID |
| create_time | int(11) | 0 | yes |  | 创建时间 |
| update_time | int(11) | 0 | yes |  | 更新时间 |
| day_history | text | 0 | yes |  | 历史申请天数 |
| chat01 | text |  | yes |  | 导服与领队沟通记录 |
| chat02 | text|  | yes |  | 导服与计调沟通记录 |
| notice | tinyint(1)| 1 | yes |  | 是否通知领队 |
| is_del | tinyint(1)| 0 | yes |  | 是否已删除 |
| is_read | tinyint(1) | 0 | yes |  | 是否阅读 |

** 领队申请日期表 **`yxk_leader_applyday` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(10) unsigned |  |NO | 是 | 编号 |
| qid | int(11) | 0 | NO |  | 请求id |
| day | int(11) |  | NO |  | 申请某一天 |

** 领队评价表 **`yxk_leader_evaluation` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| le_id | int(11)  |  |NO | 是 | 编号 |
| lid | smallint(6) | 0 | NO |  | 领队id |
| gp_id | int(11) |  | NO |  | 出团计划id |
| responsibility | varchar(12) |  | NO |  | 责任心 |
| temper_character | varchar(12) |  | NO |  | 脾气性格 |
| organization_ability | varchar(12) |  | NO |  | 组织能力 |
| professional | varchar(12) |  | NO |  | 专业程度 |
| describe | varchar(256) |  | NO |  | 描述 |
| reviewers | varchar(32) |  | NO |  | 评论者 |
| operation | varchar(32) |  | NO |  | 操作者 |
| create_time | timestamp |  | NO |  | 创建时间 |
| cat | tinyint(4) | 1 | NO |  | '1客人评价 2内部评价 3马甲评价' |
| status | tinyint(4) | 0 | NO |  | -1审核不通过 0待审核 1审核通过 -2删除 |
| userid | int(11) |  | yes |  | 前台评价者id |
| user_name | varchar(30) |  | yes |  | 前台评价者name |
| content | text |  | yes |  | 评论内容|
| reply | varchar(256) |  | yes |  | 前台领队回复|

** 领队信息表 **`yxk_leader_info` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| lid | smallint(6) |  | NO | 是 | 领队id |
| cid | tinyint(4)  |  |NO |  | 所属公司编号 |
| nick | varchar(32)  |  |NO |  | 昵称 |
| name | varchar(32)  |  |NO |  | 真实名字 |
| pinyin | char(1)  |  |NO |  | 昵称的首字母 |
| sex | enum('男','女')  |  |NO |  | 性别 |
| category | varchar(32)  |  |NO |  | 已废弃 |
| phone | varchar(16)  |  |NO |  | 手机号码 |
| level | enum('A','B','C','D')  |  |yes |  | 领队级别A优秀 B良 C合格 D暂时没资格带队 |
| qq | varchar(16)  |  |yes |  | QQ号码 |
| cardno | varchar(32)  |  |NO |  | 身份证号码 |
| linkman | varchar(32)  |  |yes |  | 紧急联系人 |
| linkmanphone | varchar(16)  |  |yes |  | 紧急联电话 |
| company | varchar(32)  |  |yes |  | 工作单位 |
| career | varchar(32)  |  |yes |  | 职业 |
| contract | varchar(32)  |  |yes |  | 合同 |
| isguide | enum('0','1')  |  |yes |  | 有无导游证 |
| isleader | enum('0','1')  |  |yes |  | 有无领队证 |
| guideno | varchar(32)  |  |yes |  | 导游证号 |
| leaderno | varchar(32)  |  |yes |  | 领队证号 |
| remark | varchar(32)  |  |yes |  | 备注 |
| jobstate | enum('1','2','-1')  |  |yes |  | 1实习 2正式 -1停用 |
| total_score | int(11)  | 0 |NO |  | 总分 |
| evaluation_number | int(11)  | 0 |NO |  | 评价次数 |
| average | float(11,2)  | 0.00 |NO |  | 平均分 |
| state | enum('0','1')  |  |yes |  | '0停用，1正常' |
| isdel | enum('0','1')  |  |yes |  | '0、正常,1、删除' |
| haveaccount | enum('0','1')  | 0 |yes |  | 0表示未创建登陆账号,1已创建 |
| operator | varchar(32)  | 0 |yes |  | '创建人' |
| photo | varchar(100)  |  |yes |  | 自定义头像 |
| createtime | timestamp  | CURRENT_TIMESTAMP |NO |  | 创建时间 |
| zhaopian | varchar(200) | 0 |yes |  | 工作照片 |
| cat | varchar(13)  |  |yes |  | 领队分类 |
| click | int(10)  | 100 |yes |  | 点击次数 |
| sign | varchar(100)  |  |yes |  | 个性签名 |
| score1 | float(10,1)  | 5.0 |yes |  | 责任心平均分 |
| score2 | float(10,1)  | 5.0 |yes |  | 性格分平均分 |
| score3 | float(10,1)  | 5.0 |yes |  | 组织能力分平均分 |
| score4 | float(10,1)  | 5.0 |yes |  | 专业度分平均分 |
| uid | int(11)  |  |yes |  | 用户id(个人领地id) |
| zhan | int(20)  |  |yes |  | 点赞数 |
| weight | int(11)  |  |yes |  | 领队权重 |
| addr | varchar(255)  |  |yes |  | 领队详细住址 |

** 领队感谢信表 **`yxk_leader_thanks` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(10) unsigned |  | NO | 是 | id |
| lid | int(11) | 0 | yes |  | 领队id |
| uid | int(11) | 0 | yes |  | 用户id |
| username | smallint(6) |  | yes |  | 用户名 |
| title | varchar(20) |  | yes |  | 标题 |
| content | text |  | yes |  | 感谢信内容 |
| weight | int(10) |  | yes |  | 权重 |
| click | int(11) | 0 | yes |  | 点击次数 |
| op | varchar(255) | 0 | yes |  | 操作者 |
| createtime | smallint(6) |  | yes |  | 创建时间 |
| img | varchar(255) |  | yes |  | 感谢信内容 |

** 领队时间安排表 **`yxk_leader_time_arrange` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| lta_id | int(11) |  | NO | 是 | 主键id |
































