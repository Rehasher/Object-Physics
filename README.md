# Object-Physics (Lorenc_'s Edit)
SA-MP Include used to handle 2D and 3D physics of (~sphere) objects.

http://forum.sa-mp.com/showthread.php?t=446286

### This include supports only streamer objects!

In my version, every physics have their own physics instances have handles and are assigned an object ID. 

This does not support/use ColAndreas either. It's been removed for the purpose of making it easy to debug/lightweight.

**Warning...** your client's `ackslimit` could get hit using this which can lead to timeouts. The solutions:
1. Increase the interval in which the physics include updates object positions `PHY_TIMER_INTERVAL`
2. Raise `ackslimit` to like 5,000 or 10,000 - or refrain from moving too many objects at a time with this version

__What's working__
1. Object to object collision
2. Object to wall collision

__What's not tested__
1. Object to cylinder collision
2. Object to player collision
