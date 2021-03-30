1、ceph cephfs 相关信息
cpu24T 内存96G ssd系统 hhd作为osd
一、cephfs配置
[global]
fsid = f16893ec-12c5-41ac-8d53-7181be0e75c3
public_network = 111.111.111.111/0
cluster_network = 111.111.111.111/0
mon_initial_members = ceph03_node12,ceph03_node13,ceph03_node14,ceph03_node15,ceph03_node16
mon_host = 111.111.111.111,111.111.111.112,111.111.111.113,111.111.111.114,111.111.111.115
auth_cluster_required = abcd
auth_service_required = abcd
auth_client_required = abcd
# Default of 0.05 is too aggressive for my cluster. (seconds)
mon clock drift allowed = 0.1

[osd]
# 20210323 https://support.huaweicloud.com/tngg-kunpengsdss/kunpengcephfile_05_0008.htm
# 20210323 https://documentation.suse.com/ses/6/html/ses-all/tuning-ceph.html
# default 4G
#osd memory target = 12884901888
osd memory target = 8589934592
# default 134217728
osd_memory_cache_min = 4294967296
# default 90
osd_max_write_size = 512
# default 524288000
osd_client_message_size_cap = 2147483648
# default 50
osd_map_cache_size = 1024
# default 5120
osd_journal_size = 20000
# default 10485760
journal_max_write_bytes = 1073714824
# default 100
journal_max_write_entries = 10000
# default 1G
bluestore_cache_size_hdd = 3G
# default 5
osd_op_num_shards_hdd = 12
# default 1
osd_op_num_threads_per_shard_hdd = 2

# 20210326
# default 65536
bluestore_min_alloc_size_hdd = 8192
# defalut 5
osd_op_log_threshold = 50
# defalut 1024
objecter_inflight_ops = 819200
# defalut 104857600
ms_dispatch_throttle_bytes = 1048576000
# defalut 3000
osd_max_pg_log_entries = 100000
# defalut 3000
osd_min_pg_log_entries = 30000
# defalut 1
osd_max_backfills = 4
# defalut 3
osd_recovery_max_active = 10
# defalut 3
osd_recovery_op_priority = 2
# defalut 524288
osd_deep_scrub_stride = 131072
# default 0
osd_scrub_begin_hour = 23
# default 24
osd_scrub_end_hour = 9

二、系统层面
read_ahead_kb

2、
1
