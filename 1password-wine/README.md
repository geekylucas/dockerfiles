# 1Password in Docker

## Prerequisites

You'll almost certainly need to be running a local xhost. Add this to your `~/.xsessionrc`.

```
xhost local:root
```

## To run:

```
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY -v $HOME/Dropbox/1Password.agilekeychain:/root/Dropbox/1Password.agilekeychain --net="host" --name 1password-wine geekylucas/1password-wine bash
```

- Exposes X11 to the container
- Sets the `DISPLAY` environment variable
- Exposes local keychain to container (assumes dropbox, change as needed)
- `--net="host" is required if you want the chrome extension to be able to connect to the 1Password agent in the container. This is because it only listens on `127.0.0.1`.

### Install

```
wine /usr/src/1Password-4.6.0.598.exe
```

### Launch 1Password Application

```
wine /root/.wine/drive_c/Program\ Files/1Password\ 4/1Password.exe
```

### Launch 1Password Agent

```
wine /root/.wine/drive_c/Program\ Files/1Password\ 4/Agile1pAgent.exe
```

### Chrome extension

You'll need to configure 1Password to allow this. Go to:

- Help > Advanced > Verify web browser code signature (should be unchecked)

## Start after first run:

```
docker start -i 1password-wine
```
