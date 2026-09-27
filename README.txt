PIRATES MM SET
==============

A new Mastermind primary for an i24 server. Buccaneers (T1), two Coralax,
the Tidecaller and the Tidesinger (T2), and a Captain (T3), plus three
blade attacks with Bleed, two slottable upgrades, and Cannon Barrage.

This package has three folders. Install all three, then restart the server
so that it rebuilds the bins. Your launcher must also send the new and
changed files to players.


1. Defs/  (complete files, copy them in as they are)
----------------------------------------------------
  - mastermind_summon_pirates.powers        the player powers
  - mastermind_pets_pirate_*.powers (19)    the pet powers
  - Pirates_Mastermind.villain              the pet VillainDefs

  Copy the .powers files to data/defs/powers/.
  Copy Pirates_Mastermind.villain to data/defs/villains/.


2. Merge/  (Pirates blocks to add to files you already have)
------------------------------------------------------------
  Each block starts with "// BEGIN PIRATES" (or "# BEGIN PIRATES") and ends
  with "// END PIRATES". Add each block to your own copy of the file. Do not
  replace your file, because it has your other sets in it.

  File                                   Where the block goes
  -------------------------------------  --------------------------------------
  Mastermind_Summon.powersets            with the other Mastermind_Summon sets
  Mastermind_Pets.powersets              with the other Mastermind_Pets sets
  Player_Mastermind_Summon.categories    inside the Mastermind_Summon category,
                                         before the Robotics line (the creation
                                         screen lists the sets in file order)
  Player_Mastermind_Pets.categories      inside the category, before the "}"
  Player_Mastermind_Summon.ms            anywhere (texts for the player powers)
  Player_Mastermind_Pets.ms              anywhere (texts for the pet powers)
  player.txt  (data/sequencers/)         after the line
                                           Include sequencers\player\emotes_CostumeChange.inc
  boostsets/*.powerinc (15 files)        at the end of each file in
  (data/defs/boostsets/)                 data/defs/boostsets/ (IO set lists)

  If you prefer, send me your current copies of these files. I add the
  blocks and send them back complete.


3. Data/  (new files, in the data folder layout)
------------------------------------------------
  Copy the folder over your data folder. It only adds files:
  - defs/v_mastermind_pets/v_mastermind_pirates.nd      pet costumes
  - ent_types/Pirate_Tidesinger_*.txt                   Tidesinger bodies
  - sequencers/player/pirates.inc                       cast animations
  - fx/pirates/                                         effects
  - menu/powers/animfx/Pirates/                         power animations
  - sound/Ogg/Pirates/                                  sounds
  - texture_library/GUI/Icons/Powers/Pirates_*.texture  icons


Engine features the set uses
----------------------------
All are stock i24 features. If your custom code changed one of them, the
Pirates feature beside it can fail without an error.

  Feature                                   Used for
  ----------------------------------------  ----------------------------------------
  TargetRequires "distance 10 >"            pistol and musket are not used in melee
  rand in a Requires                        Lady Luck's card draw
  target.ownPower? / target.ownPowerNum?    Bleed stacks, the sharks' bonus, the draw
  kGrantPower of hidden powers (LifeTime)   Bleed, the four card suits, Snake Eyes
  source.owner> in a Requires               no ghost when the Mastermind is dead or
                                            offline
  kPostDeath power with kEntCreate          the Revenant ghost rises
  kSetCostume swap powers                   eyepatches, parrot, coral growth
  PrimaryTint / SecondaryTint in a .pfx     sea colors on the upgrade casts
  new player sequencer moves (JOBSDONE bit) coin, bow, and order casts end cleanly


Notes
-----
  - The server gives the new powers new IDs in data/defs/dbidmaps on the first
    start. Existing characters are not affected.
  - The IO blocks assume the stock boostsets lists. If you renamed or merged
    those lists, add the power names from the blocks to your own lists.
  - To remove the set: delete the Defs and Data files, and delete each
    BEGIN PIRATES ... END PIRATES block. Characters that have Pirates as
    their primary lose those powers.
