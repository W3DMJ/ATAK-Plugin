# Meshtastic Plugin
Offical Meshtastic ATAK Plugin for sending CoT to IMeshService in the Meshtastic Android app.

# Meshtastic Plugin Tool menu
There is now a Meshtastic Tool menu, it currently is only used for recording Voice Memos. Voice memos will record your speech to text then send a Meshtastic text message. If users enable "Text to Speech" in preferecnes the message will be read outloud. Only English is supported currently. The Speech to Text is performed with the Vosk library.

# Settings
The plugin currently has the following settings:
- Enable relay to server, this forwards all CotEvents (except DMs) to any connected TAKServers
- Enable relay from server, this forwards all PLI and All Chat Rooms geochats from connected TAKServers to Meshtastic
- Show all Meshtastic devices, this will place Sensor CoTs on the map for meshtastic devices
- Do not show Meshtastic devices without GPS, this will not place Sensor CoTs for meshtastic devices without GPS (0,0)
- Do not show your local node, this will not place a Sensor CoT on the map for the meshtastic device currently bound to the EUD
- Use Meshtastic GPS as External GPS
- Enable reporting rate controls, this will set ATAK's reporting rate to Constant and allow you to pick a interval from 1,5,10,20,30 minutes
- Reporting rate, the menu to pick the interval in minutes
- Only send PLI and Chat messages, this will only use the atak.protos which are optimized for speed (no libcotshrink)
- Use Text to Speech for incoming messages, this will read outloud any Meshtastic TEXT_MESSAGE_APP (basic meshtastic text messages)
- PTT KeyCode, this allows you to define what hardware key to use to enable voice recording (see the Mestastic Plugin's Tool menu "Voice Memo")
- Meshtastic Channel Index, this allows you to define what channel to send ATAK messages on (0 by default)
- Meshtastic Hop Limit, this allows you to adjust the hop limit for ATAK messages (3 by default, 8 max)
- Allow SWITCH command, this opts-in for allowing nodes to switch your node to Short/Fast for file transfers

# Video Walkthrough

https://www.youtube.com/watch?v=7cn4ofiSd0A

# Using Meshtastic device as external GPS device
ATAK can use GPS positioning data of Meshtastic device as a source of GPS data for itself.
In order for this to work following conditions have to be met:
- Meshtastic device should have GPS receiver (for example LILYGO T-Beam)
- Meshtastic device should be configured to send GPS positions (GPS enabled, intervals are configured properly)
- ATAK should be configured to use external GPS (Settings -> Callsign and Device Preferences -> Device Preferences -> GPS Preferences -> GPS Option -> Ignore internal GPS / Use External or Network GPS Only)
- Meshtastic Plugin should have External GPS setting enabled (Settings -> Tool Preferences -> Specific Tool Preferences -> Meshtastic Preferences -> Use Meshtastic GPS as External GPS)
- Show all Meshtastic Devices should be off to avoid duplicating markers on the map