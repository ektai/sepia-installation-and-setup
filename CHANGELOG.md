## Release history and changelog

### v2.2.2 - 2019.05.31

Updated client to v0.18.0:
* Added new 'music-search' and 'media' function to client-controls with Android MEDIA_BUTTON Intent support
* Added selector for default music app including YouTube, Spotify, Apple Music (Browser/Mobile) and VLC (Android only)
* Added music-search as link-card type and added support for YouTube embedded videos (including stop and next command interface)
* Added new skins "Spots" and "DarkCanary"
* Added new context menu for cards to link and timer cards with buttons like 'share' and 'copy' (link)
* Added 'add to Android calendar' and 'add to Android alarms' buttons to timer cards
* Improved link-cards
* New and upgraded implementation for universal deeplinks (e.g. share reminders, requests, links, etc.)
* Filled Teach-UI help button with many examples and info for each command
* Added Teach-UI support for flex-parameters in sentence_connect (see new help for more info)
* Added new platform_controls command to Teach-UI (one sentence - device dependent actions like URL-call or Android-Intent)
* Improved reconnect behaviour after lost connection
* Added server version check and incompatability warning to start-up sequence 
* Added new client info to server requests (deviceId, platform, default music app etc.)
* Fixed and imroved 'Hey SEPIA' code (still some smaller issues left)
* Added Android ASSIST Intent listener to allow SEPIA to become default system assistant (long-press on home button)
* Added Android Intent plugin
* Added Android navigation bar plugin for colored soft-keys (bottom of screen)
* Fixed some issues related to active chat-channel and messages
* Added onActive and onBeforeActive event queue
* Added button to store/load app settings to/from account after login
* Support for follow-up messages from server (received after initial service 'completion')
* Updated CLEXI client library to v0.8.0 (with support for CLEXI http events)
* Added CLEXI connection status indicator
* Improved handling of well-being/pro-active notifications (e.g.: inform server of received notes to prevent duplicated messages, deliver when active, etc.)
* Improved my-view updates
* Improved list scrolling on footer minimize-click
* Improved audio player animation
* Improvements to pop-up messages
  
Updated Assist-server to v2.2.2:
* New MediaControls parameter and improved ClientControls service to handle 'next song', 'stop music', (improved) 'volume', etc.
* Added dynamic select parameter to ServiceBuilder to easily add choose-one-of questions to any service
* Added SpotifyApi (see properties file for API client/key) and iTunesApi classes to handle music search requests
* New service: MusicSearch with parameters for song, artist, service, playlist, genre and support for music search link-cards
* New service: PlatformControls (see client Teach-UI for more info)
* Improved cards and URL actions in some services (location, direction, music, etc.)
* Tweaked WebSearch service to better handle YouTube
* Added flex-parameter support to sentence matcher (see client Teach-UI for more info)
* Updated news outlets
* Added deviceId, platform and custom data to NluInput (for things like default music app etc.)
* Added support for 'recently triggered pro-active notification' to events manager
* Improved NLU and several parameters, e.g. action, number, list sub-type, date/time
* Improved link-cards with new type and brand options (e.g. to distinguish music links and web-search)
* Added support to store and read app settings (per user-id and device-id)
* Added follow-up message support (delayed assistant answers etc.) for duplex connections (e.g. with default WebSocket client)
* Improved RSS feed reader (again! less errors finally and improved backup check for outdated content)
* Moved basic Elasticsearch interface to core-tools
  
Updated WebSocket Chat-Server to v1.1.1:
* Support for follow-up messages (see assist-server and client for more info)
* Moved code for channel management endpoint to new ChannelManager class
* Improved SocketChannel with JSON import/export of data
* Preparations for improved channel create/join support
  
Updated Core-tools to v2.2.1:
* Added new content to CMD, PARAMETERS and CLIENTS
* Improved Connectors (e.g. http GET with headers and better encoding)
* Moved Elasticsearch interface from assist-server package
* Updated FasterXML/jackson core to 2.9.9 to include latest security fix

### v2.2.1 - 2019.03.24

Updated client to v0.17.0:
* Added support for Bluetooth LE beacons to be used as remote control triggers
* Added [Node.js CLEXI](https://www.npmjs.com/package/clexi) integration to handle BLE support on e.g. Desktop browsers
* Improved remote control settings (aka gamepad settings) to support BLE beacons
* Added new client-controls function including new Teach-UI command (use e.g. to control volume or call Mesh-Nodes and CLEXI form client)
* New wake-word settings, fixed wake-word for AO-mode, proper settings storing and auto-load of engine
* Store and load selected voice (per language)
* New 'view' URL parameter to e.g. launch Always-On mode ('aomode') directly on start
* New 'isTiny' URL parameter to be able to handle very small screens (e.g. 240x240) via sepiaFW-style-tiny.css file
* New Always-On animations (mouth). AO-mode can be activated via double-tap on SEPIA label (center top)
* UX tweaks (mic press stops alarm, bigger shortcuts button area etc.) and skin improvements
* Renamed 'Chatty reminders' to 'Well-being reminders' (and made them opt-in by default) ;-)
* New idle-time action queue (used e.g. in client-control to get voice feedback on error)
* Custom environmental variable during AO-mode: avatar_display (use for services)
* Fixed a bug in Chrome TTS and other minor bug- and UX-fixes
  
Updated Assist-server to v2.2.1:
* Added client-controls service and client-function parameter to handle e.g. volume control, toggle settings and AO-mode, trigger a Mesh-Node or CLEXI call from client and more
* Imroved RSS feed reader, updated ROME tools and fixed news-outlets
* Improved some NLU parameters (e.g. radio station and location)
  
Updated Mesh-Node to v0.9.9:
* Added PIN and localhost security options to plugins
  
Notable mentions:
* SEPIA STT-Server has been updated with new english Kaldi model
* Smaller fixes to the SEPIA control HUB
* A [browser plugin](https://chrome.google.com/webstore/detail/sepia-framework-tools/gbdjpbipoaacccffgemiflnhfldahopp) has been release to improve the SEPIA client running in Chromium kiosk mode

### v2.2.0 - 2019.01.31

New additions and changes:
* Added [SEPIA Mesh-Node server](https://github.com/SEPIA-Framework/sepia-mesh-nodes) to the SEPIA-Home bundle: A small, lightweight server that can be distributed in your network to run tasks securely triggered from anywhere using SEPIA.
* Completely rebuilt the SEPIA Admin-Tools (on top of the ByteMind Web-App template) and renamed them to SEPIA Control-HUB (internally) :-)
* Added a web-based code editor called Code-UI to the Control-HUB (following in the footsteps of the Teach-UI ^^) that can be used to code and upload custom Smart-Services to the SEPIA core server and plugins to a SEPIA Mesh-Node.
* The code editor can load services and plugins directly from the new [SEPIA Extensions repository](https://github.com/SEPIA-Framework/sepia-extensions). You can think of it as some kind of "skill store light", contributions welcome ;-)
* Introduced [the new SEPIA Java SDK](https://github.com/SEPIA-Framework/sepia-sdk-java) to build, test and upload Smart-Services (standalone, download separately).  

Updated Assist-server to v2.2.0:
* Many internal changes to support the new Java SDK, the rebuilt Control-HUB and the Code-UI
* Implemented the feature to add "real" custom answers (multi language + variation) right inside a service. Previously they had to be defined in the assistant database. This will make it easier to deliver high quality dialog with the SDK.
* Added a Mesh-Node connector to handle calls to Mesh-Node Plugins like a service with parameters (this enables the new 'plugin' command in the Teach-UI, see below)
* Tweaked settings endpoint to write changes submitted by Control-HUB permanently to the active config-file (previously they were lost after restart)
* Improvements in 'Number' and 'DateAndTime' parameters
* Improved 'Alarm' service to better handle "this event is in the past" cases
* Added a limited-size cache for custom commands (saves some database calls)
* Improved Java 9+ support
* Fixes and clean-ups all over the place
* Updated SEPIA core tools to v2.2.0 (this applies to all core servers)  

Updated client to v0.16.0:
* Added new 'plugin' command (mesh_node_plugin) to the Teach-UI to easily interface with SEPIA Mesh-Nodes (see above)
* Added speech-to-text output to AlwaysOn-mode
* Automatically close await-dialog state (yellow mic) after 15s
* Improved my-view automatic refresh (e.g. after wake-up from background)
* Fixed link-cards for dark skins and HTML link colors
* Added skin 'Nightlife'
* Translated tutorial to German (and added language support to Frames)
* Added ACTION "switch_language" to experiment with custom services in non-default languages
* Improved demo-mode
* Fixed a bug in the mic-reset function
* Fixed a bug in Teach-UI for unsupported commands

### v2.1.3 - 2018.12.16

Updated client to v0.15.2 with following changes:
* Added drag & drop module and applied it to shopping and to-do list for sorting (activate via long-press on item check-button)
* Added 3-states support for to-do lists (similar to Kanban-cards: open/in-progress/done)
* Updated to-do/shopping list design and list context-menu in general
* Updated tutorial with new list features and generally more info
* Added a help and support button to settings menu (pointing to SEPIA docs page)
* Improved alarms during AlwaysOn-mode
* Introduced smart-microphone toggle (enable in settings) that auto-activates mic on voice based questions (beta)
* Added new skins 'Study', 'Odyssey1', 'Odyssey2', 'Professional' (with less rounded corners ^^), reworked 'NeoSepiaDark' and changed old one to 'Malachite', updated 'Grid' and tweaked other styles
* Fixed some bugs in GPS event handling
* Improved handling of large lists to show them more often in 'big-results'-view and sorted time-events by date
* Split Alarms/Timers button in shortcuts into 2 buttons
* Introduced upper limit for maximal visible chat entries (to improve performance)
* Added mood indicator to AlwaysOn-mode avatar (mouth angle ^_^)
* Improved hotkeys/gamepad config menu
* Reworked AudioRecorder module to support different recorder types
* Introduced new WakeTriggers module and added new config options (e.g. (dis)allow remote hotkey)
* Improved file reader to handle array-buffers so that we can import WebAssembly code
* Added Porcupine JS wake-word tool as 'xtension' and beta-test view to experiment with 'Hey SEPIA' (access from settings)
* Added embedded module with (very) basic offline NLU and services (currently only used for demo-mode e.g. to load a demo list)
* Updated demo mode with offline custom buttons
* Fixed a bug that crashed app when a Bluetooth devices was (dis)connected  

Updated Assist-server to v2.1.4:
* Read more than 10 lists with one request (handle paging in service)
* Improved lists NLU ('show me my A and B lists'), radio NLU ('play radio with songs of BAND'), time/date and location parameters
* Updated news-outlets, Wired Germany will close down end of 2018 :-(  

Other changes:
* Improved installation scripts

### v2.1.2 - 2018.11.xx (internal version)

Updated client to v0.14.3 with some nice upgrades, e.g.:
* Define custom button for your own commands via the Teach-UI
* Add music stream commands via Teach-UI
* Always-On view with animated avatar and controls (beta)
* Power-events e.g. open AO-mode on power plugin
* Gamepad and hotkey support for remote microphone trigger and other controls (beta)
* Design update of quick-access menu (bottom left) and additional smaller changes (skins etc.)
* Fixed bug where radio won't turn off via voice
* Fixed a bug that prevented timer stop via voice
* Many smaller fixes  

Other changes:
* Teach-server update to v2.0.2 with custom buttons support for personal commands
* Assist-server update to v2.1.3 with reworked radio stations (external, curated file), time/date answers and fixes
* Admin-Tools support for server URL parameters
* Added server backup script (Unix) and updated Windows setup and run
* Fixed a UTF-8 encoding bug for Windows

### v2.1.0a - 2018.10.26

Updated assist-server to v2.1.0 with numerous improvements, e.g.:
* Added smart home NLU, parameters (device, room) and service BETA via openHAB integration (currently testing Hue lights)
* Updated news service and exported the hard-coded outlet data to external .json file for easier editing and fixing
* Updated Bundesliga soccer service with data of new season
* Updated and improved setup scripts (e.g. for admin password reset)
* Fixes in NLU and parameter extractions (e.g. for location parameter)
* Improved handling of internal error with proper client message  

Other changes:
* Upgraded dependencies, mainly: Java Spark (2.5.4 -> 2.8.0) and Jetty Server (9.3 -> 9.4)
* Updated SEPIA Reverse-Proxy to use external properties file and added some features
* Added new menues to Admin-Tools (e.g. smart home configuration and speech recognition)
* Many smaller bugfixes

### v2.0.1a - 2018.07.07

* Updated assist-server to v2.0.1 (smaller bugfixes)
* Added SEPIA Reverse-Proxy, a tiny JAVA proxy for the custom-bundle. This will save you the installation of a 3rt-party proxy and it works well with ngrok ;-)
* Updated SEPIA HTML client to v0.11.4 (better hostname handling)
* Updated core-tools to v2.0.1 and replaced 'connection-check.jar' with 'sepia-core-tools-*.jar connection-check'

### v2.0.0a - 2018.07.02

First public, open-source release of SEPIA-Framework 2.0 (v1 was proprietary software).