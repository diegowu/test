** 葵花宝典-常用文档表 **`yxk_article` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(11) |  |NO | 是 | 编号 |
| cid | int(11) | 0 | NO |  | 分类id |
| title | varchar(60) |  | NO |  | 文档标题 |
| content | text |  | NO |  | 文档内容 |
| weight | int(11) | 10 | yes |  | 权重 |
| click | int(11) | 0 | yes |  | 点击次数 |
| createtime | datetime |CURRENT_TIMESTAMP | yes |  | 创建时间 |

** 葵花宝典-分类表 **`yxk_cat_article` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(11) |  |NO | 是 | 编号 |
| pid | int(11) | 0 | NO |  | 父id |
| name | varchar(20) |  | NO |  | 分类名 |

** 公司表 **`yxk_company_info` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| cid | tinyint(4) |  |NO | 是 | 主键id |
| companyName | varchar(128) | 0 | NO |  | 公司名称 |
| companyfullname | varchar(128) |  | yes |  | 公司名称全称 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 领队反馈表 **`yxk_fadeback` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(10) unsigned |  |NO | 是 | 主键id |
| lid | int(11) |  | NO |  | 领队id |
| title | varchar(50) |  | yes |  | 标题 |
| content | text |  |  |  | 反馈内容 |
| reply | text |  |  |  | 回复 |
| createtime | datetime |  |  |  | 创建时间 |

** 领队群组表 **`yxk_group` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gid | smallint(6) |  |NO | 是 | 主键id |
| tr_id | mediumint(9) |  | NO |  | 路线id |
| isdel | enum('0','1')  |  | NO |  | 0删除 1正常 |
| createtime | datetime |  |  |  | 创建时间 |

** 领队群组成员表 **`yxk_group_leader` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gl_id | int(11) |  |NO | 是 | 主键id |
| lid | smallint(6) |  | NO |  | 领队ID |
| gid | smallint(6)  |  | NO |  | 群组ID |
| createtime | datetime |  |  |  | 创建时间 |

** 出团计划表 **`yxk_group_plans` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gl_id | int(11) |  |NO | 是 | 主键id |
| ID | int(11) | 0 | NO |  | 领队ID |
| cid | tinyint(4)  | 1 | NO |  | 所属公司id |
| teamno | varchar(32) |  | NO |  | 团号 |
| teamname | varchar(512) |  | NO |  | 团队名称 |
| starttime | date |  | NO |  | 开始时间 |
| endtime | date |  | NO |  | 结束时间 |
| group | varchar(64) |  | NO |  | 组团社 |
| people | varchar(64) |  | NO |  | 人数 |
| localtravelagency | varchar(32) |  | yes |  | 地接社 |
| localguide | varchar(64) |  | yes |  | 地陪 |
| guide | varchar(256) |  | yes |  | 全陪 |
| driver | varchar(64) |  | yes |  | 司机 |
| emergencyphone | varchar(64) |  | yes |  | 紧急联系电话 |
| roomnumber | varchar(32) |  | yes |  | 用房数量 |
| departuretimeandplace | varchar(256) |  | yes |  | 出发地点与时间 |
| platenumber | varchar(32) |  | yes |  | 车牌号 |
| seating | varchar(32) |  | yes |  | 车位数量 |
| money | varchar(16) | 0 | yes |  | 领队备用金 |
| Batch | tinyint(4) |  | NO |  | 老：批次 |
| plans_type | enum('1','2') |  | NO |  | 1=活动团 2=企业团 |
| personnel | enum('0','1') | 0 | yes |  | 废弃 0未上传名单 1已经上传名单 |
| isevaluation | enum('0','1') | 0 | yes |  | 0未对全陪评价，1已经评价 |
| state | char(1) |  | yes |  | 状态(未启用) |
| isdel | enum('0','1') | 0 | yes |  | 0正常，1删除 |
| isold | enum('0','1') | 0 | yes |  | 废弃 0新版出团计划,1老版出团计划 |
| operator | varchar(32) |  | yes |  | 创建人 |
| createtime | timestamp| CURRENT_TIMESTAMP | yes |  | 创建时间 |
| bid | int(11) | 0 | yes |  | 分车id |
| batch_id | smallint(4) | 1 | yes |  | 批次id |

** 出团计划-草搞表 **`yxk_group_plans_draft` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gpd_id | int(11) |  |NO | 是 | 主键id |
| plans_type | enum('1','2') | 1 | NO |  | 出团计划类型 |
| fileName | varchar(128) |  | NO |  | 文件名 |
| founder | varchar(32) |  | NO |  | 作者 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |
| teamno | varchar(64) |  |  |  | 出团单号 |
| lid | int(11) |  | NO |  | 领队ID |

** 出团计划-费用表 **`yxk_group_plans_fee` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gpd_id | int(11) |  |NO | 是 | 主键id |
| gp_id | int(11) |  |  |  | 出团计划ID |
| items | varchar(64) |  | NO |  | 项目 |
| detail | text |  | NO |  | 明细 |
| payments | varchar(128) |  | NO |  | 款项支付 |
| operator | varchar(32) |  |  |  | 操作人 |
| isdel | enum('1','0') | 0 | NO |  | 0 正常  1删除 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 出团计划-全陪表 **`yxk_group_plans_leader` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gpd_id | int(11) |  |NO | 是 | 主键id |
| gp_id | int(11) |  |  |  | 出团计划ID |
| lid | smallint(6) |  | NO |  | 领队ID |
| tr_id | mediumint(9) |  |  |  | 旅游路线 |
| nick | varchar(32) |  | NO |  | 昵称 |
| phone | varchar(32) |  | NO |  | 电话 |
| teamno | varchar(32) |  | NO |  | 团号 |
| leader_type | enum('1','2','4','3') |  | NO |  | 1=主领队 2=副领队 3=跟队 4=主副不分 |
| isread | enum('0','1') | 0 |  |  | 该出团计划领队是否读过，0 未读，1 已读 |
| have_log | enum('0','1') | 0 |  |  | 出团计划该领队是否生成日志，0 未生成，1 已生成 |
| isdel | enum('1','0') | 0 |  |  | 0正常 1删除|
| isedit | enum('0','1') | 0 |  |  | 0未修改 1修改 |
| operator | varchar(32) | 0 |  |  | 操作人 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 出团计划-分表 **`yxk_group_plans_old` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| gpo_id | int(11) |  |NO | 是 | 主键id |
| gp_id | int(11) |  |  |  | 出团计划ID |
| prepare | text |  |  |  | 领队准备 |
| focus | text |  |  |  | 活动亮点 |
| collection | text |  |  |  | 集合时间 |
| planfee | text |  |  |  | 活动费用 |
| isdel | enum('0','1') |  |  |  | 0正常  1删除 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 信息通知表 **`yxk_information` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| infor_id | int(11) |  |NO | 是 | 主键id |
| gp_id | int(11) |  |  | NO | 出团计划ID |
| send_lid | int(11) |  |  | NO | 接受者id |
| accept_id | int(11) |  |  | NO | 出团计划ID |
| information | varchar(256) |  |  | NO | 发送的信息 |
| isread | enum('0','1') | 0 |  | NO | 0未读 1已读 |
| createtime | timestamp | CURRENT_TIMESTAMP | NO |  | 创建时间 |


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
| lid | smallint(6) |  | yes |  | 领队id |
| things | varchar(512) |  | yes |  | 主键id |
| starttime | date | 0000-00-00 | yes |  | 开始时间 |
| endtime | date | 0000-00-00 | yes |  | 结束时间 |
| comefrom | enum('1','2','3') |  | yes | | 由谁安排？ 1自己 2公司 3计调安排的档期 |
| gp_id | int(11) |  | NO |  | 来自出团计划安排 |
| tr_id | int(11) |  | NO |  | 预安排路线id |
| isdel | enum('0','1') | 0 | NO |  | 0未删除 1删除 |
| edit_personne | varchar(24) |  | NO | | 谁做的修改 |
| operator | varchar(32) |  | NO |  |  |
| createtime | int(11) |  | NO |  | 创建时间 |

** 领队点赞表 **`yxk_leader_zhan` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(11) |  | NO | 是 | 主键id |
| lid | int(11) |  | NO |  | 领队id |
| uid | int(11) |  | NO |  | 用户id |
| createtime | int(11) |  | NO |  | 点赞时间 |

** 领队点赞日志表 **`yxk_leader_zhan_log` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| id | int(11) |  | NO | 是 | 主键id |
| uid | int(11) |  | NO |  | 用户id |
| lid | int(11) |  | NO |  | 被点赞lid |
| user_ip | varchar(15) |  | NO |  | 用户ip |
| source | int(11) |  | NO |  | 点赞来源(pc、wap)|
| add_time | int(11) |  | NO |  | 点赞时间 |

** 地接社表 **`yxk_local_travel_agency` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| lta_id | int(11) |  | NO | 是 | 主键id |
| travelName | varchar(128) |  | NO |  | 旅行社名字 |
| contacName | varchar(64) |  | NO |  | 联系人 |
| phone | varchar(26) |  | NO |  | 联系人电话 |
| createTime | timestamp |  | NO |  | 创建时间 |
| cid | tinyint(4) | 1 | NO |  | 所属分站id |

** 领队日志表 **`yxk_log` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| log_id | int(11) unsigned |  | NO | 是 | 日志id |
| lid | smallint(6) |  | NO |  | 领队ID |
| gp_id | mediumint(9) |  | NO |  | 出团计划ID |
| tr_id | mediumint(9) |  | NO |  | 路线ID |
| teamno | varchar(128) |  | NO |  | 团号 |
| travelName | varchar(256) |  | NO |  | 团队名称 |
| starttime | date |  | NO |  | 团队时间 |
| endtime | date |  | NO |  | 结束时间 |
| people | varchar(32) |  | NO |  | 团队人数 |
| guide | varchar(32) |  | NO |  | 导游 |
| localtravelagency | varchar(64) |  | NO |  | 地接社 |
| localguide | varchar(32) |  | NO |  | 地接导游 |
| localguideservice | varchar(64) |  | NO |  | 地接导游服务 |
| driver | varchar(32) |  | NO |  | 司机 |
| platenumber | varchar(32) |  | NO |  | 车牌号 |
| seating | varchar(32) |  | NO |  | 车辆座位数 |
| vehiclecondition | varchar(64) |  | NO |  | 车辆情况 |
| driverservice | varchar(128) |  | NO |  | 司机服务 |
| summary | text |  | yes |  | 导游总结 |
| top | enum('0','1') | 0 | yes |  | 是否置顶 |
| operator | varchar(32) |  | yes |  | 操作人 |
| state | char(1) |  | yes |  | 日志状态 |
| isdel | enum('1','0')| 0 | yes |  | 0正常，1删除 |
| createtime | timestamp |  | yes |  | 创建时间 |
| updatetime | timestamp |  | yes |  | 更新时间 |
| is_share | tinyint(1) |  | yes |  | 是否共享 |

** 领队日志-行程安排表 **`yxk_trip` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| tid | int(11) |  | NO | 是 | 主键id |
| log_id | int(10) unsigned |  | NO |  | log表的id |
| tripdate | varchar(32)  |  | NO |  | 行程日期 |
| accommodation | varchar(255) |  | yes |  | 住宿 |
| catering | varchar(255)  |  | yes |  | 餐饮 |
| tickets | varchar(255)  |  | yes |  | 门票 |
| tripsuggest | text  |  | yes |  | 行程建议 |
| tripsummary | text  |  | yes |  | 行程/耗时 |
| operator | varchar(32)  |  | yes |  | 操作人员 |
| isdel | enum('0','1')  | 0 | yes |  | 0正常 1删除 |
| createtime | timestamp  | CURRENT_TIMESTAMP | yes |  | 创建时间 |
| operator | varchar(32)  |  | yes |  | 操作人员 |
| images | text  |  | yes |  | 行程中的图片 |

** 操作记录表 **`yxk_operation_records` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| ori_id | int(11)  |  | NO | 是 | 主键id |
| record_type | int(4) | 0 | NO |  | 记录类型，0领队与账号记录 ，1出团计划记录，2个人档期记录 |
| operation_way | enum('a','d','u','on','off') |  | NO |  | 操作类型，a添加操作，d删除操作，u修改操作,on是开启,off是关闭操作 |
| operation_records | varchar(512) |  | NO |  | 操作记录信息|
| operation_personnel | varchar(32) |  | NO |  | 操作人员|
| operation_time | timestamp |  | NO |  | 执行操作的时间|

** 省份表 **`yxk_provincial_table` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| zipcode | mediumint(9)  |  | NO | 是 | 主键id,邮编号 |
| name | varchar(32) |  | NO |  | 省名 |
| pinyin | varchar(32)  |  | NO |  | 省的拼音 |

** 旅行线路表 **`yxk_route` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| ID | int(11) |  | NO | 是 | 主键id |
| CID | mediumint(9) |  | NO |  | 圈子流水号??? |
| AName | varchar(512)  |  | NO |  | 路线名称 |
| Province | varchar(32)  |  | NO |  | 路线所属省 |
| isdel | enum('0','1')  |  | NO |  | 0删除 1正常 |
| createtime | timestamp  | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 旅行线路表（共享日志时会用到tr_id,跟上面有重叠，也有不同） **`yxk_travel_route` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| tr_id | mediumint(9) |  | NO | 是 | 主键id |
| zipcode | mediumint(9) |  | NO |  | 省份id |
| route_name | varchar(128)  |  | NO |  | 路线名称 |
| isdel | enum('0','1') | 0 | NO |  | 0删除 1正常 |
| cid | tinyint(4)  | 1 | NO |  | 分站id |
| createtime | timestamp  | CURRENT_TIMESTAMP | NO |  | 创建时间 |

** 用户密码表 **`yxk_user_info` 

|字段名|数据类型|默认值|允许非空|自动递增|备注|
| -- | -- | -- | -- | -- | -- |
| uid | smallint(6) |  | NO | 是 | 主键id |
| lid | smallint(6) |  | NO |  | 领队id |
| loginname | varchar(64)  |  | NO |  | 登陆名 |
| nick | varchar(32) | 0 | NO |  | 昵称 |
| password | varchar(64)  | 1 | NO |  | 密码 |
| lastlogintime | timestamp  | 0000-00-00 00:00:00 | NO |  | 最后登陆时间 |
| createtime | timestamp  | 0000-00-00 00:00:00 | NO |  | 创建时间 |
| state | enum('0','1')  | 1 | NO |  | 已废弃 1正常,0禁用 |
| role | tinyint(4)  | | NO |  | 已废弃 角色 |

















