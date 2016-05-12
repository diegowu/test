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
| -- | -- | -- | -- | -- | -- |
| id | int(10) unsigned |  |NO | 是 | 编号 |
| qid | int(11) | 0 | NO |  | 请求id |
| day | int(11) |  | NO |  | 申请某一天 |

** 领队评价表 **`yxk_leader_evaluation` 
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
| userid | int(11) | 0 | NO |  | 前台评价者id |
| user_name | int(11) | 0 | NO |  | 前台评价者name |
| userid | int(11) | 0 | NO |  | 前台评价者id |