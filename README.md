# DDNet Community NetMessages
Collection of unofficial ddnet-compatible netmessages, server-side and client-side

## NetMessages (network.py)

### Modify Tile (DDNet++/Chillerbot-ux)

Modify a specific tile in a layer

`NetMessageEx("Sv_ModifyTile", "modify-tile@msg.zillyhuhn.com", [
		NetIntAny("m_X"),
		NetIntAny("m_Y"),
		NetIntAny("m_Group"),
		NetIntAny("m_Layer"),
		NetIntAny("m_Index"),
		NetIntAny("m_Flags"),
	]),`

### Kaizo Network Crown

Intended for showing a blue crown above the character, needs to be sent each certain amount of time

`NetMessageEx("Sv_KaizoNetworkCrown", "kaizocrown@m0rekz.github.io", [
		NetIntAny("m_ClientId"),
	]),`

## NetMessages (protocol_ex_msgs.h)

### Kaizo Network version

Kaizo Network client version, can be sent to "Kaizo" or "K-Gores" servers to get extra data

`UUID(NETMSG_KZ_KAIZO_NETWORK_VERSION, "kaizoversion@m0rekz.github.io")`

### Infclass version

Infclass version, sent to Infclass servers

`UUID(NETMSG_CLIENTVER_INFCLASS, "clientver@infclass")`

## NetObjects

### Infclass Class Info

Info for Infclass Classes

`NetObjectEx("InfClassClassInfo", "classinfo@infclass", [
		NetIntAny("m_Flags"),
		NetIntRange("m_Class", -1, 255),
		NetIntAny("m_Data1"),
	]),`

### Infclass Game Info

Game Info for Infclass server

`NetObjectEx("InfClassGameInfo", "gameinfo@infclass", [
		NetIntAny("m_Version", 0),
		NetIntAny("m_Flags", 0),
		NetIntRange("m_TimeLimitInSeconds", 0, 'max_int', 0),
		NetIntAny("m_HeroGiftTick", -1),
	], validate_size=False),`

### Infclass Kill Message

Infclass extended kill message

`NetMessageEx("Inf_KillMsg", "kill-ex1@infclass", [
		NetIntRange("m_Victim", 0, 'MAX_CLIENTS-1'),
		NetIntRange("m_Killer", -1, 'MAX_CLIENTS-1'),
		NetIntRange("m_Assistant", -1, 'MAX_CLIENTS-1'),
		NetIntAny("m_InfDamageType"),
		NetIntRange("m_Weapon", -3, 'NUM_WEAPONS-1'),
	]),`

### Infclass Server Params

Values for some server configs

`NetMessageEx("InfClass_ServerParams", "server-params1@infclass", [
		NetIntAny("m_Version", 0),
		NetIntRange("m_WhiteHoleMinKills", 0, 255, 0),
		NetIntRange("m_SoldierBombs", 0, 255, 0),
	]),`

### Infclass Object

Infclass Object

`NetObjectEx("InfClassObject", "object@infclass", [
		NetIntAny("m_Flags", 0),
		NetIntRange("m_Owner", -1, 'MAX_CLIENTS-1', -1),
		NetIntAny("m_X", 0),
		NetIntAny("m_Y", 0),
		NetIntAny("m_X2", 0),
		NetIntAny("m_Y2", 0),
		NetIntAny("m_Type", 0),
		NetIntAny("m_StartTick", 0),
		NetIntAny("m_EndTick", 0),
		NetIntAny("m_ProximityRadius", 0),
		NetIntAny("m_Data1", 0),
	], validate_size=False),`

### Infclass Player

Infclass player extended data

`NetObjectEx("InfClassPlayer", "player@infclass", [
		NetIntAny("m_Flags"),
		NetIntRange("m_Class", -1, 255),
		NetIntAny("m_Kills"),
		NetIntAny("m_Deaths"),
		NetIntAny("m_Assists"),
		NetIntAny("m_Score"),
	]),`

### Kaizo Network Character

Extended character data for Kaizo Network servers

`NetObjectEx("KaizoNetworkCharacter", "kaizocharacter@m0rekz.github.io", [
		NetIntAny("m_Flags", default=0),
        NetIntAny("m_RealCurrentWeapon", default=-1),
        NetIntAny("m_Tick", default=0),
	], validate_size=False),`

### Kaizo Network Mine

Kaizo Network Mine Entity

`NetObjectEx("KaizoNetworkMine", "kaizomine@m0rekz.github.io", [
		NetIntAny("m_X"),
		NetIntAny("m_Y"),
		NetIntRange("m_Type", 0, 'max_int'),
	]),`

### Kaizo Network Pickup

Kaizo Network Pickup Entity

`NetObjectEx("KaizoNetworkPickup", "kaizopickup@m0rekz.github.io", [
		NetIntAny("m_X", default=0),
        NetIntAny("m_Y", default=0),
        NetIntAny("m_Type", default=0),
        NetIntAny("m_Switch", default=0),
	], validate_size=False),`

### Kaizo Network Turret

Kaizo Network Turret Entity

`NetObjectEx("KaizoNetworkTurret", "kaizoturret@m0rekz.github.io", [
		NetIntAny("m_X"),
		NetIntAny("m_Y"),
		NetIntRange("m_Type", 0, 'max_int'),
	]),`

### Player Ping (Kaizo Network)

Player ping (sent by Kaizo Network servers)

`NetObjectEx("KaizoNetworkPlayerPing", "kaizoplayerping@m0rekz.github.io", [
		NetIntAny("m_Ping", default=0),
	], validate_size=False),`

