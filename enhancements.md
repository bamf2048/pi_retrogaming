# Retropie Enhancements

These are enhancments that aren't installed by default but that I think pretty cool.

## Dreamcast Two-ways

Some games play better with either Flycast or Redream. We can install both and you can set which emulation to use using the launch menu. Personally I think Redream is much better.

Better in Redream:

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

Press ESC to get into the menu. Use the mouse and click on input to setup your controllers. Buttons C and Z should be L1 and R1. 


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


If you find that games are running really fast with no sound press F6 to turn turbo/fast forward off.

.gdi files are text files that tell Redream what the collection of files are to be used for a game. If you rename your .bin or .raw files be sure to update the contents of the .gdi file.

!> As of August 2020, Windows CE based games **do not work**.

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

## Add more emulators and ports

**Retropie-Extra** is a collection of unofficial installation scripts for emulators, ports and libretrocores not included in Retropie.

!> Retropie-Extra is no longer mantained but still works.

```
cd ~
git clone https://github.com/zerojay/RetroPie-Extra.git
cd RetroPie-Extra/
./install-extras.sh
cd ~/RetroPie-Setup
sudo ./retropie_setup.sh
```

Source: https://github.com/zerojay/RetroPie-Extra


## Demo mode

This script plays a random games like a slideshow.

https://retropie.org.uk/forum/topic/25551/demo-mode-random-starting-of-games-for-es-retropie-menu


## Play Retropie in a browser from another computer

Install on a Pie, connect to your network via ethernet and play on a browser on your PC.

http://www.linux-projects.org/uv4l/tutorials/play-retropie-in-browser/


## Add "Pixel" Desktop

This is a full graphic UI with Chromium. You might find it easier to manage files using this.

In Emulationstation, go to Retropie Setup > Configuration / Tools > Raspbiantools > Install Pixel Desktop Environment.

You can go to the desktop in the Ports menu in Emulationstation or type `startx` from the terminal.


### Add Synaptic to Pixel Desktop

Allows you to easily install desktop applications. Synaptic is the App Store before there was the App Store.

```
sudo apt install synaptic
```
