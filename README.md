# ue4-processevent-intercept

This powerful small library allows you to intercept all **ProcessEvent** calls on any game object therefore you could capture and modify 90% of game function calls, one example is you could intercept a function that creates a projectile and modify it's direction to achieve "silent" aim.

The hooking method used is **VMT shadowing** therefore the hook must be applied on every indvidual object that you're targeting in order to intercept the **ProcessEvent** calls and the hook must be reapplied everytime the object gets destroyed and changes (this is already implemented into this library). This method does not require any patching that could be integrity checked against therefore it's safe to use on any anti-cheat the game may have.

I have included an example/usage code based on Ark Survival Evolved.

In order to use this you must find the process event offset for the unreal engine 4 game you're working on, after that the library finds the process event index by using the offset.

Note: Project uses **GetModuleHandleA(NULL)** to get module base so if the game's module is not the main module of the process then you must change this.
