# VNOC5 Tournament Overlay - by [Boy]DaLat
Overlay and Controller are in [Releases](https://github.com/FukutoTojido/vcl-guide/releases)
## Available scenes
- `/`: Main Overlay, used when a match is playing
- `#/mappool`: Mappool Scene, switch to this scene when the match is having a Protect-Ban-Pick session
- `#/winner`: Winner Scene, switch to this scene when the match has ended
- `#/showcase`: Showcase Scene, used for mappool showcase
- `#/countdown`: Countdown Scene, including schedule
## Setup
### Overlay
- Extract the overlay and put it in your `tosumemory/static` folder under a folder named `VNOC5` **(MANDATORY! DO NOT CHANGE THE FOLDER NAME TO ANYTHING ELSE)**
- Just to make sure, your folder structure **MUST** be like this:
```
.
└── <tosumemory folder>/
    └── static/
        └── VNOC5/
            ├── assets/
            ├── index.html
            ├── ...
            └── ...
```
### Controller
- Extract anywhere you can have access except for `C:/` drive

## Running the overlay
You must follow these steps in the correct order:
- Start osu! tournament client
- Start `tosumemory` (wait for them to load all clients)
- Start `VNOC5 Overlay Controller`
- Use the scene on OBS by opening these urls on Browser Source:
  - Overlay: `http://127.0.0.1:24050/VNOC5/`
  - Mappool: `http://127.0.0.1:24050/VNOC5/#/mappool`
  - Winner: `http://127.0.0.1:24050/VNOC5/#/winner`
  - Showcase: `http://127.0.0.1:24050/VNOC5/#/showcase`
  - Countdown: `http://127.0.0.1:24050/VNOC5/#/countdown`

- Note: For Showcase Scene, in order to change Stage Name, please use `/#/showcase/:stageId`. In which `stageId` respectively correspond to:
  - `0`: Qualifiers
  - `1`: Swiss Stage 1 + 2
  - `2`: Swiss Stage 3 + 4
  - `3`: Swiss Stage 5
  - `4`: Knockout Week 1
  - `5`: Knockout Week 2
  - `6`: Knockout Week 3
> E.g: `http://127.0.0.1:24050/VNOC5/#/showcase/1`

- Note: For Countdown Scene, to configure the countdown destination, please add the `dest` parameter into the URL, with `dest` correspond to the local time of the match (mm:ss)
> E.g: `http://127.0.0.1:24050/VNOC5/#/countdown?dest=21:00`

## Use the Controller
- Select the current stage
- Select the current match
- Change the match log format (switch Map Slots' state to Pick / Ban / Protect respectively to the current stage)
- Turn on "Beatmap Details"
- When a beatmap is picked, left-click the desired Map Slot and select that beatmap. In case you fucked up, you can right-click the Map Slot to remove the beatmap from the slot.

## Configurations
### `mappool.json`
```json
{
  "<MD5 hash of the beatmap>": {
    "metadata": {
      "artist": "",
      "title": "",
      "difficulty": "",
      "mapper": "",
      "id": 0 // The Beatmapset ID, not the Beatmap ID
    },
    "stats": {
      "CS": 0,
      "AR": 0,
      "OD": 0,
      "BPM": {
        "common": 0 // Don't ask, just follow it
      },
      "fullSR": 0,
    },
    "info": {
      "index": 0, // The number in NM1 / HD1,
      "mod": "", // NM, HD, HR, DT, TB,
      "isCustom": true // or false
    }
  },
  ...
}
```
### `rounds.json`
```json
[
  {
    "name": "",
    "bans": 0,
    "protects": 0,
    "bestOf": 0
  },
  ...
]
```
### `matches.json`
```json
[
  {
    "id": 1,
    "player": {
      "red": {
        "name": "",
        "seed": 0,
        "id": 0,
        "stats": {
          "aim": 0,
          "highBPM": 0,
          "highAR": 0,
          "technical": 0,
          "tapping": 0,
          "precision": 0,
          "lowAR": 0
        }
      },
      "blue": {
        "name": "",
        "seed": 0,
        "id": 0,
        "stats": {
          "aim": 0,
          "highBPM": 0,
          "highAR": 0,
          "technical": 0,
          "tapping": 0,
          "precision": 0,
          "lowAR": 0
        }
      }
    }
  }
]
```
