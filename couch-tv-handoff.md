Set up couch-tv (https://github.com/Seagey/couch-tv) on my TV. Follow the repo's AGENTS.md.
I have already answered every question and said YES to the plan below, so after you find the TV
and check it, go straight to setup (AGENTS.md step 4). Still tell me before each step on the TV.

This computer is Windows. Use Git Bash for the shell scripts and Python 3.11+ from python.org
(install it with my OK if missing). The venv's Python is .venv/Scripts/python.exe, so run the
scripts with PY=.venv/Scripts/python.exe (apply.sh reads PY), and call the .py tools with that
Python directly.

The plan (already agreed):
- TV: Philips 55OLED856/12 (2021, Android TV), on the same Wi-Fi as this laptop.
- Option A: TV home only, no bridge, normal TV remote. Download couch-tv-home.apk from the
  Releases page into dist/.
- Switch off what apply.sh switches off, setup wizard included (I accept the Wi-Fi risk; I will
  rejoin Wi-Fi on the TV if it forgets it). Have me allow USB debugging ("Always allow") first.
- After install, show me how to put Netflix, Plex, Disney+, YouTube first in the dock (hold OK),
  and show me the undo command.
- I asked about keeping the old home on a second user profile: check whether this TV has Android
  user profiles at all (I expect not) and tell me.

config.json (repo root; fill in the TV's IP once found):

{
  "default_tv": "living-room",
  "tvs": [
    {
      "id": "living-room",
      "name": "Living room",
      "label": "Philips 55OLED856/12",
      "ip": "SET_YOUR_TV_IP",
      "adb_port": 5555,
      "wake_on_lan": false,
      "quick": ["look"]
    }
  ],
  "people": [{ "id": "me", "name": "Me" }],
  "home": {
    "look": "night",
    "scenes": ["night", "dawn"],
    "scene_seconds": 300,
    "clock": "24h",
    "dock_size": 10,
    "hide_packages": [],
    "language": "en"
  },
  "phone_remote": false,
  "ask": { "enabled": false },
  "weather": { "lat": 44.4268, "lon": 26.1025, "place": "Bucharest", "timezone": "Europe/Bucharest" },
  "country": "RO",
  "screens": []
}
