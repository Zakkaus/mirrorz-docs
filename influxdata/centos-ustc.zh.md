#### USTC

```{ztmpl lang="ini" path="/etc/yum.repos.d/influxdata.repo"}
[influxdata]
name = InfluxData Repository - Stable
baseurl = {{endpoint}}/stable/$basearch/main
enabled = 1
gpgcheck = 1
gpgkey = https://repos.influxdata.com/influxdata-archive_compat.key
```
