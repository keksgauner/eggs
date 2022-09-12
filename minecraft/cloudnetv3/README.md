<h1 color="red">WARNING: I do not recommend using this egg.
<br>
It is only for those people who are trying hard to create a pterodactyl cloudnet server!</h1>

Look to [containers-single-or-multiple-processes](https://www.tutorialworks.com/containers-single-or-multiple-processes)
```
Why should a container have only one process?

It’s sometimes recommended in books and documentation to stick to the principle of one container, one process. Many container images on Docker Hub usually just run one process.
```
## Info (Read carefully before using his)
1. This is a snapshot or developent build. It have issues.
2. It is not a finished build yet. And never will be.
3. I try my best to do what they want [here](https://github.com/parkervcp/eggs/issues/1245)
4. And I definitely don't recommend using it.
5. This is a test if it works. Unfortunately to use it has too many bugs
6. It is public so that eventually someone else can improve it

## Wings Settings
Increase `container_pid_limit` more than 512 like 3512 (Your max can you see with `sysctl -a | grep kernel.pid_max `). Than service wings restart
Look to [pterodactyl wings configuration](https://pterodactyl.io/wings/1.0/configuration.html)

### How to stop
1. Klick on stop
2. Write in the console stop

### How to install
1. Select your Version what you want
2. You have to say yes twice (If you ask to, because cloudnet wrote already yes)
3. You need to change the port in the local/tasks/Proxy.yml from 25565 to your own port manual
4. You need to change the variable Internal Docker IP. (You can see it when you delete config.yml thats why I don't recommentd this)

### Errors what I got:
- If you get by starting a server somethink like 
`java.lang.OutOfMemoryError: unable to create native thread: possibly out of memory or process/resource limits reached`
![image](https://cloud.rakutt.eu/s/fBJSKkeYncfGtci/preview)
The reason is a docker contianer have a limit of processes or something. This does not mean there is out of memory
Look to [containers-single-or-multiple-processes](https://www.tutorialworks.com/containers-single-or-multiple-processes) and [how-to-solve-javalangoutofmemoryerror-unable-to-create-new-native-thread](http://www.mastertheboss.com/jbossas/monitoring/how-to-solve-javalangoutofmemoryerror-unable-to-create-new-native-thread) to fix this look to Wings Settings


### Docker IP
- You can see it when you delete config.yml
- You can see it with Portainer
![image](https://cloud.rakutt.eu/s/SgLrNQCmpLNsddi/preview)
- You can see it with commands in the console
```
$ docker inspect -f \
'{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' \
16e11b0d-0969-4b1c-889c-56c8b9b01252
```
Look to [how-to-get-a-docker-container-ip-address](https://www.freecodecamp.org/news/how-to-get-a-docker-container-ip-address-explained-with-examples)

# CloudNet3 server
CloudNet is an alternative application that can dynamically and easy deploy Minecraft oriented software.

## Minimum requirements
Look to [cloudnetservice.eu](https://cloudnetservice.eu/docs/3.4/setup/requirements)

## Server Ports
The minecraft server requires a single port for access (default 25565) but plugins may require extra ports to enabled for the server.


| Port  | default |
|-------|---------|
| Game | 25565 |
| Cloudnet | 1410 |
| CloudNet's WebServer | 2812 |
