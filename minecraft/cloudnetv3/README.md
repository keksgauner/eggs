<h1 color="red">WARNING: I do not recommend using this egg.

## Info (Read carefully before using his)
1. This is a test. It have issues.
2. It is not a finished build yet. And never will be.
3. I try my best to do what they want [here](https://github.com/parkervcp/eggs/issues/1245)
4. And I definitely don't recommend using it.
5. This is a test if it works. Unfortunately to use it has too many bugs
6. It is public so that eventually someone else can improve it
7. Only change something if you know what you are doing
8. I assume no liability for damages

### Info
I use a docker container i built myself that is laid out on cloudnet with pterodactyl\
See [hub.docker.com/keksgauner/cloudnet](https://hub.docker.com/r/keksgauner/cloudnet) and [keksgauner/docker-stuff](https://github.com/keksgauner/docker-stuff/blob/main/pterodactyl/images/cloudnet)

### How to install
1. Select your Version what you want
2. You have to say yes twice (If you ask to, because cloudnet wrote already yes)
3. You need to change the port in the local/tasks/Proxy.yml from 25565 to your own port manual
4. If you want more than 4 processes (3 Server) look to Wings Settings

### How to stop
1. Klick on stop
2. Write in the console stop (CloudNet need it twice)

## Wings Settings
Increase `container_pid_limit` more than 512 like 3512 (Your max can you see with `sysctl -a | grep kernel.pid_max `). Than restart your service `service wings restart` Look to [pterodactyl wings configuration](https://pterodactyl.io/wings/1.0/configuration.html)
- You must know 512 pids are nealy 4 processe

### Errors what I got:
- If you get by starting a server somethink like 
`java.lang.OutOfMemoryError: unable to create native thread: possibly out of memory or process/resource limits reached`
The reason is a docker contianer have a limit of processes or something. This does not mean there is out of memory\
Look to [containers-single-or-multiple-processes](https://www.tutorialworks.com/containers-single-or-multiple-processes) and [how-to-solve-javalangoutofmemoryerror-unable-to-create-new-native-thread](http://www.mastertheboss.com/jbossas/monitoring/how-to-solve-javalangoutofmemoryerror-unable-to-create-new-native-thread) to fix this look to Wings Settings you must increase `container_pid_limit`

- Not known NullPointerException
```
[18.09 20:35:07.878] ERROR: java.lang.NullPointerException: Cannot invoke "java.util.jar.Manifest.getMainAttributes()" because the return value of "java.util.jar.JarInputStream.getManifest()" is null
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.service.defaults.JVMCloudService.startProcess(JVMCloudService.java:187)
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.service.defaults.DefaultCloudService.invokeStart(DefaultCloudService.java:275)
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.service.defaults.DefaultCloudService.startNow(DefaultCloudService.java:259)
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.service.defaults.DefaultCloudService.start(DefaultCloudService.java:236)
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.provider.service.LocalNodeSpecificCloudServiceProvider.setCloudServiceLifeCycle(LocalNodeSpecificCloudServiceProvider.java:143)
[18.09 20:35:07.878] ERROR:     at de.dytanic.cloudnet.driver.provider.service.SpecificCloudServiceProvider.start(SpecificCloudServiceProvider.java:103)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.commands.CommandService.lambda$new$15(CommandService.java:187)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.commands.CommandService.forEachService(CommandService.java:294)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.commands.CommandService.lambda$new$16(CommandService.java:186)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.sub.SubCommandBuilder$1.execute(SubCommandBuilder.java:64)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.sub.SubCommandHandler.executeCommand(SubCommandHandler.java:135)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.sub.SubCommandHandler.execute(SubCommandHandler.java:112)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.DefaultCommandMap.dispatchCommand0(DefaultCommandMap.java:227)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.command.DefaultCommandMap.dispatchCommand(DefaultCommandMap.java:204)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.CloudNet.lambda$runConsole$19(CloudNet.java:1049)
[18.09 20:35:07.879] ERROR:     at de.dytanic.cloudnet.console.ConsoleReadThread.run(ConsoleReadThread.java:48)
```

- If successfully connected to the channel missing than check your Docker ip. It should look like this. (Used log level FATAL)
```
[12.09 15:26:47.698] INFO: CloudService [uniqueId=f09e75e5-7161-4323-a68f-538f22f550c6 task=Proxy name=Proxy-1] is being prepared...
[12.09 15:26:47.733] INFO: CloudService [uniqueId=f09e75e5-7161-4323-a68f-538f22f550c6 task=Proxy name=Proxy-1] is started...
[12.09 15:26:48.099] INFO: CloudService [uniqueId=f09e75e5-7161-4323-a68f-538f22f550c6 task=Proxy name=Proxy-1] was successfully connected to the channel [serverAddress=16e11b0d-0969-4b1c-889c-56c8b9b01252:55501 clientAddress=172.18.0.19:44280]
```

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
