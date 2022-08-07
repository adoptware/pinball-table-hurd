SPDX-FileCopyrightText: 2020 Paolo Caroni
SPDX-FileCopyrightText: 2020 rzr
SPDX-FileCopyrightText: 2022 Joseph Engelhardt
SPDX-License-Identifier: GPL-2.0-or-later


The Hurd table is a creation of Paolo Caroni, 
released under the same licences of The Emilia Pinball Project;
if The Emilia Pinball Project changes version of GPL, the Hurd Table can do the same.

The files gnu.{png,.xcf} and label.{png,xcf}
are derived works from 
"A Bold GNU Head" https://www.gnu.org/graphics/heckert_gnu.html
by Aurelio A. Heckert https://web.archive.org/web/20150609000539/http://wiki.colivre.net/Aurium/WebHome
which is released under one of the following licences:
GNU-FDL-1.3 https://www.gnu.org/licenses/fdl-1.3.html
FAL-1.3 https://directory.fsf.org/wiki/License:FAL1.3
CC-BY-SA-2.0 https://creativecommons.org/licenses/by-sa/2.0/

Those terms also apply to related files.
FAL-1.3 is the preferred license since CC-BY-SA-2.0's 4.b
can be problematic for some distribution channels.

Many thanks for the help in the packaging to rzr.

Additional sound design in Audacity by Joseph Engelhardt.

The Hurd table includes:

## Sounds:

bump.wav                        From "Mint play" https://commons.wikimedia.org/wiki/File:Mint_play.ogg
Bumpers				Recording of Rotamint Mint slot machine mechanisms
				By miq
				This audio file came from pdsounds.org and has been released into the public domain by its author.
				Edited from original

bumphard.wav                    Composite of "Peliautomaatti, Yksikätinen rosvo" https://freesound.org/people/YleArkisto/sounds/316887/
Targets				From the Finnish Broadcasting Company, Yle Archives https://yle.fi/aihe/elava-arkisto
				Used under the Creative Commons Attribution 4.0 License. https://creativecommons.org/licenses/by/4.0/
				& "Cash Register Purchase" https://freesound.org/people/Zott820/sounds/209578/
				By Zott820 https://freesound.org/people/Zott820/
				Used under the Creative Commons 0 License. https://creativecommons.org/publicdomain/zero/1.0/

bumpsoft.wav                	From "Peliautomaatti, Yksikätinen rosvo"
Kickers & slingshots		Clipped from original

flip.wav                        From "Peliautomaatti, Yksikätinen rosvo"
Flippers			Clipped from original

freesoftwaresong.xml            "Free Software Song"
freesoftwaresong.mid		Lyrics by Richard Stallman https://www.gnu.org/music/free-software-song.html
freesoftwaresong.ogg		Melody from "Sadi Moma", a traditional Bulgarian folk song https://en.wikipedia.org/wiki/Sadi_Moma
Gameplay soundtrack		Richard Stallman and the Free Software Foundation claim no copyright on this song.
				Files written with MuseScore https://musescore.org/

gameover.wav                    "Game Over Arcade" https://freesound.org/people/myfox14/sounds/382310/
Game Over sting			By myfox14 https://freesound.org/people/myfox14/
				Used under the Creative Commons 0 License.

intro.ogg                       From "90s Pinball in Arcade" https://freesound.org/people/mrpagliara/sounds/391560/
Waiting to play again		By mrpagliara https://freesound.org/people/mrpagliara/
				Used under the Creative Commons Attribution 3.0 (Unported) License. https://creativecommons.org/licenses/by/3.0/
				Clipped and looped from original

loop.wav                        Composite of "Mint play" and "Peliautomaatti, Yksikätinen rosvo"
Entering habitrail		

nudge.wav        		Composite of "Trip on Metal Boxes" https://freesound.org/people/Zott820/sounds/370346/
Nudge				By Zott820 https://freesound.org/people/Zott820/
				Used under the Creative Commons 0 License.
				& "slot machine vending hits angry punches thud" https://freesound.org/people/kyles/sounds/637820/
				By kyles https://freesound.org/people/kyles/
				Used under the Creative Commons 0 License.

shoot.wav			From "Peliautomaatti, Yksikätinen rosvo"
Entering upper playfield 	
Shots from saucer		Clipped from original

up.wav				From "Ball on Table" https://freesound.org/people/NeatoEnt/sounds/458137/
Through habitrail		By NeatoEnt https://freesound.org/people/NeatoEnt/
				Used under the Creative Commons 0 License.
				Clipped from original

## Art

By Paolo Caroni https://github.com/paolo-caroni
released under the same licences of The Emilia Pinball Project. https://github.com/adoptware/pinball

floor.png                        write with gimp
floor3.png                       write with gimp
floor4.png                       write with gimp
floor-room.png                   write with gimp
floortotal.xcf                   write with gimp
gnu.png                          write with gimp (contains GNU logo under FAL-1.3)
gnu.xcf                          write with gimp (contains GNU logo under FAL-1.3)
hurd.png                         write with gimp (contains HURD logo under CC-BY-SA-3.0)
hurd.xcf                         write with gimp (contains HURD logo under CC-BY-SA-3.0)
label.png                        write with gimp (contains GNU logo under FAL-1.3)
label.xcf                        write with gimp (contains GNU logo under FAL-1.3)
sub.png                          write with gimp
tiles.png                        created from the same of the tux table (develop) with gimp
tiles2.png                       write with gimp
Wood.jpg                         write with gimp

## Code

ModuleHurd.cpp                   created from ModuleTux.cpp (develop) with gedit
pinball.pbl                      table designed with pinedit

(The .xcf and .xml file serve only as source code for easy changes)