# SSL Network Extender
Подробнее см. ["Настройка SNX"](https://unix.stackexchange.com/questions/450229/getting-checkpoint-vpn-ssl-network-extender-working-in-the-command-line) и ["Маппинг библиотек в Void Linux"](https://github.com/void-linux/void-packages/blob/master/common/shlibs)

### Установка
```bash
sudo -i
xbps-install -Syu void-repo-multilib void-repo-multilib-nonfree void-repo-nonfree
xbps-install -Syu glibc-32bit libX11-32bit pam-libs-32bit
chmod 755 *
cp libstdc++.so.5.0.7 /usr/lib32 # перенести бинарный пакет в lib32 (отсутствует в void)
ln -s /usr/lib32/libstdc++.so.5.0.7 /usr/lib32/libstdc++.so.5
./snx_install_linux30.sh
```

### Использование
В домашней директории создается конфигурационный файл ```.snxrc```, который дополняется следующим содержанием:
```
server IP_address_of_your_VPN
username YOUR_USER
reauth yes
```

Подключиться к сессии:
```bash
snx
```

Отключиться:
```bash
snx -d
```

