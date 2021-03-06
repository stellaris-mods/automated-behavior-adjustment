# Steam description

[//]: # (start)
Steam description transliterated from `steam.bbcode` by [our release script](https://raw.githubusercontent.com/stellaris-mods/scripts/master/stlrel).

## **Corrects combat behaviors to something more realistic\.**
**Please test, review, and let me know how it works**

This mod is 100% compatible with all other addons\.
It's also a brilliant companion mod to ASBM, because this mod will fix any ship that does NOT use ASBMs behaviors\. That includes the AI, and all ingame non\-standard empires and ships\.

Quote from the NSC developers:

> (CaptainX3)
> 6:28 PM CaptainX3: HOLY CRAP
> 6:28 PM CaptainX3: That looked like a REAL fleet engagement\!
> 6:28 PM CaptainX3: What the hell did you do???

Quote from ASBM author Issen:

> (Issen)
> I like it, nice values

So true\. Nice values, indeed\!

So, some time ago I spent some effort [documenting the technical details](http://www\.stellariswiki\.com/Ship\_modding) of Stellaris' ship behavior\.

It was during this endeavour that I realised whoever implemented the ship behavior changes for Stellaris 1\.3 and later can not **possibly** be the same person who created the system initially\. And whoever created it initially has not documented it for the new developers at Paradox\.

Short and sweet; it's completely broken\.

This mod represents the least intrusive, most compatible way to fix it\.

* It is compatible with all addons\.
* It fixes ship behaviors across any installed addon that adds ship types
* It has no user\-facing interface or ingame representation, but works completely behind the scenes\.



I'd like to note that this is still highly experimental, in the sense that I don't actually **play** the game that much, I merely make addons\. As such, there's a limited set of testing scenarios I can set up and execute\.

This addon solves two major issues\.

## 1\. Ship targeting
Here's the thing; vanilla ships that equip Torpedoes, XL weapons, and some few others, will actually never attack non\-vanilla (addon/mod) ships on purpose until all vanilla ships are dead\.

There are obviously many scenarios where they will **fire** on non\-vanilla ships, but at no point in a battle \- while vanilla ships are alive \- will these be their main target\.

Also, some addons "fix" this by overwriting the vanilla weapon files to add in their ship types as explicit targets\. That sounds like a sustainable solution, right?

Possibly the most obvious example of this is if you take a fleet of vanilla ships \+ Dreadnought from Realistic Ships or NSC to fight the Stellarite Devourer\. It will simply never fire at the Dreads until the vanilla ships are dead\. This is, as far as I have found, the best test scenario for this behavior\. But it is \- in fact \- present in all fleet battles\.

Another obvious example of completely broken behavior is the large Pirate Galleon that sometimes spawns, it will relentlessly kill your smallest ships first, because of big misunderstanding whoever wrote that event has with the ship targetting\.

## 2\. Movement fluidity
When vanilla fleets engage eachother, their movement is horrible and jagged\. This can be fixed slightly by increasing formation scale and other tricks that NSC, ISB: Graphics, and other addons do\. This mod makes it even smoother\.


## **Behavior adjustments**
More specifically, regarding combat targeting, here's the priorities this mod applies;

1. Corvettes will charge into combat, focus any target they find, and when they see a large ship with all shields depleted, they charge and kill it
1. Destroyers try to stay in the middle of the battle field, picking off low health targets
1. Cruisers unleash their firepower on any ship not focused by Corvettes or Destroyers, mid\-range, and try to help other ships finish off their targets
1. Battleships stay in the back (but not as far back as vanilla), and fire on targets that no other ship is firing on\. This results in them most of the time focusing the targets furthest away


As a player, what you need to know is that most addons (NSC, Realships, etc) that add ships already map their ships to one of these four behaviors\. And if they do not, which is exceptionally rare, this addon will not interfere with them at all\.

## Specifically, what did I do?
The problem is mostly to do with something Paradox calls component\_target\_weight\_mult\. Whenever a weapon (yes, all weapons pick their own targets) wants to pick a new target, it runs through a list of score bonuses and penalties\. This list is extremely limited, and hard to work with\. But in 1\.3, Paradox added some new behavior (target\_weight) to the XL and Torpedo slots that completely overrides this behavior, using component\_target\_weight\_mult\.

This addon prevents that entirely\. Overriding their explicit\-case override\.
If you're an addon author, it means this mod makes ships ignore target\_weights you set in your weapon components\.

I could go on, but that seems like enough for now\. Read the wiki, and my Aggro\! computer addon code if you want to know more\. I also wrote an article on the PDX forums that I have linked from my Aggro\! workshop description\.

Please let me know if you have any comments, questions, or suggestions\.

## Replaced files
The mod replaces the following game files:
common/ship\_behaviors/00\_strike\_craft\.txt
common/ship\_behaviors/standard\_ship\_behaviors\.txt

## Please check out my other addons\!
[![](http://i\.imgur\.com/XLkY9rP\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=786514324) [![](http://i\.imgur\.com/HB3mzUd\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=790840932)
[![](http://i\.imgur\.com/QbwKam7\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=787280885) [![](http://i\.imgur\.com/Qowgmu2\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=785719197)
[![](http://i\.imgur\.com/557d0qz\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=776095610) [![](http://i\.imgur\.com/c85HK9A\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=785582857)
[![](http://i\.imgur\.com/hGJdX51\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=779729987) [![](http://i\.imgur\.com/HmbP3Gd\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=796214744)
[![](http://i\.imgur\.com/IVM6B6g\.png)](http://steamcommunity\.com/sharedfiles/filedetails/?id=799159083)
[And many others :\-)](http://steamcommunity\.com/workshop/filedetails/?id=779739023)

[//]: # (stop)
