# Quick sample

```
$ ansible-playbook -i inventories/vagrant/ spark.yml -b
```

```
$ ansible-playbook -i inventories/vagrant/ spark.yml -b --private-key=vagrant.key --tags spark::masters-start
```

* masters-start
* masters-stop
* workers-start
* workers-stop


export LD_LIBRARY_PATH=/usr/local/hadoop/lib

spark.read.text("hdfs://cluster1/test/a.txt").show()


Not needed:
```
export HDFS_CONF_DIR=$HADOOP_CONF_DIR

sc._jsc.hadoopConfiguration().set("dfs.nameservices", "cluster1")
sc._jsc.hadoopConfiguration().set("dfs.namenode.rpc-address.cluster1.mach1", "mach1:8020")
sc._jsc.hadoopConfiguration().set("dfs.namenode.rpc-address.cluster1.mach2", "mach2:8020")
```

