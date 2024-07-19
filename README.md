# SSL Network Extender
Подробнее см. [ответ](https://unix.stackexchange.com/questions/450229/getting-checkpoint-vpn-ssl-network-extender-working-in-the-command-line)

### Установка
```bash
sudo -i
dpkg --add-architecture i386
apt install libc6:i386 libx11-6:i386 libpam0g:i386 libstdc++5:i386
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

