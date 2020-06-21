* 普通插入一条记录：`INSERT INTO 表名(字段1, 字段2, ...) VALUES (值1, 值2, ...)` OR `INSERT 表名 Values (值1, 值2, ...)`
* 插入多条记录：`INSERT INTO 表名(字段1, 字段2, ...) VALUES (值1, 值2, ...)(...)...`
* 不存在则插入，存在则不操作：`INSERT INTO 表名(字段1, 字段2, ...) VALUES(值1, 值2, ...) ON  DUPLICATE KEY UPDATE 字段1=值`
* 不存在则插入，存在则更新：`INSERT INTO 表名(字段1, 字段2, ...) SELECT (值1, 值2, ...), FROM dual WHERE NOT EXISTS (sql)`
* 不存在则插入，存在则先删除，再插入：
    - `REPLACE INTO 表名(字段1, 字段2, ...) VALUES (值1, 值2, ...)`
    - `REPLACE INTO 表名(字段1, 字段2, ...) SELECT 值1, 值2, ...`
    - `REPLACE INTO 表名 SET 字段1=值1, ...`
