{
  "timestamp" : "2017-10-05T14:25:27.656Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "andrescruzat",
    "version" : "CDH5",
    "fullVersion" : "5.11.2",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true",
          "sensitive" : false
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
            "value" : "13h2s80xyw4hyegejcn9g0kto",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "2",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
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
            "value" : "6m4qaarbykz9qcchlciqpjjlj",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "1",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
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
            "value" : "48tp9u20zewbc6zqelxgivl5b",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "3",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ {
            "name" : "dataDir",
            "value" : "/var/log/zookeeper",
            "sensitive" : false
          }, {
            "name" : "dataLogDir",
            "value" : "/var/log/zookeeper",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hadoop_secure_web_ui",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80",
          "sensitive" : false
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "eaW8IO9MnDMKfDAk9rCC2nB2yLJZ4h",
          "sensitive" : true
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "auccc1oyxfafor2l1bpt91zxv",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
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
            "value" : "2qzasupp8sw37zhssnx7jswrk",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
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
            "value" : "3lhvuncfxs799ojqeipwgilg6",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
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
            "value" : "bnpy0ct6b5nrxhj1rmkvjms25",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
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
            "value" : "4z56sd21g7ob6idjf0aimkm0u",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-2"
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
            "value" : "37",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "a6ojj04dbifnp8894vxxuufb0",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16",
            "sensitive" : false
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1",
        "displayName" : "NodeManager Group 1",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "14653",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2",
        "displayName" : "NodeManager Group 2",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "16650",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "800",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "10992",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "16650",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding",
          "sensitive" : false
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "qn28Oe0YtOU8xw4bYt8APXmLrN8dKu",
          "sensitive" : true
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "MnMK2a7zDLT1dJy2aKvJxMsLpGIOpF",
          "sensitive" : true
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos",
          "sensitive" : false
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "fV100qg5VitAFuorsqaoAPk4fne4dE",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
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
            "value" : "9c1hlczj1hiwpp98nillem9t",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
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
            "value" : "aejq4c52sfhqnjevnumapuryp",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
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
            "value" : "95jwzk27jv8vc2ylbrita5ayl",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
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
            "value" : "594xztzgn1gsftp1l2752rafk",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
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
            "value" : "ca40wr3ra1q7vgxuw79pn5pju",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
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
            "value" : "39rx6haei0pnbitbpd8mn171w",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
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
            "value" : "cq4s7tuf6lgbkv4ujx0qqr97g",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-HTTPFS-BASE"
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
            "value" : "ccfrrf4q37e8j89nhi5tzmxe9",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
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
            "value" : "6kxgwjzlgboi2w8df9m2ycxb7",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
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
            "value" : "88pqabrezk9ohcu3v0mapn6id",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
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
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "ClouderaBCHA",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "ClouderaBCHA",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "45",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "bp4gu3b8pffawy5aed18jf3uy",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
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
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "ClouderaBCHA",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "ClouderaBCHA",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "39",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "ef3jehbxcrrb8wckij5780m6m",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824",
            "sensitive" : false
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disco1/dfs/dn,/disco2/dfs/dn",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "200",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/disco2/dfs/jn",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disco1/dfs/nn,/disco2/dfs/nn",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disco1/dfs/snn",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      } ],
      "replicationSchedules" : [ {
        "id" : 4,
        "startTime" : "2017-10-03T13:53:22.678Z",
        "interval" : 0,
        "intervalUnit" : "MINUTE",
        "paused" : false,
        "nextRun" : null,
        "alertOnStart" : false,
        "alertOnSuccess" : false,
        "alertOnFail" : false,
        "alertOnAbort" : false,
        "hdfsArguments" : {
          "sourceService" : {
            "peerName" : "Eduardo",
            "clusterName" : "cluster",
            "serviceName" : "hdfs"
          },
          "sourcePath" : "/user/DKvothe",
          "destinationPath" : "/labs/storage/DKvothe",
          "mapreduceServiceName" : "yarn",
          "numMaps" : 20,
          "dryRun" : false,
          "bandwidthPerMap" : 100,
          "abortOnError" : false,
          "removeMissingFiles" : false,
          "preserveReplicationCount" : true,
          "preserveBlockSize" : true,
          "preservePermissions" : true,
          "skipChecksumChecks" : false,
          "skipTrash" : false,
          "replicationStrategy" : "DYNAMIC",
          "preserveXAttrs" : false,
          "exclusionFilters" : [ ]
        },
        "active" : false
      } ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password",
          "sensitive" : true
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-09a8971997ed81555c5f44b91d6ffdc0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ec4eafa4-a4e8-4f8d-99f5-f9db24c1fae1"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-1d83191a88dcbeba75c97d15188b08ab",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "7d1d67f3-aab0-479b-988b-c48425e17d43"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-505ce28cfc5b3390912d6e8957f312fe",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "97bb53ed-e3f3-4cdf-9c65-9376663971e3"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-d5952b29ce39ccddc9575298d515399a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
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
            "value" : "8tn92mw9eo03a1fw5ngj3vqvh",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
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
            "value" : "16go8wahzik3g91zkfhqr3dln",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "858993459",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "52428800",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "9797055283",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "1648",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    }, {
      "name" : "impala",
      "type" : "IMPALA",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "llama_am_ha_zk_auth_secret_key",
          "value" : "EQOMsqNhTSrxc2Lyc68A5XYRHBRjyI",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
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
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "2x91jg2ny278aitilkrqn3gtl",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-CATALOGSERVER-BASE"
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
            "value" : "bvydef48ijkdgu6usjko8gpwx",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
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
            "value" : "2lqtqm1tpoerp6i5o9av62jeg",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
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
            "value" : "2q7es28pcu61x10lzqjg1igkr",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
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
            "value" : "bms07owj4ja4086w0jar6wdm8",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
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
            "value" : "9q4n736nbcvfv674mkjc8sv92",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-STATESTORE-BASE"
        }
      } ],
      "displayName" : "Impala",
      "roleConfigGroups" : [ {
        "name" : "impala-CATALOGSERVER-BASE",
        "displayName" : "Impala Catalog Server Default Group",
        "roleType" : "CATALOGSERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ {
            "name" : "catalogd_embedded_jvm_heapsize",
            "value" : "52428800",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-BASE",
        "displayName" : "Impala Daemon Default Group",
        "roleType" : "IMPALAD",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ {
            "name" : "impalad_memory_limit",
            "value" : "268435456",
            "sensitive" : false
          }, {
            "name" : "scratch_dirs",
            "value" : "/disco1/impala/impalad,/disco2/impala/impalad",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "impala-LLAMA-BASE",
        "displayName" : "Impala Llama ApplicationMaster Default Group",
        "roleType" : "LLAMA",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "impala-STATESTORE-BASE",
        "displayName" : "Impala StateStore Default Group",
        "roleType" : "STATESTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
            "value" : "5bd3h9z1baq3r0pfbivvepfre",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "oozie_data_dir",
            "value" : "/var/log/oozie/data",
            "sensitive" : false
          }, {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-28-62.us-east-2.compute.internal",
            "sensitive" : false
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password",
            "sensitive" : true
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql",
            "sensitive" : false
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie",
            "sensitive" : false
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "52428800",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "database_password",
          "value" : "hue_password",
          "sensitive" : true
        }, {
          "name" : "database_type",
          "value" : "mysql",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-0266459cbc739cc5eb9cffbed79e2850",
          "sensitive" : false
        }, {
          "name" : "impala_service",
          "value" : "impala",
          "sensitive" : false
        }, {
          "name" : "oozie_service",
          "value" : "oozie",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
            "value" : "av6o7c9tg2tx6rjnm9bua2ywq",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "CRTftwnZezkgqwm5ja4SIhRA22ue0b",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
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
            "value" : "6no0djqw2dnqa4ksv3b8ta6zm",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-KT_RENEWER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Load Balancer Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ {
            "name" : "hue_http_port",
            "value" : "18888",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password",
          "sensitive" : true
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,andrescruzat",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
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
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-GATEWAY-BASE"
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
            "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "59hjllfzuzx4edspijld0qbe5",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-SENTRY_SERVER-BASE"
        }
      } ],
      "displayName" : "Sentry",
      "roleConfigGroups" : [ {
        "name" : "sentry-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-BASE",
        "displayName" : "Sentry Server Default Group",
        "roleType" : "SENTRY_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456",
            "sensitive" : false
          } ]
        }
      } ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ],
    "uuid" : "cbd31c39-dbe5-4192-a173-a8b88b6bead5"
  } ],
  "hosts" : [ {
    "hostId" : "478d1736-9465-48b8-97d4-65c8fbc97ad3",
    "ipAddress" : "172.31.18.122",
    "hostname" : "ip-172-31-18-122.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
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
        "value" : "0.9",
        "sensitive" : false
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
        "value" : "0.9",
        "sensitive" : false
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
        "value" : "0.9",
        "sensitive" : false
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "8mw5y70d9a4yryvngc1ozklcd",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ACTIVITYMONITOR-BASE"
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "9kzsitcvdher54kkwunetgewd",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "3jff7pjc1dahgr5dc00iyysim",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "5eza4qk2zxcrxsus7jjorbvnw",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "reportsmanager_scratch_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "736puq7yvs5ryoih3nts46hfi",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
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
          "value" : "{\"warning\":2147483648,\"critical\":1073741824}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "etqwrobqnmvof64dh26j1jxw6",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "firehose_database_name",
          "value" : "amon",
          "sensitive" : false
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password",
          "sensitive" : true
        }, {
          "name" : "firehose_database_user",
          "value" : "amon",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-host-monitor",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-28-62.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password",
          "sensitive" : true
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-service-monitor",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-TELEMETRYPUBLISHER-BASE",
      "displayName" : "Telemetry Publisher Default Group",
      "roleType" : "TELEMETRYPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false",
      "sensitive" : false
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 18:30",
      "sensitive" : false
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAABBAAEADkFDUlVaQVRDREguQ09NAAxjbG91ZGVyYS1zY20AAAABWdUWagEAFwAQW3urzDxVlGq8iczEVsPckwAAAAE=",
      "sensitive" : true
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@ACRUZATCDH.COM",
      "sensitive" : false
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-28-62.us-east-2.compute.internal",
      "sensitive" : false
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac",
      "sensitive" : false
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD",
      "sensitive" : false
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/",
      "sensitive" : false
    }, {
      "name" : "SECURITY_REALM",
      "value" : "ACRUZATCDH.COM",
      "sensitive" : false
    } ]
  },
  "allHostsConfig" : {
    "items" : [ {
      "name" : "rm_enabled",
      "value" : "true",
      "sensitive" : false
    } ]
  },
  "peers" : [ {
    "name" : "Eduardo",
    "type" : "REPLICATION",
    "url" : "http://ec2-18-221-155-15.us-east-2.compute.amazonaws.com:7180",
    "username" : "__cloudera_internal_user__12f66dcf-f657-4cb9-ad80-76a2ea761cc3",
    "password" : "2f40d646-9c4a-4e9f-a8b7-fc3e800ce376b07cc524-7c63-4e03-8bd1-ba369c964b87",
    "clouderaManagerCreatedUser" : true
  } ],
  "hostTemplates" : {
    "items" : [ ]
  }
}
