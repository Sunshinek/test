Original made by ricci77 on Trinity Forum!I Remade all the access to db and updated with the new SD2 code, some clean in code, etc :P!

###### CPP ######

How to manually apply the renamenpc.cpp file:
Quote:Copy renamenpc.cpp from the "CPP file only" folder to your "TrinityCore2/src/bindings/scripts/scripts/custom/" folder.
[Linux only]Open CMakeLists.txt in your Scripts folder and find: scripts/eastern_kingdoms/blackrock_depths/blackrock_depths.cpp Above that, paste scripts/custom/renamenpc.cpp so it looks like this:

   include/sc_instance.h
   scripts/custom/on_events.cpp
   scripts/custom/renamenpc.cpp
   scripts/eastern_kingdoms/blackrock_depths/blackrock_depths.cpp
   scripts/eastern_kingdoms/blackrock_depths/boss_ambassador_flamelash.cpp

Now open the ScriptLoader.cpp file from your TrinityCore2/src/bindings/scripts/system/ folder and find: "//custom" (without quotes). Under that, paste extern void AddSC_renamenpc(); so it looks like this:

//custom
extern void AddSC_renamenpc();

Now search for: "//custom" again (without quotes). Paste AddSC_renamenpc(); under it so it looks like this:

//custom
AddSC_renamenpc();

New open the TrinityCore&Script solution (I use "TrinityCore&Script VC90.sln", but you want to use the one for your Visual Studio version).

In the Solution Explorer, expand 'Scripts->Custom'

Right-click the 'custom' folder and choose 'Add->Existing Item...' and browse to the renamenpc.cpp file

Compile TrinityCore2 as usual


###### SQL ######

Use RenameNPC.sql from Sql if you don't want to create your own NPC

If you create your own make sure to:
* Set npcflag to 1 for GOSSIP
* Set ScriptName to "renamenpc"


Thread on scriptdev2 forum for support and suggestions:
http://www.scriptdev2.com/showthread.php?t=3228


###### RenameNPC Setup ######

In order to have custom RenameNPC full working you will need to modify the renamenpc.cpp file.


Open the renamenpc.cpp. As you can see there, you need to change charactersdb with your charactersdb name:

   You need to serch for characters.characters
   After you find characters.characters you need to know what is this is esy first characters is your ch db name and second characters is ch table from ch db 
   And new you know what is this characters.characters you need to replace first characters with your ch db name and don't edit the second ch becose all ch db have the same name on ch table

Exemple:

Lets say that me ch db name is charac I well put as here:

charac.characters

charac = characters db name
characters = characters table name from characters db