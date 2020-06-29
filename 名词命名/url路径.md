url路径命名常见的类型有：
**普通路径命名**
* 动词 下划线方式
* 小驼峰方式

**restful**
**用户相关**
* 登录：login    PUT
* 注册：register POST
* 注销：logout   DELETE
* 用户信息：user_info GET
* 修改信息：user_info PUT（完整）
* 修改信息：user_info PATCH（完整）
* 用户列表：user_list GET

**文件相关**
* 上传：upload POST
* 下载：download GET
* 文件信息：file_info GET

**任务相关**
* 任务信息：task GET
* 发布任务：task POST
* 更新任务：task PUT（完整）
* 更新任务：task PATCH（部分）
* 删除任务：task DELETE
* 任务列表：task_list GET

**积分配置相关**
* 积分配置信息：credit_configure GET
* 新增积分配置：credit_configure POST
* 更新积分配置：credit_configure PUT（完整）
* 更新积分配置：credit_configure PATCH（局部）
* 删除积分配置：credit_configure DELETE
* 积分配置列表：credit_configure_list GET

**积分相关**
* 积分信息：credit GET
* 新增积分：credit POST
* 积分列表：credit_list GET

**微信授权相关**
* 获取openid：openid GET
