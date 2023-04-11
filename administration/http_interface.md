为了方便维护StarRocks集群，StarRocks不同组件的web server提供了不同类型的的操作和查询接口，本文列举当前版本提供的所有HTTP 接口和使用方法。

# FE
# BE
| HTTP请求方法       | HTTP请求路径                                                     | 描述                                                                                                                |
|------------------| --------------------------------------------------------------  |-------------------------------------------------------------------------------------------------------------------- |
| PUT              | /api/{db}/{table}/_stream_load                                  | stream load操作，详见 [stream load](https://docs.starrocks.io/zh-cn/latest/loading/StreamLoad)                                |
| POST/PUT         | /api/transaction/{txn_op}                                       | stream load事务接口，详见 [stream load事务](https://docs.starrocks.io/zh-cn/latest/loading/Stream_Load_transaction_interface)     |
| GET              | /api/{db}/_load_info
| GET              | /api/_set_config?config_key1=config_value1                      | 更新FE配置                                                                                                            |
| GET              | /api/_get_ddl?db={}&tbl={}                                      | 查看表DDL语句
| GET              | /api/_migration?db={}&tbl={}                                    | 查看表的tablet信息                                                                                                    |
| GET              | /api/_check_storagetype
| POST             | /api/{db}/{label}/_cancel
| GET              | /api/{db}/get_load_state
| GET              | /api/health
| GET              | /metrics?type={core/json}                                       | 查看当前FE的metrics                                                                                                |
| GET              | /api/show_meta_info
| GET              | /api/show_proc
| GET              | /api/show_runtime_info
| HEAD/GET         | /api/get_log_file
| GET              | /api/get_small_file
| GET              | /api/rowcount
| GET              | /api/check_decommission
| GET              | /api/_meta_replay_state
| POST             | /api/colocate/bucketseq
| GET              | /api/colocate
| POST             | /api/colocate/group_stable
| POST             | /api/colocate/group_unstable
| POST             | /api/colocate/update_group
| POST             | /api/global_dict/table/enable
| GET              | /api/profile?query_id={}                                        | 获取指定query id的profile信息                                                                                       |
| GET              | /api/query_detail
| GET              | /api/connection
| GET              | /api/show_data?db={}                                            | 查询指定db的大小                                                                                                    |
| POST             | /api/query_dump                                                 | 获取query dump 信息，详见 [query dump](https://docs.starrocks.io/zh-cn/latest/faq/Dump_query)                        |
| GET              | /api/stop
| GET              | /image
| GET              | /info
| GET              | /version
| GET              | /put
| GET              | /journal_id
| GET              | /check
| GET              | /dump
| GET              | /role
| GET              | /api/{db}/{table}/_count                                       
| GET              | /api/{db}/{table}/_schema                                      | 查看表结构                                                                                                          |
| GET/POST         | /api/{db}/{table}/_query_plan

# BE
| HTTP请求方法       | HTTP请求路径                                                     | 描述                                                                                                                |
|------------------| --------------------------------------------------------------  |-------------------------------------------------------------------------------------------------------------------- |
| PUT              | /api/{db}/{table}/_stream_load                                  | stream load操作，详见 [stream load](https://docs.starrocks.io/zh-cn/latest/loading/StreamLoad)                          |
| POST/PUT         | /api/transaction/{txn_op}                                       | stream load事务接口，详见 [stream load事务](https://docs.starrocks.io/zh-cn/latest/loading/Stream_Load_transaction_interface)   |
| PUT              | /api/transaction/load                                           |
| HEAD/GET         | /api/_download_load                                             |
| HEAD/GET         | /api/_tablet/_download                                          |
| HEAD/GET         | /api/_load_error_log                                            |
| GET              | /api/health                                                     |
| GET              | /api/_stop_be                                                   |
| GET              | /pprof/heap                                                     |
| GET              | /pprof/growth                                                   |
| GET              | /pprof/profile                                                  |
| GET              | /pprof/pmuprofile                                               |
| GET              | /pprof/contention                                               |
| GET              | /pprof/cmdline                                                  |
| HEAD/GET/POST    | /pprof/symbol                                                   |
| GET              | /metrics                                                        | 查看当前BE的metrics                                                                                                 |
| HEAD             | /api/meta/header/{tablet_id}                                    |
| GET              | /api/checksum                                                   |
| GET              | /api/reload_tablet                                              |
| POST             | /api/restore_tablet                                             |
| GET              | /api/snapshot                                                   |
| GET              | /api/compaction/show?tablet_id={}                               | 查看指定tablet compaction信息
| POST             | /api/compact?tablet_id={}&compaction_type={base/cumulative}     | 手动对指定tablet进行compaction                                                                                       |
| GET              | /api/compaction/show_repair                                     |
| PUT              | /api/compaction/submit_repair                                   |
| POST             | /api/update_config                                              | 更新BE配置，详见[更新BE配置](https://docs.starrocks.io/zh-cn/latest/administration/Configuration#be-%E9%85%8D%E7%BD%AE%E9%A1%B9)  |
| GET/PUT          | /api/runtime_filter_cache/{action}                              |
| POST             | /api/compact_rocksdb_meta                                       |
| GET/PUT          | /api/query_cache/{action}                                       |
| GET              | /api/pipeline_blocking_drivers/{action}                         |
| GET              | /greplog                                                        |
| GET              | /varz                                                           | 查看当前BE配置                                                                                                       |



# CN

| HTTP请求方法       | HTTP请求路径                                                     | 描述                                                                                                                |
|------------------| --------------------------------------------------------------  |-------------------------------------------------------------------------------------------------------------------- |
| GET              | /api/health                                                     |
| GET              | /pprof/heap                                                     |
| GET              | /pprof/growth                                                   |
| GET              | /pprof/profile                                                  |
| GET              | /pprof/pmuprofile                                               |
| GET              | /pprof/contention                                               |
| GET              | /pprof/cmdline                                                  |
| HEAD/GET/POST    | /pprof/symbol                                                   |
| GET              | /metrics                                                        | 查看当前CN的metrics                                                                                                 |