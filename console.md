## Dreamcast Two-ways

**Dreamcast support is not installed by default** but there are two emulators you're able to install: **Redream** (standalone program) and **Flycast** (Retroarch core). Some games play better with either one of these so we can install both and you can set which emulator to run using the launch menu. Personally I think Redream is much better but you lose the ease of use of Retroarch.

Better in Redream, crappy in Flycast:

- San Fransico Rush 2049
- Star Wars Episode 1 Racer

### Redream

1. Retropie > Retropie Setup
2. Update RetroPie-Setup script
3. Manage packages
4. Manage experimental packages
5. 139 redream
6. Install from pre-compiled binary and then exit
7. Copy two bios files to ~/Retropie/BIOS/
8. Copy games to ~/Retropie/roms/dreamcast/

This is not a Retroarch core so it has it's own configuration menus.

!> You'll need a keyboard and mouse at first to configure your controller. After, you'll be able to use a controller for the menus. Be sure to set a button to open the Redream menu.

Press ESC to get into the menu. Use the mouse and click on input to setup your controllers:

- Buttons C and Z should be L1 and R1
- Use select button for Main Menu
- Use Xbox Button for Exit Emulator

If you find that games are running really fast with no sound press F6 to turn turbo/fast forward off.

#### Duplicate Games?

In the Redream *Games* section you might see duplicate game covers. Go into `Library` and click on one of the folders that point to the `dreamcast` folder. They're both the same folder.

#### Change Discs

Open the Redream menu and select Change Disc

#### Widescreen Cheat

Some games support widescreen. If you go into the Redream menu:

- select Edit Cheats
- turn Widescreen to on
- Restart Game


### Flycast

1. Retropie > Retropie Setup
2. Update RetroPie-Setup script
3. Manage packages
4. Manage experimental packages
5. lr-flycast
6. Install from pre-compiled binary and then exit
7. Copy two bios files to ~/Retropie/BIOS/
8. Copy games to ~/Retropie/roms/dreamcast/

Open a game, open the Retroarch menu (select X), turn on Video > Filtering.

Note: Flycast can also play Naomi arcade games.

---

### gdi vs cdi vs chd

Get the .gdi  or .chd of .gdi versions of a game if you can.

**.gdi** files are text files that tell Redream what the collection of files are to be used for a game. If you rename your .bin or .raw files be sure to update the contents of the .gdi file.

**.cdi** files are ripped games. They may have highly compressed movies or files removed. .gdi are complete copies.

**.chd** are like zip files. If you can find chd versions of the gdi files these will be most convenient.

### Dreamcast Windows CE games

!> Redream: As of August 2020, Windows CE based games **do not work**.

<details>
<summary>List of Windows CE Games</summary>

- 4x4 Evolution
- Armada
- Atari Anniversary Edition
- Bang! Gunship Elite
- Bust-A-Move 4
- Caesars Palace 2000: Millennium Gold Edition
- Championship Surfer
- Cherry Blossom
- Densha de Go! 2
- Ducati World Racing Challenge
- Eisei Meijin III: Game Creator Yoshimura Nobuhiro no Zunou
- For Symphony: With All One's Heart
- Fragrance Tale
- Get!! Colonies
- Giant Killers
- Happy Lesson
- Hello Kitty no Garden Panic
- Hello Kitty no Lovely Fruit Park
- Hello Kitty no Magical Block
- Hello Kitty no Waku Waku Cookies
- Hidden & Dangerous
- Hoyle Casino
- Hundred Swords
- Jimmy White's 2: Cueball
- Kaitou Apricot
- KISS: Psycho Circus: The Nightmare Child
- Kita e. White Illumination
- Kitahei Gold
- Marionette Company
- Marionette Company 2
- Maximum Pool
- Midway's Greatest Arcade Hits Volume 1
- Midway's Greatest Arcade Hits Volume 2
- Miss Moonlight
- Morita no Saikyou Reversi
- Morita no Saikyou Shogi
- The Next Tetris
- Net de Para: Nekosogi Paradise
- NFL QB Club 2001
- NFL Quarterback Club 2000
- Nightmare Creatures II
- Nishikaze no Rhapsody
- Plus Plum
- Princess Maker Collection
- Q*bert
- Railroad Tycoon II
- Resident Evil 2
- Rune Jade
- Sega Rally 2
- Sekai Fushigi Hakken! Troy
- Shinseiki Evangelion: Typing E-Keikaku
- Shinseiki Evangelion: Typing Hokan Keikaku
- Sno-Cross Championship Racing
- Soukou no Kihei: Space Griffon
- South Park: Chef's Luv Shack
- Spirit of Speed 1937
- Starlancer
- Super Producers
- Super Robot Taisen Alpha for Dreamcast
- Super Runabout
- Super Runabout: San Francisco Edition
- Sweet Season
- Taxi 2
- Tomb Raider Chronicles
- Tomb Raider: The Last Revelation
- Tom Clancy's Rainbow Six
- Tsuushin Taisen Logic Battle Daisessen
- UnderCover AD2025 Kei
- Urban Chaos
- Virtua Cop 2
- WebTV for Dreamcast
- Who Wants to Beat Up a Millionaire
- Wild Metal
- World Neverland Plus: Orurudo Oukoku Monogatari
- Worms Armageddon
- Worms World Party
- Yoshia no Oka de Nekoronde...
- Yuki Gatari

</details>

---



## PSX / PS1

### Bios 

Place here: `~/pi/Retropie/bios/SCPH1001.BIN` (all caps!)


### Increase Resolution

- run a game
- press Select + X (assuming you choose Select as your hotkey)
- open Quick menu
    - go to Options
    - Enhanced resolution (slow): enabled
    - Enhanced resolution speed hacks: enabled
- press back (B), back
- Settings
    - Video
        - Bilinear filter: on
- back, back
- Configurations
    - Save current configuration
- Exit (Select + X)


### Compress games

Coming...


## MAME


### Smash TV

Not sure why these are fucked up 'cause Robotron is fine. 

- hook up a keyboard
- start the game
- press Tab
- Choose Input (this game)
- Scroll and find and set (B1-4 are the Mame buttons, XBYA are your Retropie controller buttons):
    - B3 (up): X
    - B1 (down): B
    - B2 (left): Y
    - B4 (right): A
- press Tab and play


### Xenophobe

Get past service screen:
- With keyboard:
- press tab
- Dip Switches
- Service Mode: Off
