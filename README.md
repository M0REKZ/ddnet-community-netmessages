# DDNet Community NetMessages
Collection of unofficial ddnet-compatible netmessages, server-side and client-side

## NetMessages (network.py)

### Kaizo Network Crown

Intended for showing a blue crown above the character, needs to be sent each certain amount of time

`NetMessageEx("Sv_KaizoNetworkCrown", "kaizocrown@m0rekz.github.io", [
		NetIntAny("m_ClientId"),
	]),`

## NetMessages (protocol_ex_msgs.h)

### Kaizo Network version

Kaizo Network client version, can be sent to "Kaizo" or "K-Gores" servers to get extra data

`UUID(NETMSG_KZ_KAIZO_NETWORK_VERSION, "kaizoversion@m0rekz.github.io")`

## NetObjects

### Kaizo Network Turret

Kaizo Network Turret Entity

`NetObjectEx("KaizoNetworkTurret", "kaizoturret@m0rekz.github.io", [
		NetIntAny("m_X"),
		NetIntAny("m_Y"),
		NetIntRange("m_Type", 0, 'max_int'),
	]),`

### Kaizo Network Mine

Kaizo Network Mine Entity

`NetObjectEx("KaizoNetworkMine", "kaizomine@m0rekz.github.io", [
		NetIntAny("m_X"),
		NetIntAny("m_Y"),
		NetIntRange("m_Type", 0, 'max_int'),
	]),`

### Kaizo Network Character

Extended character data for Kaizo Network servers

`NetObjectEx("KaizoNetworkCharacter", "kaizocharacter@m0rekz.github.io", [
		NetIntAny("m_Flags", default=0),
        NetIntAny("m_RealCurrentWeapon", default=-1),
        NetIntAny("m_Tick", default=0),
	], validate_size=False),`

### Kaizo Network Pickup

Kaizo Network Pickup Entity

`NetObjectEx("KaizoNetworkPickup", "kaizopickup@m0rekz.github.io", [
		NetIntAny("m_X", default=0),
        NetIntAny("m_Y", default=0),
        NetIntAny("m_Type", default=0),
        NetIntAny("m_Switch", default=0),
	], validate_size=False),`

### Player Ping (Kaizo Network)

Player ping (sent by Kaizo Network servers)

`NetObjectEx("KaizoNetworkPlayerPing", "kaizoplayerping@m0rekz.github.io", [
		NetIntAny("m_Ping", default=0),
	], validate_size=False),`

