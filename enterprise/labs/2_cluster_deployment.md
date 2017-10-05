{
  "timestamp" : "2017-10-05T13:48:23.051Z",
  "clusters" : [ {
    "name" : "andrescruzat",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "dataDir",
            "value" : "/var/log/zookeeper"
          }, {
            "name" : "dataLogDir",
            "value" : "/var/log/zookeeper"
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        } ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "13h2s80xyw4hyegejcn9g0kto"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6m4qaarbykz9qcchlciqpjjlj"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "48tp9u20zewbc6zqelxgivl5b"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "10992"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "16650"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
          } ]
        } ],
        "items" : [ {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "eaW8IO9MnDMKfDAk9rCC2nB2yLJZ4h"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-d5952b29ce39ccddc9575298d515399a",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "role_jceks_password",
            "value" : "auccc1oyxfafor2l1bpt91zxv"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2qzasupp8sw37zhssnx7jswrk"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3lhvuncfxs799ojqeipwgilg6"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bnpy0ct6b5nrxhj1rmkvjms25"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-d5952b29ce39ccddc9575298d515399a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4z56sd21g7ob6idjf0aimkm0u"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "37"
          }, {
            "name" : "role_jceks_password",
            "value" : "a6ojj04dbifnp8894vxxuufb0"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disco1/dfs/dn,/disco2/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "FAILOVERCONTROLLER",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "HTTPFS",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/disco2/dfs/jn"
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disco1/dfs/nn,/disco2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disco1/dfs/snn"
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "qn28Oe0YtOU8xw4bYt8APXmLrN8dKu"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "MnMK2a7zDLT1dJy2aKvJxMsLpGIOpF"
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "fV100qg5VitAFuorsqaoAPk4fne4dE"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9c1hlczj1hiwpp98nillem9t"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aejq4c52sfhqnjevnumapuryp"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "95jwzk27jv8vc2ylbrita5ayl"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-d5952b29ce39ccddc9575298d515399a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "594xztzgn1gsftp1l2752rafk"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ca40wr3ra1q7vgxuw79pn5pju"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "39rx6haei0pnbitbpd8mn171w"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cq4s7tuf6lgbkv4ujx0qqr97g"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ccfrrf4q37e8j89nhi5tzmxe9"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6kxgwjzlgboi2w8df9m2ycxb7"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-d5952b29ce39ccddc9575298d515399a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "88pqabrezk9ohcu3v0mapn6id"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "ClouderaBCHA"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "ClouderaBCHA"
          }, {
            "name" : "namenode_id",
            "value" : "45"
          }, {
            "name" : "role_jceks_password",
            "value" : "bp4gu3b8pffawy5aed18jf3uy"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "ClouderaBCHA"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "ClouderaBCHA"
          }, {
            "name" : "namenode_id",
            "value" : "39"
          }, {
            "name" : "role_jceks_password",
            "value" : "ef3jehbxcrrb8wckij5780m6m"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "858993459"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "52428800"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "6"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "9797055283"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "1648"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-09a8971997ed81555c5f44b91d6ffdc0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-d5952b29ce39ccddc9575298d515399a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-09a8971997ed81555c5f44b91d6ffdc0",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8tn92mw9eo03a1fw5ngj3vqvh"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-d5952b29ce39ccddc9575298d515399a",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "16go8wahzik3g91zkfhqr3dln"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "impala",
      "type" : "IMPALA",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "CATALOGSERVER",
          "items" : [ {
            "name" : "catalogd_embedded_jvm_heapsize",
            "value" : "52428800"
          } ]
        }, {
          "roleType" : "IMPALAD",
          "items" : [ {
            "name" : "impalad_memory_limit",
            "value" : "268435456"
          }, {
            "name" : "scratch_dirs",
            "value" : "/disco1/impala/impalad,/disco2/impala/impalad"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "llama_am_ha_zk_auth_secret_key",
          "value" : "EQOMsqNhTSrxc2Lyc68A5XYRHBRjyI"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        } ]
      },
      "roles" : [ {
        "name" : "impala-CATALOGSERVER-d5952b29ce39ccddc9575298d515399a",
        "type" : "CATALOGSERVER",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "role_jceks_password",
            "value" : "2x91jg2ny278aitilkrqn3gtl"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-0266459cbc739cc5eb9cffbed79e2850",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bvydef48ijkdgu6usjko8gpwx"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2lqtqm1tpoerp6i5o9av62jeg"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2q7es28pcu61x10lzqjg1igkr"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-d5952b29ce39ccddc9575298d515399a",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bms07owj4ja4086w0jar6wdm8"
          } ]
        }
      }, {
        "name" : "impala-STATESTORE-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "STATESTORE",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9q4n736nbcvfv674mkjc8sv92"
          } ]
        }
      } ],
      "displayName" : "Impala"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "oozie_data_dir",
            "value" : "/var/log/oozie/data"
          }, {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-28-62.us-east-2.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "52428800"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-d5952b29ce39ccddc9575298d515399a",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5bd3h9z1baq3r0pfbivvepfre"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HUE_SERVER",
          "items" : [ {
            "name" : "hue_http_port",
            "value" : "18888"
          } ]
        } ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-0266459cbc739cc5eb9cffbed79e2850"
        }, {
          "name" : "impala_service",
          "value" : "impala"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "av6o7c9tg2tx6rjnm9bua2ywq"
          }, {
            "name" : "secret_key",
            "value" : "CRTftwnZezkgqwm5ja4SIhRA22ue0b"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6no0djqw2dnqa4ksv3b8ta6zm"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SENTRY_SERVER",
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,andrescruzat"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-09a8971997ed81555c5f44b91d6ffdc0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
          }, {
            "name" : "role_jceks_password",
            "value" : "59hjllfzuzx4edspijld0qbe5"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3",
    "ipAddress" : "172.31.18.122",
    "hostname" : "ip-172-31-18-122.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3",
    "ipAddress" : "172.31.18.46",
    "hostname" : "ip-172-31-18-46.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43",
    "ipAddress" : "172.31.19.50",
    "hostname" : "ip-172-31-19-50.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1",
    "ipAddress" : "172.31.28.62",
    "hostname" : "ip-172-31-28-62.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c2bde8a2-b96b-44e4-a16e-2e74cf3d4fb2",
    "ipAddress" : "172.31.29.121",
    "hostname" : "ip-172-31-29-121.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__a108c58b-3539-44e0-83a7-b4d6e26ec22b",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c4e91beeb11c201793a521354b6687f7b6754ae34118ad0170e198ed1f598dea",
    "pwSalt" : 3418149914699452095,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ba0138745db2475f55dcbcd20c4d34c6e3efe07cd8ae45f0108c72855d419a82",
    "pwSalt" : -1672808812072807007,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-09a8971997ed81555c5f44b91d6ffdc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "692630536e7cbee4957df5aa1cc80ba0f9b9ea432ae1dd768de1e1b53fdbb2eb",
    "pwSalt" : -4087223889561721550,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3ea8cc7ac20328fef52e15615484d9d3256e3576664adae75eb29346cc38f2f8",
    "pwSalt" : 421607734840800655,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-09a8971997ed81555c5f44b91d6ffdc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "01f4ff4dc59e920e8ee99939c00fa539e9bafb049446112d3d2f87fe78384183",
    "pwSalt" : 7428213649074096312,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f0e9c5e02cb8f0b09bfe78256f79034ddbc1789e245f2fba6ab5f201eeae3635",
    "pwSalt" : 6078148926208772429,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "60fb8e29bb90adafc60f0302825adeba9904894c7917294bed4d34331eaf3c55",
    "pwSalt" : -3563351199965415250,
    "pwLogin" : true
  }, {
    "name" : "andrescruzat",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "6c87f52dc3fb2af0086f41347ff7f48dfe9cc97715c6643336d25955e5156568",
    "pwSalt" : -8939434145405813389,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "c7dd3d37cead3ca1ff50f15019af4dc128fa90321bd6c1e1d04f8bf41f3cce3f",
    "pwSalt" : 4020671908512342563,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.11.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170811-0014",
    "gitHash" : "3c3ea33a12076fb83a8f11c4452c52fac685d01b",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-host-monitor"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-service-monitor"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "8mw5y70d9a4yryvngc1ozklcd"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "9kzsitcvdher54kkwunetgewd"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "eventserver_index_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "3jff7pjc1dahgr5dc00iyysim"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "5eza4qk2zxcrxsus7jjorbvnw"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "reportsmanager_scratch_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "736puq7yvs5ryoih3nts46hfi"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-09a8971997ed81555c5f44b91d6ffdc0",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}"
        }, {
          "name" : "role_jceks_password",
          "value" : "etqwrobqnmvof64dh26j1jxw6"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 18:30"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAABBAAEADkFDUlVaQVRDREguQ09NAAxjbG91ZGVyYS1zY20AAAABWdUWagEAFwAQW3urzDxVlGq8iczEVsPckwAAAAE="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@ACRUZATCDH.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-28-62.us-east-2.compute.internal"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "ACRUZATCDH.COM"
    } ]
  }
}
