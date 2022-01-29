# Stealth
V1.2
Morrowind MWSE-Lua Stealth mod

#### Short explanation

    Sneak is now consistent, predictable, and fun
    The sneak icon now fades based on your stealth level
    Attacks made from behind while stealthed now guarantee a hit
    Invisibility is reduced in power for realism and balance (but still great)
    Full configuration menu to tweak anything you don't like


#### Long explanation
Stealth in vanilla Morrowind is incredibly frustrating to say the least. While many of the settings were adjustable,
they relied entirely on a random number generator that would compare your attributes to other NPCs, and it did so every 5 seconds.
This caused you to constantly pop in and out of stealth, and take multiple seconds to go into stealth and be noticed. It was a mess.

Thanks to MWSE-lua, I have the ultimate power to replace the formula entirely, and I've done to using the original as a guide.

The original formula can be found here

The new formula goes something like this:

[Player]

    base = (Sneak + Agility * 0.2 + luck * 0.1)
    Subtract penalties for wearing medium or heavy armor
    Multiply by +25% for full fatigue or -25% for empty fatigue
    Multiply by between 0.5 and 10 depending on distance to the target (closer is lower)
    Add 50% of chameleon, add invisibility bonus


[NPC]

    base = 150% of their sneak skill (most NPCs are very blind, and they rarely have any bonuses) + 0.2 agility + 0.1 luck - blinded effect
    If you are within the front/side viewing angle of the NPC, multiply by 3, if not, multiply by 0.5
    Multiply by +25% for full fatigue or -25% for empty fatigue


[Final]
If player - detector is >= 50 (adjustable), you are sneaking

#### Rant on Invisibility

It's impossible to address stealth without also addressing invisibility mechanics. Previously, invisibility made you perfect.
You could not be seen whatsoever. In this mod, invisibility makes you permanently "behind the enemy" and provides a flat bonus.
Why would invisibility help you if the enemy couldn't see you? This makes sneak or chameleon still necessary to hide, and means
enemies still still attack you if you are very close to them and invisible!

And of course invisibility's close relative chameleon
Chameleon in the base game just added flat sneak skill. In this, by default, it adds [0.5, adjustable] sneak skill.
It's still fantastic, just not game-breakingly so.

#### InvisFix

Invisibility is completely and utterly broken. A mage of mediocre worth can become a master thief in a single spell.
Want to steal a limeware platter? Just cast invisibility in front of someone and then grab it, problem solved!
This mod includes a toggleable feature called Invis Fix that drops stealth before you activate something.


There is a Mod Configuration Menu included:

-Toggle mod on/off

-Toggle invisibility fix

-Adjust basically every variable in this mod


New! Light-based Sneaking Beta

-Only works indoors

-Increases stealth by ash/blight/blizzards outdoors

1.2 Update by Necrolesian

-"Enable light-based stealth" off by default.

-"Show light bar" off by default.

-"Percentage effectiveness of chameleon" set to 25 (from 50).

-Chameleon magnitude capped at 100.

-Chameleon and invisibility bonuses don't stack; instead, you will get the highest bonus from either of the two.

-MCM "NPC sneak bonus" slider fixed.

#### Requirements

-MGEXE

-MWSE-lua beta branch (available here: https://nullcascade.com/mwse/mwse-dev.zip )

-OpenMW is not supported

#### Installation

-Drag and drop data files folder, merge if asked.

#### Uninstallation

-Remove or rename the main.lua file. There is also a mod configuration option to disable the mod as well.

#### Special Thanks:

Necrolesian - Bugfixing

Sigourn - Maintainer

Remiros - Invisibility Fix

Nullcascade - MWSE

Hrnchamd - MWSE
