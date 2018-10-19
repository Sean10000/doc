#新增或删除hdp平台某个host组件的client命令


###Use the following command to list all the services installed on your node in cluster
```
curl -u admin:admin -H "X-Requested-By: ambari" -X GET http://AMBARIHOSTNAME:8080/api/v1/clusters/CLUSTERNAME/hosts/HOST
```
example
```
curl -u admin:admin -H "X-Requested-By: ambari" -X GET http://hdp-itg-ambari:10101/api/v1/clusters/HDP_ITG/hosts/hdp-itg-003
```

###Then delete the client you want using following command
```
curl -u admin:admin -H "X-Requested-By: ambari" -X DELETE http://hdp-itg-ambari:10101/api/v1/clusters/HDP_ITG/hosts/hdp-itg-001/host_components/OOZIE_CLIENT
```


##实操

```
curl -u admin:passwd -H "X-Requested-By: ambari" -X DELETE http://hdp-itg-ambari:8080/api/v1/clusters/HDP_ITG/hosts/hdp-itg-003/host_components/OOZIE_CLIENT

```