MultiPlayerSessionPlugin
-----------------------

**MultiPlayerSessionPlugin**: A C++ multiplayer Steam plugin designed to simplify your development workflow.

- **Date**: 2023/09/30
- **Author**: Abdul Moez
- **Version**: 0.1.0 (Initial Release)
- **Study**: Undergraduate at GCU Lahore, Pakistan

Supported Engine Version
------------------------

- Unreal Engines: 5.0–5.0.3
- Works exclusively on the Steam platform

Documentation
-------------

**Step 1:** Create a new project. In the plugin section (under Edit > Plugins), search for `Online Subsystem Steam` and enable it. Then, close the Unreal Engine editor.

**Step 2:** Copy the `MultiplayerSession` folder from this repository to the `Plugins` folder in your project directory. If the plugin folder is not available, create it manually.

**Step 3:** Open the `DefaultEngine.ini` file inside the `Config` folder in the project's root directory. Paste the following at the end of the file. You can change `SteamDevAppId` to your personal dev ID. The current ID is a test ID provided by Steam.
  ```ini
  [/Script/Engine.GameEngine]
  +NetDriverDefinitions=(DefName="GameNetDriver",DriverClassName="OnlineSubsystemSteam.SteamNetDriver",DriverClassNameFallback="OnlineSubsystemUtils.IpNetDriver")

  [OnlineSubsystem]
  DefaultPlatformService=Steam

  [OnlineSubsystemSteam]
  bEnabled=true
  SteamDevAppId=480
  bInitServerOnClient=true

  [/Script/OnlineSubsystemSteam.SteamNetDriver]
  NetConnectionClassName="OnlineSubsystemSteam.SteamNetConnection"
  ```
  Then open `DefaultGame.ini` file and paste the following at the end of the file. Here you will specify max number of players. 
  ```ini
  [/Script/Engine.GameSession]
  MaxPlayers=100
  ```

**Step 4:** Delete the following folders from the root directory: `Binaries`, `Intermediate`, and `Saved`. Right-click on your project file (ending with the extension `.uproject`) and select `Generate Visual Studio project files`.

**Step 5:** Open the project by clicking on the `.uproject` file. It will prompt you to build the files; click OK.

**Step 6:** Open the `Open Level Blueprint`. On `EventBeginPlay`, set an action by right-clicking and selecting `Create Widget`. For the class parameter of the created widget, select `WBP_Menu`. On Return Value, search for the `Menu Setup` function and select it. Here, you can set three parameters:

* `Num Of Public Connections`: self-explanatory.
* `Type Of Match`: ensure it is unique for different matches.
* `Lobby Path`: the path of the level where the game begins. Pass `/Game/` up to the Content folder, and then the next path to the Lobby map (e.g., `/Game/Maps/Lobby`).

**Step 7:** Compile the game and run it on different systems. Ensure Steam is running in the background.

-----------

# Contributor

<a href = "https://github.com/Anonym0usWork1221/MultiPlayerSessionPlugin/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=Anonym0usWork1221/MultiPlayerSessionPlugin"/>
</a>

-----------
Support and Contact Information
----------
> If you require any assistance or have questions, please feel free to reach out to me through the following channels:  
* **Email**: `abdulmoez123456789@gmail.com`

> I have also established a dedicated Discord group for more interactive communication:  
* **Discord Server**: `https://discord.gg/RMNcqzmt9f`


-----------

Buy Me a coffee
--------------
__If you'd like to show your support and appreciation for my work, you can buy me a coffee using the 
following payment option:__

**Payoneer**: `abdulmoez123456789@gmail.com`

> Your support is greatly appreciated and helps me continue providing valuable assistance and resources. 
Thank you for your consideration.


