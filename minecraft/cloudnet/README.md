# [CloudNet](https://github.com/CloudNetService/CloudNet)

CloudNet is an alternative application that can dynamically and easy deploy Minecraft oriented software.

> [!IMPORTANT]
> It is very important to use version up to 4.0.0-RC11 because it includes a [fixed version of jline](https://github.com/CloudNetService/CloudNet/pull/1441)
>
> I only created this egg and cannot be held responsible if anything goes wrong. I am not affiliated with the CloudNet team in any way. If you need help related to CloudNet, please join the CloudNet Discord.
>
> If you have problems setting up, I would recommend the [README](https://github.com/Lostes-Burger/Docker/blob/main/pterodactyl/eggs/cloudnet/README.md) by [Lostes-Burger](https://github.com/Lostes-Burger).

### About the docker image

I use a Docker container I built myself, which is based on CloudNet with Pterodactyl.\
See [hub.docker.com/keksgauner/cloudnet](https://hub.docker.com/r/keksgauner/cloudnet) and [keksgauner/docker-stuff](https://github.com/keksgauner/docker-stuff/blob/main/pterodactyl/images/cloudnet)

## Wings Settings

Increase `container_pid_limit` more than 512 like 3512. Than restart your service `service wings restart`\
Look to [pterodactyl wings configuration](https://pterodactyl.io/wings/1.0/configuration.html)

- You must know 512 pids are nealy 4 processe

## Minimum requirements

Look to [cloudnetservice.eu](https://cloudnetservice.eu/docs/3.4/setup/requirements)

## Server Ports

The minecraft server requires a single port for access (default 25565) but plugins may require extra ports to enabled for the server.

| Port                 | default |
| -------------------- | ------- |
| Game                 | 25565   |
| Cloudnet             | 1410    |
| CloudNet's WebServer | 2812    |
