#### TUNA/BFSU/NJU 等

```{ztmpl lang="ini" input="release" path="/etc/yum.repos.d/influxdata.repo"}
[influxdata]
name = InfluxData Repository - RHEL $releasever
baseurl={{endpoint}}/yum/{{release}}
enabled=1
gpgcheck=1
gpgkey=https://repos.influxdata.com/influxdata-archive_compat.key
```
