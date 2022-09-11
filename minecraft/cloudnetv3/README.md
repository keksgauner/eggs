# WARNING: I do not recommend using this egg.
### This is a snapshot or developent build. It may have issues.
### It will be updating. if it is still needed. It is not a finished build yet.
I try my best to do what they want [here](https://github.com/parkervcp/eggs/issues/1245)

# CloudNet3 server
CloudNet is an alternative application that can dynamically and easy deploy Minecraft oriented software.

## Minimum requirements
Look to [cloudnetservice.eu](https://cloudnetservice.eu/docs/3.4/setup/requirements)

## Egg Nodes
There are some Errors!

### How to stop
1. Klick on stop
2. Write in the console stop


### How to use
1. Select your Version what you want
2. You have to say yes twice (If you ask to, because cloudnet wrote already yes)
3. You need to change the port in the local/tasks/Proxy.yml from 25565 to your own port manual
4. You need to change the variable Internal Docker IP. (You can see it when you delete config.yml thats why I don't recommentd this)

### Errors what I got:
- If you get by starting a server somethink like 
`java.lang.OutOfMemoryError: unable to create native thread: possibly out of memory or process/resource limits reached`
The reason is a docker contianer have a limit of processes. This does not mean there is out of memory
Look to [containers-single-or-multiple-processes](https://www.tutorialworks.com/containers-single-or-multiple-processes)

### Docker IP
- You can see it when you delete config.yml thats why I don't recommentd this
- You can see it with Portainer
![image](https://cloud.rakutt.eu/s/SgLrNQCmpLNsddi/preview)
- You can see it with commands in the console
```
$ docker inspect -f \
'{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' \
16e11b0d-0969-4b1c-889c-56c8b9b01252
```
Look to [how-to-get-a-docker-container-ip-address](https://www.freecodecamp.org/news/how-to-get-a-docker-container-ip-address-explained-with-examples)

## Server Ports
The minecraft server requires a single port for access (default 25565) but plugins may require extra ports to enabled for the server.


| Port  | default |
|-------|---------|
| Game | 25565 |
| Cloudnet | 1410 |
| CloudNet's WebServer | 2812 |
