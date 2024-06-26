DMFI Wands & Widgets for Neverwinter Nights 1
Package Version 1.09 (August 24, 2008)
INSTALLATION AND BASIC INFORMATION README
=========================================

Update by: Tsunami282

Original base coding performed by: Hahnsoo

Credits: ACS, Arawen Silverstar, Archaegeo, Biocyde, Dezran, Demetrious, the DMFI Guild, Doppleganger, Elchwang, Jason Robinson (AKA Vendolin), Jhenne, JRR Tolkien, Lurker, Merle, Morderon, Mykael22000, Night Journey, Oddbod, OldManWhistler (whistler), Prince Demetri, Razorwise, volition, and the Dragonspire Gang.

Required Software:

This release requires Neverwinter Nights, with both Shadows of Undrentide and Hordes of the Underdark expansions installed, patched to version 1.69. It also requires the accompanying Toolset to import this package into your module.


INSTALLATION:  (this has changed from prior versions)

This should supersede any prior documentation regarding installation of the package.

1) Import the erf into your module. Overwrite the following files when prompted:

-- nw_c2_default4
-- nw_c2_default5
-- nw_s3_actitem01
-- x2_sig_state

2) Make a new neutral faction and assign "The Voice" and "Settings Adjuster" to that faction.  The voice is much less needed now, but still might cause faction issues.  It is set to Merchant as a default.  They are under custom tutorial.

3) If you had a prior version of the wands in place - DELETE NW_IO_GENERIC from your module.  (why? because one of the big features of this install over the prior versions is to use the massive amount of BW work for improving generic behavior to have effects in your module.  If you keep using the old behavior scripts including lots of other scripts like the ones this package overwrites, then BWs new work is not used.)

4) If you are updating from DMFI version 1.07 or 1.08a, you may delete the following scripts from your module (assuming you have not made any changes from what was supplied with the old DMFI version):
-- nw_c2_default9
-- nw_ch_ac4
-- nw_ch_ac9
-- nw_ch_summon_9

Previous versions of DMFI required these custom scripts in order for the listener system to work. With the switch to the OnPlayerChat event, these custom files are obsoleted.

5) As of NWN patch 1.64, caching of scripts is no longer necessary. If you are updating from a previous version of this package, you may remove any DMFI scripts from your module's list of cached scripts.

6) Add dmfi_onclienter as your handler for the module-level OnClientEnter event. This DMFI script will invoke the default x3_mod_def_enter script, then perform DMFI initialization for the player. If you have a script other than x3_mod_def_enter already assigned to this event, you will have to merge or chain the new DMFI script with yours.

7) Add dmfi_onplychat as your handler for the module-level OnPlayerChat event. The DMFI script provides an easy-to-use hook chaining function, allowing you to add your own processing of this event. Or if you prefer, you can use ExecuteScript in your own OnPlayerChat event handler to invoke dmfi_onplychat.

8) If you want to use the DMFI rest system introduced in 1.08, add dmfi_onrest as your handler for the module-level OnPlayerRest event.

9) If you want to use the persistence support for Knat's NBDE, edit dmfi_db_inc to select NDBE support, and add dmfi_modonhb as your module-level OnHeartbeat event handler.


Advanced install information for people who have already messed with the BW default HotU behavior:
----------------------------------------

If you have already customized any of the files that the erf will overwrite, then you will need to add the DMFI code into your files.  All added code is tagged with DMFI Code Begins Here and Ends Here.  Specifics of where to place the code should be similiar to the location in these overwritten files.

Please see the specific scripts for changes.  Integration is beyond the scope of this readme.


Quick DM Equipping:
-------------------

Create the DMFI Exploder on the ground.  Pick it up and activate it to create all pertinent items in your inventory.


Note on Spoken Settings Changes:
--------------------------------

Remember all spoken settings must be in a float format.  This is true for all spoken setting changes, including those that are in the toolset as integers.  You must have a history of visibility for any creature to capture your voice so if you intend on doing any changes through the settings, you should get away from the players, appear and summon the voice settings creature.  Then what you say is captured.  It should be in float format like "4.0".


Clarification on using "The Voice":
-----------------------------------

There is no longer a need to have an NPC, summon, familiar, or "The Voice" around in order to process voice commands.

There is no longer a need to type your language, voice throw, or other command on the DM channel. Simply use the Talk or Whisper channel. Type the special character (":", ";", ",", "[", or ".") then your text.

There is now good in game documentation to help both players and DM get good use from these functions.


*Known issues*  (These are still existing from 1.08a)
-----------------------------------------------------

From hahnsoo: 

I still can't get alignment shifts to work. I can't figure out if this is a bug. I will playtest a single line script Wed - If anyone sees an error in the code or knows that the BW alignment shift functions don't work, or knows a trick - please post so I can fix the sucker.

The reputation adjustments are not perfect.  I cannot get them to function more than one time for BW default factions.  For example:  The adjustment is set to 5.0 - It will move the reputation by 5 one time and then have no effect (for commoners vs. defenders).  To make a larger effect, you must change the adjustment.  I believe they will function repeatedly for PCs.

Item functions (in the DM Wand):  You will run to the lower left corner of the area (or until impeded).  This is due to BW settings - I don't think it can be fixed.  Options are:  don't use these functions OR stand next to an impedement OR accept the run across the screen.  You may see this same thing with hak objects, or certain object settings or some items (at least I have heard of players seeing this).


Additional Custom Tokens that are now used:
-------------------------------------------

20771 - 20779 : These implement the custom encounters.
20780         : The number of dice for the damage feature of the affliction wand.


If you have problems or questions:
----------------------------------

Message tsunami282 on the Bioware boards.
