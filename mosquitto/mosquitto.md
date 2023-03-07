## mount mosquitto data in volume und mosquitto logs on host folder
``` zsh
docker run -d  --name mosquitto -h mosquitto -p 1883:1883 -v /mnt/data/mosquitto/config/mosquitto.conf:/mosquitto/config/mosquitto.conf -v mosquitto_data:/mosquitto/data -v /mnt/data/mosquitto/log:/mosquitto/log eclipse-mosquitto
```
## mount mosquitto data and log in two seprate volumes
``` zsh
docker run -d  --name mosquitto -h mosquitto -p 1883:1883 -v /mnt/data/mosquitto/config/mosquitto.conf:/mosquitto/config/mosquitto.conf -v mosquitto_data:/mosquitto/data -v mosquitto_log:/mosquitto/log eclipse-mosquitto
```
## run inside container to create user for mqtt auth
```zsh
mosquitto_passwd -c /mosquitto/config/password.txt mqtt
```
## change mosquitto.conf to use user auth
``` config
allow_anonymous false
password_file /mosquitto/config/password.txt
```

## check logs from running container
``` zsh
docker logs mqtt -f
```