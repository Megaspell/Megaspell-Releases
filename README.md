# Launcher / Лаунчер
[**Windows**](https://github.com/Megaspell/MegaspellLauncher/releases/latest/download/Megaspell-Launcher-Installer.exe)  
[**Linux**](https://github.com/Megaspell/MegaspellLauncher/releases/latest/download/Megaspell-Launcher.AppImage)  

# Direct downloads / Прямые загрузки
[**Windows**](https://github.com/Megaspell/Megaspell-Releases/releases/latest/download/PlayerWindows64.zip)  
[**Linux**](https://github.com/Megaspell/Megaspell-Releases/releases/latest/download/PlayerLinux64.zip)  
[**Linux (Server only)**](https://github.com/Megaspell/Megaspell-Releases/releases/latest/download/ServerLinux64.zip)  

# How to start a dedicated Megaspell server

### On Linux
1. Download `ServerLinux64.zip` release artifact.
2. Make sure Megaspell executable is marked as executable: `chmod +x Megaspell`
3. Run server using propert arguments.   
   **Example command:** `./Megaspell -nographics -batchmode --port 7777 --maxPlayers 20 --disableAuth --mode DeathMatch --level ManehattenSuburbs --serverName "A Megaspell Server"`

### On Windows
1. Either download `PlayerLinux64.zip` release artifact, or download it using launcher and open it's folder.
2. Make sure that firewall allows Megaspell to start on specified port (default 7777).
3. Run server using propert arguments.   
   **Example command:** `Megaspell.exe -nographics -batchmode --port 7777 --maxPlayers 20 --disableAuth --mode DeathMatch --level ManehattenSuburbs --serverName "A Megaspell Server"`

### Engine arguments
Adding `-batchmode` and `-nographics` is very recommended for server!

Unity docs: https://docs.unity3d.com/Manual/PlayerCommandLineArguments.html

### Server arguments

| Argument          | Description                                                                                                                | Default                          |
|-------------------|----------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| port              | Port the server is running on.                                                                                             | `7777`                           |
| bindIPv4          | IPv4 address to which server will be listening to.<br/>If not provided server will listen to all available IPv4 addresses. |                                  |
| bindIPv6          | IPv6 address to which server will be listening to.<br/>If not provided server will listen to all available IPv6 addresses. |                                  |
| maxPlayers        | Max amount of players allowed to connect. For singleplayer this is always `1`.                                             | `5`                              |
| singleplayer      | Run server in singleplayer mode.                                                                                           | `false`                          |
| disableAuth       | Disable all auth methods.<br/>Server will accept any Player ID without questions.<br/>Always `true` for singleplayer.      | `false`                          |
| stopWhenNoPlayers | Shutdown server when all connected players leave.<br/>Always `true` for singleplayer.                                      | `false`                          |
| everyoneIsAdmin   | Should players get access to admin tools by default?                                                                       | `true` for SP, otherwise `false` |
| defaultAdmins     | Player IDs that should be made admins by default.<br/>Example format: `76561197960287930,76561197960287936`.               |                                  |
| mode              | Game mode the server is running on.<br/>If `saveName` is set - will be set from save file.                                 | `DeathMatch`                     |
| level             | Level ID to load. If `saveName` is set - will be overriden by save file.                                                   | Default level for game mode      |
| saveName          | Save file name. If set, game state will be loaded from save file.                                                          |                                  |
| serverName        | Server name displayed to players in server list.                                                                           |                                  |
| password          | Optional server password.<br/>Length limited to 32.<br/>Can't be set for singleplayer.                                     |                                  |
| announce          | Should server be announced to server registry so other players will see it without entering the address?                   | `true`                           |
| announceHost      | How to announce the server.<br/>Set if you use a domain name so players can enter by `example.com` and not just IP.        | Server's public IP               |
| serverRegistry    | Override default server registry used for announcement (not recommended).                                                  |                                  |

### Alternative ways to configure arguments
You can also specify properties in a file called `application.properties` that is located in either working directory, or in game directory.

Contents example:
```properties
port=7777
maxPlayers=20
disableAuth=true
mode=DeathMatch
level=ManehattenSuburbs
serverName=A Megaspell Server
```
