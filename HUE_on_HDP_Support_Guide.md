#HUE on HDP Support Guide

##启动hue

login hdp-itg-001/hdp005

```
sudo su
nohup /usr/local/hue/build/env/bin/supervisor &
```
##停止hue

```
ps -ef | grep hue | grep -v grep | awk '{print $2}' | xargs kill -s 9
nohup /usr/local/hue/build/env/bin/supervisor &
```

##设置hue.ini
```
vim /usr/local/hue/desktop/conf/hue.ini
```

##查看设置是否生效
```
/usr/local/hue/build/env/bin/hue config_dump
```