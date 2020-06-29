`SELECT * FROM 表名`

**时间相关**
* 统计今天：`WHERE to_days(时间字段名) = to_days(now())`
* 统计昨天
* 统计本周：`WHERE YEARWEEK(date_format(createtime,'%Y-%m-%d')- INTERVAL 1 DAY) = YEARWEEK(now())`
* 统计上周
* 统计7天：`WHERE DATE_SUB(CURDATE(), INTERVAL 7 DAY) <= date(时间字段名)`
* 近30天：`WHERE DATE_SUB(CURDATE(), INTERVAL 7 DAY) <= date(时间字段名)`
* 统计本月：`WHERE date_format(时间字段名,'%Y-%m')=date_format(now(),'%Y-%m')`
* 统计上个月：`WHERE PERIOD_DIFF( date_format(now(), '%Y%m') , date_format(时间字段名, '%Y%m')) =1`
* 统计本季度：`WHERE QUARTER(时间字段名)=QUARTER(now())`
* 统计上季度：`WHERE QUARTER(时间字段名)=QUARTER(DATE_SUB(now(),interval 1 QUARTER))`
* 统计今年：`WHERE YEAR(时间字段名)=YEAR(NOW())`
* 统计去年：`WHERE year(时间字段名)=year(date_sub(now(),interval 1 year))`

**数量相关**
* 前n条：`SELECT ... FROM 表名 ... LIMIT n` 或者 `SELECT ... FROM 表名 ... LIMIT 0, n`
* 第n条：`SELECT ... FROM 表名 ... LIMIT n-1, 1` 或者 `SELECT ... FROM 表名 ... limit n OFFSET n-1`
* 从m条开始n条：`SELECT ... FROM 表名 ... LIMIT m, n`
* 最后n条：`SELECT ... FROM 表名 ... LIMIT -n`
* 总共多少条：`SELECT COUNT(*) FROM 表名 ...`