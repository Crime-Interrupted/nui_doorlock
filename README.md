# QBCore Version - Maintained/Updated

* Easily add and configure new doors! <a href='https://streamable.com/e290wk'>Example video</a>  
Use the `/newdoor` command to automatically create a new entry on the DoorList.  

* No more `SetEntityHeading` and `FreezeEntityPosition` natives.  
 Doors in range are assigned a doorHash, used with `AddDoorToSystem`.  
 Doors are assigned a state depending on if they are unlocked, locked, or locking with `DoorSystemSetDoorState`.  

* Garage doors and gates can be locked and will properly move into the correct position.  
If a player comes into range of an unlocked automatic door like this, it will open appropriately.  

* The state of the door is drawn into the world using NUI, meaning full customisation of the appearance and content.  
By default, icons from font-awesome are being displayed; but there is support for images with this method.  
Customisable audio playback! Modify the lock and unlock sound on a door-by-door basic.  

* Improved performance by utilising threads and functions where appropriate.  
Instead of updating the door list every X seconds, your position will be compared to where the last update occured and update when appropriate.  
The state of doors is only checked while in range, and the number of checks per loop depends on the state of the door.  

* Persistent door states! Door states are saved when the resource stops, then loaded back up on start.  
States.json will auto-generate if the file does not exist.  

* Config for both Community MRPD and gabz_MRPD  
Just choose which config file to use and delete the one you are not using.

* Set door access permissions  
Set multiple jobs to be authorised to use a door, with the minimum required grade `authorizedJobs = {['police']=0, ['offpolice']=0}`  
Allow the door to be lockpicked with `lockpick = true`  
Allow item authorisation with `items = {'key_master', 'key_lspd'}` etc.  
