# About
OpenFrags-Duels is a fork of OpenFrags intended for duels and a SourceMod plugin for [Open Fortress](https://openfortress.fun) that allows cross-server stat tracking and viewing it using fancy web pages and chat commands  
More info at http://openfrags.ohaa.xyz

#### ConVars:

```
sm_openfrags_announce_elos [0 or 1] (Default: 1) - Announce player ELOs each time a round starts
```

#### Server commands:
```
sm_openfrags - About OpenFrags-Duels
sm_openfrags_duels - An alias for sm_openfrags
sm_openfrags_stats [Name/SteamID2] - View your stats (or someone else's)
sm_openfrags_top - View the top players
sm_openfrags_leaderboard - An alias for sm_openfrags_top
sm_openfrags_eligibility - Test the server for stat tracking eligibility
sm_openfrags_test_query (admin only) - Increase the caller's damage_dealt stat by 1
```

#### Chat commands:
```
!openfrags / !openfrags_duels
!top / !leaderboard
!stats
!elo / !rating
!elos / !ratings
```

# Installation:
You can apply for a MySQL user for your server to access the OpenFrags database at http://openfrags.ohaa.xyz/apply
Without access to the DB you won't be able to use the plugin on your server

0. Requirements:
- [SM-OpenFortress-Tools](https://github.com/openfortress/SM-Open-Fortress-Tools)
- [Updater](https://forums.alliedmods.net/showthread.php?t=169095)  
- [cURL Extension](https://code.google.com/archive/p/sourcemod-curl-extension/downloads) (need it for Updater)  
- [morecolors.inc](https://forums.alliedmods.net/showthread.php?t=185016)  
1. Download the files from the repo and unpack them in open_fortress/addons/sourcemod/
2. Configure the translation file (open_fortress/addons/sourcemod/translations/openfrags.phrases.txt) to fit your server's theme
3. Add an "openfrags" database entry to open_fortress/addons/sourcemod/configs/databases.cfg
Below is an example of how an entry can look like:
```
	"openfrags"
	{
		"driver"			"mysql"
		"host"				"123.45.67.89"
		"database"			"openfrags"
		"user"				"ratserver"
		"pass"				"my_password"
		"port"				"3306"
		"timeout"			"20"
	}
```
4. Restart the server and verify that the plugin works by typing `sm_openfrags` and `sm_openfrags_top` in your __player__ console (this will most likely not work if you use the server console!)

# Compiling
This should be the same as compling any other SourceMod plugin, but you need to have [morecolors.inc](https://forums.alliedmods.net/showthread.php?t=185016) in open_fortress/addons/sourcemod/scripting/include/
