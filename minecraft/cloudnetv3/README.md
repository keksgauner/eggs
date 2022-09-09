# WARNING: I do not recommend using this egg.
### This is a snapshot or developent build. It may have issues.
### It will be updating. if it is still needed. It is not a finished build yet.
I try my best to do what they want [here](https://github.com/parkervcp/eggs/issues/1245)

# CloudNet3 server
CloudNet is an alternative application that can dynamically and easy deploy Minecraft oriented software.

## Minimum requirements
Look to [cloudnetservice.eu](https://cloudnetservice.eu/docs/3.4/setup/requirements)

## How to use
1. Select your Version what you want
2. You have to say yes twice (If you ask to, because cloudnet wrote already yes)
3. You need to change the port in the local/tasks/Proxy.yml from 25565 to your own port manual
4. You need to change the variable Internal Docker IP. (You can see it when you delete config.yml thats why I don't recommentd this)

## Docker IP
- You can see it when you delete config.yml thats why I don't recommentd this
- You can see it with Portainer
![image](https://cloud.rakutt.eu/s/SgLrNQCmpLNsddi/preview)
- You can see it with commands
```
$ docker ps --format \
"table {{.ID}}\t{{.Status}}\t{{.Names}}"
```
```
$ docker inspect -f \
'{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' \
75000c343eb7
```


## Server Ports
The minecraft server requires a single port for access (default 25565) but plugins may require extra ports to enabled for the server.


| Port  | default |
|-------|---------|
| Game | 25565 |
| Cloudnet | 1410 |
| CloudNet's WebServer | 2812 |
