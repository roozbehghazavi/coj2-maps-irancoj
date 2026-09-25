IranCoJ Spectate  v1.0.1 beta
=============================

Spectate other players while you are dead, from the multiplayer class-selection
screen. Third person by default, first person optional.


WHAT'S NEW IN 1.0.1
-------------------
* Third-person camera now collides with the world. Indoors it pulls in towards
  the player instead of passing through walls, so it can no longer be used to
  see into rooms you are not in.


INSTALL
-------
Copy the contents of this archive into your Call of Juarez: Bound in Blood
folder, keeping the folder structure. The files land like this:

    Call of Juarez Bound in Blood\
        dinput8.dll                     <- mod loader (replaces the old one)
        spectate.dll                    <- the spectate mod
        mods.txt                        <- list of mods to load
        CoJ2\Data\Menu\
            MenuIngameNetGamemode_Scr_PC.binui   <- menu pack with the button

That's all. No launcher, no config, nothing to enable.

  * mods.txt is safe to copy over. It lists spectate.dll, voicechat.dll and
    directjoinfix.dll; any of those you do not have installed is skipped
    without complaint, so you end up with whichever mods you actually own.
    If you run something else as well (tppcam.dll, headhide.dll, ...), add its
    line back to mods.txt after copying.

  * dinput8.dll must be REPLACED, not skipped, even if you already have one.
    The mouse-button blocking lives in this file, not in spectate.dll. With an
    older loader the mod still runs, but a red marker appears while spectating
    and right-clicking damages players. If that happens to you, you skipped
    this file.

To uninstall, delete spectate.dll and remove its line from mods.txt. Keeping
the new dinput8.dll and the menu pack is harmless.


HOW TO USE
----------
1. Join a multiplayer match.
2. On the class-selection screen, press SPECTATE (next to the class buttons).
   While you are alive it tells you that you have to be dead first.
3. Once you are dead, the spectate bar appears:

       at the top:      <   [ watched player's name ]   >
       at the bottom:   BACK                        FPP/TPP

       BACK       return to class selection (ESC does the same)
       < and >    previous / next player
       FPP/TPP    switch between first and third person

The name strip sits at the top so it does not cover the chat panel.

In team modes you can only watch your own team. This is deliberate: watching
the other side would let a dead player call out enemy positions to their team.


THIRD PERSON vs FIRST PERSON
----------------------------
Third person is the default. It is built from the player's replicated position
and is rock solid. The camera collides with the world, so indoors it pulls in
towards the player rather than passing through walls.

First person sits on the engine's own eye position and follows the player's
real up/down aim, read from the game's own aim value - so when they look up,
you look up.

Two things first person cannot do, because of how the game draws players:

  * Their weapon is mostly out of frame. In first person the game draws a
    special weapon model that exists only for the player holding it. As a
    spectator you see their world model, whose gun is held at hip height.
  * Their shadow has no head, for you only. The head is hidden so it does not
    fill your screen, and a hidden part casts no shadow. Other players, and the
    player you are watching, see a perfectly normal character.


NOTES
-----
* Replaces one menu pack, MenuIngameNetGamemode_Scr_PC.binui, which is the one
  holding the class-selection screen. Nothing else in the menus is touched. If
  you have another mod that changes that same file, the two will conflict.
* Does not change gameplay, weapons, health, skins or any character. Nothing
  here affects what other players see.
* Writes no log files.
* Safe alongside the IranCoJ Skin Pack.
* Works at any resolution and any frame rate.


KNOWN LIMITATIONS
-----------------
* On servers that send few updates per second, the camera can look slightly
  stepped while a player moves. The mod measures the server's update rate and
  adapts its smoothing, but it cannot invent data that never arrived. On a
  healthy server this is not visible.
* Spectating starts only after you die, by design.
* A stray click on the spectate bar can activate whichever button is
  highlighted.
* Chat is not shown while spectating. It lives on the scoreboard panel, which
  the game only draws while TAB is held, so it is not ours to move.
* Holding certain keys while spectating draws the engine's leftover debug
  overlays - boxes around bones, lines, screen blur. Harmless, affects only
  your own screen, and goes away when you stop holding the key.
* Coming back from spectate, the class screen takes a moment before it answers
  clicks again. No instant respawn straight out of spectate.

This is a beta. If something misbehaves, tell us what you did just before it
happened - that is usually enough to find it.

IranCoJ community.
