# zabbix-proxy

Para utilizar o zabbix-proxy em container docker utilize o seguinte comando adaptado à sua necessidade:

Geralmente alteramos ZBX_SERVER e ZBX__HOSTNAME.

```
docker run -d \
  --name zabbix-proxy \
  --restart unless-stopped \
  -p 10051:10051 \
  -e ZBX_SERVER_HOST="100.100.100.100" \
  -e ZBX_HOSTNAME="supcliente-o3" \
  -e ZBX_PASSIVESERVERS="0.0.0.0/0" \
  zabbix/zabbix-proxy-sqlite3:alpine-7.0.6
```
