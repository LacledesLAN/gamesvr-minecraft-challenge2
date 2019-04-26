# Laclede's LAN Minecraft Challenge 2

Minecraft world divided into multiple identical zones that are blocked off from each other. A build challenge is set and teams of 1 to 3 players gets assigned a zone. At the end each team's creation is judged.

Each zone has goodies, supplies, and [Easter-eggs](https://en.wikipedia.org/wiki/Easter_egg_(media)) spread throughout to encourage exploration. All players new to the server spawn in a 'spawn jail' which they cannot escape - an admin must teleport them to the appropriate zone.

![alt text](https://raw.githubusercontent.com/LacledesLAN/gamesvr-minecraft-challenge2/master/.docs/OverheadMap.png "Overhead Map")

## Teleportation Coordinates

### Spawn Jail

-706 95 -1162

### Islands

| Zone | Spawn Room    |
| ---- | ------------- |
| 1    | -104 66 -1562 |
| 2    | 279 66 -1562  |
| 3    | 663 66 -1562  |
| 4    | -104 66 -1210 |
| 5    | 279 66 -1210  |
| 6    | 663 66 -1210  |
| 7    | -104 66 -858  |
| 8    | 279 66 -858   |
| 9    | 663 66 -858   |

## Admin Commands

| Description             | Command                                          | Notes |
| ----------------------- | ------------------------------------------------ | ----- |
| Enable whitelist        | `/whitelist on`                                  | Prevents players besides OP and players listed on the whitelist form connecting. Use while judging results. |
| Teleport to player      | `tp [target player] <destination player>`        |       |
| Teleport to coordinates | `tp [target player] <x> <y> <z> [<yaw> <pitch>]` |       |
| Set world spawn         | `/setworldspawn`; `/setworldspawn <x> <y> <z>`   |       |
| Set player spawn        | `/spawnpoint <player> <x> <y> <z>`               |       |
| Set game rules          | `/gamerule <rule name> [value]`                  |       |
| Night vision            | `/effect @p minecraft:night_vision 99999 255`    |       |
| Reset vision            | `/effect @p clear`                               |       |
| Give barrier block      | `/give <player> minecraft:barrier`               |       |

## Docker

### Build

```shell
docker build -t lacledeslan/gamesvr-minecraft-challenge2 -f linux.Dockerfile .
```

### Run Interactive Server

```shell
docker run -d --rm -p 25565:25565 lacledeslan/gamesvr-minecraft-challenge2 java -Xms512M -Xmx1024M -jar /app/minecraft-server.jar nogui
```
