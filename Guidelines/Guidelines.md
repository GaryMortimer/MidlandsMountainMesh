# Standard Meshtastic Settings — Newbies & Members Guidelines

**Purpose:** These settings are the group's standard starting point. The aim is to keep the mesh usable as it grows, avoid unnecessary RF traffic and preserve capacity for normal messaging and emergency/SAR use.

1. **BASIC / NEW MEMBER SETUP**

| | |
|---|---|
|**Region**|European Union 868MHz|
|**Preset**|LONG_FAST|
|**Number of  Hops**|3|
|**Frequency Override**|869.525|
|**Transmit Power**|22|
|**Device Role**|CLIENT|

Do not change the frequency or modem preset when joining the network. If you have reset your node or are unsure, start with the Meshtastic defaults for European Union 868MHz and use the group's LongFast channel.

2. **NODE ROLES**

* **CLIENT:** Default for most users and normal home nodes.
* **CLIENT_MUTE:** Useful for desk/table nodes when another suitable node is already nearby. Avoid leaving several nearby nodes as active Clients unnecessarily.
* **TRACKER:** For genuinely mobile equipment such as vehicles, people or other tracking applications.
* **CLIENT_BASE:** For a particularly useful, well-positioned node intended to provide reliable coverage/bridging.
* **ROUTER / REPEATER:** Dedicated infrastructure only, and should be community coordinated.

3. **ROOFTOP / HIGH-LOCATION NODES**

* A good rooftop/home node is generally best configured as CLIENT unless it has a specific infrastructure role.
* Use **CLIENT_BASE** where the node has a particularly useful position and purpose.
* Use **ROUTER/REPEATER** only where the site is genuinely suitable and the community has agreed to it.
* Do not select a router role simply because more hops or coverage sounds better. High sites can hear many nodes and unnecessary infrastructure can increase congestion.

4. **ROUTERS & FAVOURITES**

* If you can directly hear an established community ROUTER/REPEATER or useful CLIENT_BASE node, **favourite it**.
* For troubleshooting a long route: run a traceroute, identify the useful infrastructure hop, favourite the appropriate node and test again.

5. **ROUTER SPACING**

* Approximately **20 km**is a useful target between major infrastructure nodes, with shorter distances preferable where practical.
* Do not assume a link approaching or exceeding 30 km is reliable just because it works occasionally.
* Good antenna height and clear line-of-sight are more important than simply increasing TX power or antenna gain.
* Dedicated repeaters should be community coordinated.

6. **GPS / POSITION SETTINGS**

* **Fixed/home/base nodes:** GPS may be disabled if not required, or use a long position interval (hours rather than minutes).
* **Mobile/tracker nodes:** approximately 15–30 minutes or slower is a sensible normal range.
* During an active SAR operation, faster reporting may be justified.
* Smart Broadcast can be useful for mobile nodes because reporting can respond to movement rather than transmitting constantly while stationary.
* Position accuracy on the public LongFast network is deliberately reduced/fuzzed for privacy. Use an appropriately configured private channel when accurate/private location is required.

7. **TELEMETRY**

* For ordinary fixed nodes, use approximately **1–2 hours or longer** as a sensible starting point.
* Solar/infrastructure nodes should prioritise reliability and uptime rather than generating unnecessary telemetry traffic.

8. **MQTT**

* **Do not blindly enable MQTT bridging on the public mesh.**
*  Uncontrolled MQTT bridging can bring large amounts of outside traffic into the local RF network and increase congestion.
* If MQTT is required, discuss it with the group first and understand exactly what is being bridged.

9. **PRIVATE CHANNELS**

* Suitable for SAR operations, community-watch operations, coordinated emergency activity, private operational communications and accurate/private GPS information.
* Giving a channel the same name does not make it private or automatically compatible with another channel.
* **The PSK/key provides the encryption.** Shared private channels require matching configuration/key.

10. **SAR / EMERGENCY USE**

* Public LongFast: general chat, node discovery, testing, roll calls and network awareness.
* Operational SAR traffic should use a dedicated private/tactical channel so emergency communications do not compete with normal mesh traffic.
* During a major SAR operation, the wider group should be notified and ordinary users should reduce traffic or switch equipment off where requested.

## THE GOLDEN RULE

 Keep ordinary nodes quiet. Let well-positioned infrastructure do the heavy lifting. Keep hop counts low. Favourite useful infrastructure. Don't flood the RF network. Coordinate dedicated routers/repeaters. Keep emergency capacity available.

 **NEW TO THE GROUP? START HERE**

 | | |
|---|---|
|**Region**|European Union 868MHz|
|**Preset**|LONG_FAST|
|**Number of  Hops**|3|
|**Frequency Override**|869.525|
|**Transmit Power**|22|
|**Device Role**|CLIENT|
|**GPS**|Sensible / slow interval|
|**Telemetry**|Slow interval|
|**MQTT**|OFF unless coordinated|
