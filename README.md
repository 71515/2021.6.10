# 2021.6.10
深蓝杯比赛

数据库：
create table `user`(
userId int PRIMARY key auto_increment, -- 自增主键 消除主键插入异常
userPhone varchar(20) not null,
userPassword varchar(20) not null
)

create table plan(
planId int primary key auto_increment,
planPhone varchar(20) not null, -- 手机号
planContent varchar(200), -- 内容
planStartTime datetime not null,  -- 计划开始时间
planRemindStartTime datetime not null, -- 提醒开始时间
planRemindEndTime datetime not null, -- 提醒结束时间
planRemindState int, -- 提醒状态 默认为开启状态 0代表开启提醒 1代表关闭提醒
planCompleteState int, -- 完成状态 默认为未完成状态 0代表未完成 1代表完成
planEvaluate varchar(200) -- 评价 默认为空
)

2021.6.9
1.0搭建整体框架 mvc+mybatis 如果找不到某些jar包需要把mawen中的包导入项目lib下(file Projectstrucure artifacts 将右边的包导出到lib下)
2.0完成登录，注册模块(未完成)

2021.6.10
1.0完成登录，注册，修改密码，注销功能(完成)
2.0拦截缓存登录以及未登录用户访问主页面,以及匹配字符(完成)
3.0遗留问题，控制器使用太多重定向，造成重定向过多 错误码为302 -----------------

2021.6.11
1.0完成管理规划信息模块设计 需要完成增加,查询规划信息(完成)
2.0完成修改，删除规划信息

2021.6.12
1.0完善增加信息（当计划完成时将状态设置为1）将未完成信息按照开始的先后顺序排列
2.0处理重定向问题(遗留问题 跳转页面有问题)
3.0 ****增加过时计划浏览(考虑计划过时问题 当触发消息提醒时将计划加入消息队列 服务器启动时消息队列也开始)以及定时消息推送 (没完成)
(当前时间大于设置的开始时间 将任务标记1即失效)(不做)
4.0添加评价功能(未完成)

2021.6.13
1.0在查询信息时更新任务的完成状态(完成)
2.0处理从前端提交的数据需重定向

2021.6.14
1.0增加一个分页功能 将需要展示的信息封装到页面控制中 (缓存分页 降低数据库压力)
2.0只更新自身的状态（完成)
3.0退出使用浏览器的回退出现问题(完成)
