#### An Ambari Service for Hue
Ambari service for easily installing and managing Hue on HDP cluster.

Authors: 
  - [Kyle Joe](https://github.com/EsharEditor)
  - [Steven Matison] (https://github.com/steven-dfheinz)

A big thank you to Kyle and the original github repo. Have a lookg here:  https://github.com/EsharEditor/ambari-hue-service

Also see https://gethue.com for more information, versions, and Hue documentation.

#### Version
- Hue v3.11.0+
- Ambari v2.4.0+

#### Setup
   ***) be sure to get your correct [version] and [githuburl] for below command

``` 
sudo git clone [githuburl] /var/lib/ambari-server/resources/stacks/HDP/[version]/services/HUE
```

- Restart Ambari
```
service ambari-server restart
```
- Then you can click on 'Add Service' and choose HUE
