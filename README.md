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
3. 3D objects

__Methods__
```pawn
forward PHY_OnObjectUpdate(handleid);
forward PHY_OnObjectCollideWithObject(handleid_a, handleid_b);
forward PHY_OnObjectCollideWithZBound(handleid, lowhigh); // low bound = 0, high bound = 1
forward PHY_OnObjectCollideWithWall(handleid, wallid);
forward PHY_OnObjectCollideWithCylinder(handleid, cylinderid);
forward PHY_OnObjectCollideWithPlayer(handleid, playerid);
```

__Tips__

To get the object id of a handle: `PHY_GetHandleObject(handleid)`

To create a handle, use `PHY_InitObject`:
```pawn
new handleid = PHY_InitObject( objectid, 3003, _, _, PHY_MODE_2D );
```
