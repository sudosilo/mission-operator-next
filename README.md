Mission Operator

Mission Operator is a field scanner console for anyone curious about what is in the air and on the airwaves nearby.

It asks for the device location, then scans and lists nearby signals by type. Aircraft come from live flight data. Other types include cell towers, Wi-Fi access points, Bluetooth, ham repeaters, Meshtastic and Helium nodes, and rail. A logbook keeps what was found, and a settings panel adjusts the scan.

Live at mission-operator.vercel.app

Checked every morning by Control Troll, an automated test system that loads every app and clicks through its features.

Latest change. 2026-10-31, v2026.10.31. Every relay call now has a timeout, so a slow upstream fails fast instead of hanging the request, and every relay answers in the same shape with a hint instead of a bare 500. The three feeds that need a server key say so plainly: Settings lists each missing key with where to get it, the top bar shows a KEYS MISSING tag, and the app stops re-polling a feed it knows it cannot get until RETRY KEYS is pressed. Wi-Fi and Bluetooth scores are now deterministic, and the page has labels, a description and share tags.

Full history is in CHANGELOG.md.

Optional server keys
--------------------

Aircraft, ports, cell towers, rail stations, portals, Meshtastic nodes and weather stations work with no configuration. Three feeds stay empty until their key is set as an environment variable in the Vercel project, then redeployed:

- N2YO_KEY, satellites (Starlink, GPS, weather sats, debris, rocket bodies). Free key from n2yo.com.
- AISSTREAM_KEY, ships (AIS). Free key from aisstream.io.
- WIGLE_AUTH, Wi-Fi and Bluetooth on the scan button. The "Encoded for use" value from your WiGLE account API page.

Nothing else in the app depends on them.
