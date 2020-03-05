#### An Ambari Service for Hue
Ambari service for easily installing and managing Hue on HDP cluster.

#### Authors: 
  - [Kyle Joe](https://github.com/EsharEditor)
  - [Steven Matison](https://github.com/steven-dfheinz)

A big thank you to Kyle for creating the original HDP 2.x github repo. 
Have a look here:  https://github.com/EsharEditor/ambari-hue-service

Also see https://gethue.com for more information, versions, and official documentation.

#### Version
- Hue 3.11.0
- HDP 3.x

#### Setup
- Deliver Service Fileset to Ambari   
``` 
sudo git clone https://github.com/steven-dfheinz/HDP3-Hue-Service.git /var/lib/ambari-server/resources/stacks/HDP/[version]/services/HUE
```

  **** be sure to get your correct [version] for command above

- Restart Ambari
```
service ambari-server restart
```
- In Ambari click on 'Add Service' and install HUE
- Install requires HDFS,Yarn,Hive,Hbase,Spark,Zookeeper,Sqoop,Oozie.  

#### Known Issues
- If Hbase or Spark are missing, the install will fail on missing config objects
- There could still be conflicts with config params not yet migrated to HDP 3.x format
--   Conflict with Spark2 config object
--   Conflict with Hbase Thrift Server v1
- Very long compile time as "make apps" takes nearly 30 minutes to complete dependencies
- hue user, hue group error when Ambari is Managing User/Group Creation. The work around is below:
```
python /var/lib/ambari-server/resources/scripts/configs.py -u admin -p admin -n HDP3 -l hdp3.cloudera.com -t 8080 -a set -c cluster-env -k  ignore_groupsusers_create -v true
```

  **** make sure to get correct Cluster Name (HDP3) and Ambari Host (hdp3.cloudera.com) for command above

#### Coming Soon
- Create a repository for hue fileset built via "make apps"
- Updates for Hue 4.x
- Bundling this service into an easier to use Management Pack
- Add better handling for missing components

