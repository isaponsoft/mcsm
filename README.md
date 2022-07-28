# mcsm

Minecraft server management script for FreeBSD.

## 1. INSTALL

```sh
$ pkg install git screen openjdk18
$ git clone git@github.com:isaponsoft/mcsm.git mcsm
$ cd mcsm/build/freebsd
$ make install
```

## 2. Update server program

```sh
$ mcsm update 1.19
...
...
Copying spigot-1.19-R0.1-SNAPSHOT-bootstrap.jar to /var/games/minecraft/prog/./spigot-1.19.jar
  - Saved as ./spigot-1.19.jar
```


## Create & Start

```sh
$ mcsm create MYWORLD
Create server dir '/var/games/minecraft/servers/MYWORLD'.
/var/games/minecraft/servers/MYWORLD/mcsm.conf
$ mcsm start MYWORLD
Wakeup MYWORLD.
```

## Status

```sh
$ mcsm status
   PID  Servername
 70635  MYWORLD
```


## Server console

```sh
$ mcsm console MYWORLD
```

exit console : Ctrl+a => d


## Stop

```sh
$ mcsm stop MYWORLD
Stopping 'MYWORLD' please wait for about 30 seconds.
```


exit console : Ctrl+a => d


## Auto start & Auto stop

```sh
$ service mcsm enable
```
