# UI in docker
Allow UI application to run in docker by piping the graphical output to the host Xserver. This will not have latency like when using VNC because docker won't be running its own X rendering.

In order to do this, it requires complete mirror of host settings (uid, gid, username, network, access to Xsocket) in the docker. So docker would be able to write to Xsocket. We could run a long `docker run` command, or put all the parameters into `docker-compose.yml` and simplify execution.


### Potential use case
- Simulation!


# Start docker
Remember to update uid, gid, username in docker compose when running on your device.
```
id -u  # uid
id -g  # gid
whoami  # username
```

```
docker compose build  # build dockerfile
docker compose up  # equivalent to "docker run"
```


# Requirement
It currently only work in Linux