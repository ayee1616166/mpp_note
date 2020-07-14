[toc]

# pg_dump && pg_restore小数据量备份与恢复
```
导出方法:
	pg_dump  -F c -Z 9 testdb >testdb.pg_dump 2>input_testdb.err &
导入方法:
	pg_restore -d testdb -Fc  testdb.pg_dump 2>output_testdb.err &
```


# Greenplum备份与恢复
## 多节点备份 && master恢复数据
```
备份:
gpcrondump -x postgres -a  -C --dump-stats -g -G -h -r --use-set-session-authorization -u /home/gpadmin/back --prefix post    -l /home/gpadmin/log -d $MASTER_DATA_DIRECTORY

恢复:
gpdbrestore -d $MASTER_DATA_DIRECTORY --prefix post -R 127.0.0.1:/home/gpadmin/db_dumps/20160729/
```
## 多节点备份和恢复
```
备份:
gpcrondump -x test -c -g -G -u /home/gpadmin

恢复:
gpdbrestore -t 20160730180431 -u /home/gpadmin -a
```
