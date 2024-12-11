# zabbix-proxy

Para utilizar o zabbix-proxy em container docker utilize o seguinte comando adaptado à sua necessidade:

Geralmente alteramos:
- `ZBX_SERVER` com o IP do servidor zabbix-server
- `ZBX__HOSTNAME` com o hostname do zabbix-proxy 

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

Após isso configurar lembre-se de:
- certificar que no servidor já exista a configuração do zabbix-proxy
- entrar em cada hosts que será monitorado e colocar o IP do host que executa o container do zabbix-proxy
