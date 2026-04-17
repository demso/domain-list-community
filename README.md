# Domain lists
### Lists:

```
geosite-rlv:davoyan-category-ru (https://github.com/Davoyan/mihomo-rule-sets/blob/main/rules/category-ru.lst)
geosite-rlv:wl (https://github.com/hxehex/russia-mobile-internet-whitelist/blob/main/whitelist.txt)
```

### Usage:
```
mkdir -p /opt/remnawave/xray/share/
wget -O /opt/remnawave/xray/share/geosite-rlv.dat https://github.com/demso/domain-list-community/releases/latest/download/geosite-rlv.dat
chmod -R 755 /opt/remnawave/xray/

# Add into /opt/remnanode/docker-compose.yml
    volumes:
      - /opt/remnawave/xray/share/geosite-rlv.dat:/usr/local/bin/geosite-rlv.dat
  
docker compose down && docker compose up -d && docker compose logs -f
  
      {
        "domain": [
          "ext:geosite-rlv.dat:davoyan-category-ru",
          "ext:geosite-rlv.dat:wl"
        ],
        "outboundTag": "VLESS_TO_RU"
      },      
```
