#### An Ambari Service for Hue
Ambari service for easily installing and managing Hue on HDP cluster.

Authors: 
  - [Kyle Joe](https://github.com/EsharEditor)
  - [Steven Matison](https://github.com/steven-dfheinz)

A big thank you to Kyle for creating the original github repo. 
Have a look here:  https://github.com/EsharEditor/ambari-hue-service

Also see https://gethue.com for more information, versions, and Hue documentation.

#### Version
- Hue v3.11.0+
- Ambari v2.4.0+

#### Setup
- Deliver Service Fileset to Ambari   
   

``` 
sudo git clone https://github.com/steven-dfheinz/HDP3-Hue-Service.git /var/lib/ambari-server/resources/stacks/HDP/[version]/services/HUE
```

**** be sure to get your correct [version] for below command

- Restart Ambari
```
service ambari-server restart
```
- Next lick on 'Add Service' and choose HUE in the Installation Wizard

#### Coming Soon
- Updates for Hue 4.x
- Bundling this service into an easier to use Management Pack

#### Known Issues
- hue user, hue group error when Ambari is Managing User/Group Creation. The work around is below:
```
python /var/lib/ambari-server/resources/scripts/configs.py -u admin -p admin -n HDP3 -l hdp3.cloudera.com -t 8080 -a set -c cluster-env -k  ignore_groupsusers_create -v true
```

**** make sure to get correct Cluster Name (HDP3) and Url (hdp3.cloudera.com)