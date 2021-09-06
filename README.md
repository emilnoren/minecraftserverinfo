# Lathund plugins & kortkommandon

## Index
- [Sammanfattning](#sammanfattning)
- [Plugins](#plugins)
	- [BigDoors](#bigdoors)
	- [BigDoorsOpener](#bigdoorsopener)
	- [BuildPortals](#buildportals)
	- [Cannons](#cannons)
	- [ChestSort](#chestsort)
	- [Coins](#coins)
	- [LockettePro](#lockettepro)
	- [MobRepellent](#mobrepellent)
	- [MoveCraft](#movecraft)
	- [MythicMobs](#mythicmobs)
	- [QuickShop](#quickshop)
	- [SmoothSleep](#smoothsleep)
	- [UserLogin](#userlogin)

## Sammanfattning
Här är en översikt över de plugins och kommandon som finns tillgängliga.  
Gör ett inlägg i Facebookgruppen om ni saknar ett plugin, stöter på buggar eller har åsikter.

Ni får tåla Svengelskan då det mesta är kopierat direkt från pluginens wiki.

## Plugins

### BigDoors
**OBS! Att skapa ett objekt med BigDoors kostar ingame valuta (100 + (5 x blockCount) GP)**  
Används för att skapa rörliga dörrar, klaffbroar m.m. av block.  
[Mer info](https://www.spigotmc.org/resources/big-doors.58669/)

#### Commands
`/BigDoors`, `/BDM`  
Allows you to access the BigDoors GUI.

`/NewDoor <DoorName>`  
Initiate door creation process.

`/NewPortcullis <PortcullisName>`  
Initiate the portcullis creation process.

`/NewDrawbridge <DrawbridgeName>`  
Initiate the drawbridge creation process.

`/SetBlocksToMove <doorUID> <blocksToMove>`  
Sets the number of blocks this door will try to move.  
Only applies to doors such as portcullises and sliding doors.

`/SetDoorRotation <doorUID> <direction>`  
Changes the direction a door will try to move.

`/NameDoor <doorName>`  
Sets the name of the door when you're in a door creation process.

`/BDCancel`  
Cancel object creation process.

`/DelDoor <DoorName>`  
Allows you to delete a Big Door.

`/OpenDoor <DoorName> [DoorName2] ... [DoorNameX]`  
Allows you to open a Big Door (of any type). Also allows opening more than 1 door at a time.

`/CloseDoor <DoorName> [DoorName2] ... [DoorNameX]`  
Allows you to close a Big Door (of any type).

`/ToggleDoor <DoorName> [DoorName2] ... [DoorNameX]`  
Allows you to open a Big Door (of any type) when it is closed or close it when it's open.

`/ListDoors <DoorName || PlayerName || PlayerUUID>`  
List all doors owned by you, with a specific name if provided.

`/DoorInfo <DoorName>`  
Allows you to get information about a given door.

`/ChangePowerBlockLoc <DoorName>`  
Allows you to change the location of the powerblock of a given door.

`/InspectPowerBlockLoc`  
Gives you a tool that gives you the door info of any powerblock you hit with it.

`/BigDoors AddOwner <doorUID> <playerName>`  
Adds another user as an owner of the given door.

`/BigDoors RemoveOwner <doorUID> <playerName>`  
Removes another user as an owner of the given door.

`/SetAutoCloseTime <doorUID> <autoCloseTime>`  
Sets the amount of time after which a door will try to close itself after it was opened. Negative values mean the door will not try to automatically close (you can still use redstone, of course).

#### Tutorial
When you want to create an animated object of any type, don't worry. There's an in-game guide to help you with it!  

When you have built a door that you would like to open, you start the door creation process using `/NewDoor <DoorName>`, where you substitute `<DoorName>` for any (non-numerical) name you'd like to give it.

Alternatively, you can open the BigDoor Menu using `/BigDoorMenu` (or `/BDM` for short) and use the `New Door` button in the GUI and choose a name using `/NameDoor <DoorName || DoorUID>`, as the instructions will tell you.

Next, you will need to define the region of the door. Just select two points on the door as far away from each other as possible, e.g. top-left and bottom right. You then need to define where the rotation point (or: hinge) is, so the plugin not only knows where the door is but also how to open it. This is done by selecting a column of blocks on the side you want the door to rotate around.  
And that's it! 

You can now start using the door using `/OpenDoor <DoorName || DoorUID>` or find the door in the list shown in this plugin's GUI (sorted by door ID, i.e. creation date, for now) and use the switch there.  
If you want to use redstone to open a door, you can do that too! Simply place the `power block` (**Gold Block**) under the rotation point/hinge.

Place a `Gold Block` below the door hinge to control the door with redstone logic.

</br>
</br>

[[Back to top]](#index)

***

### BigDoorsOpener
Används för att sätta speciella conditions för att öppna eller stänga objekt skapade med BigDoors, t.ex. tidpunkt på dygnet, en nyckel m.m.  

#### Commands
[Översikt kommandon](https://github.com/eldoriarpg/BigDoorOpener/wiki/Commands)  
All commands should start with **`/bdo`**  

`setCondition <doorId> <condition> <conditionValues>`  
Set a condition for a door. Note: Conditions are combined in groups. This will remove all conditions of the same group.

`addCondition <doorId> <condition> <conditionValues>`  
Set a condition for a door. This allows you to add multiple conditions of the same group to the door.

`removeCondition <doorId> <condition> [condition id]`  
Remove a condition from a door.

`copyCondition <sourceDoorId> <targetDoorId> [condition]`  
Copy one or all condition from one door to another.

`cloneDoor <sourceDoorId> <targetDoorId>`  
Clone the settings of a door to another. This includes conditions as well.

`info <doorId>`  
Get information about this door.

`unregister <doorId>`  
Remove all conditions for a door.

`invertOpen <doorId>`  
Invert the state of the door. Useful if you created it in a opened state.

`stayOpen <doorId> <seconds>`  
Set the seconds a door will stay open when fully opened.

`list`  
Get a list of all your registered doors.

#### Conditions
[Översikt conditions](https://github.com/eldoriarpg/BigDoorOpener/wiki/Conditions)

</br>
</br>

[[Back to top]](#index)

***

### BuildPortals
Bygg portaler för att teleportera mellan två punkter.  
[Mer info](https://www.spigotmc.org/resources/buildportals.21922/)

#### Tutorial
1. Skapa en portal av **`Emerald Blocks`**
2. Placera aktiveringsblocken i portalen. Godkända aktiveringsblock är **`Gold Block`**, **`Redstone Block`** och **`Diamond Block`**.
3. Skapa en likadan portal med samma typ av aktiveringsblock vid portalens destination

#### Ritning:
![Portal blueprint](./img/buildportals1.png "Portal blueprint")

</br>
</br>

[[Back to top]](#index)

***

### Cannons
**OBS! Att skapa en kanon kostar ingame valuta (100 - 200 GP)**  
Skapa och avfyra kanoner.

#### Tutorial
[Tutorial](https://dev.bukkit.org/projects/cannons/pages/tutorial)

Bygg valfri kanon enligt ritningarna. Du får ett meddelande om du har gjort rätt.  
Betala för kanonen med kommandot `/cannons buy`, klicka sedan på kanonen.  

Ladda sedan kanonen genom att högerklicka på den med krut i handen.  
Ladda sedan en projektil på samma sätt, se listan **Projektiler**.

Sikta manuellt genom att högerklicka på kanonens sidor och topp med tom hand.  
För att automatiskt sikta högerklickar du på kanonen med föremålet **`CLOCK`**

Skjut genom att högerklicka på facklan med tom hand.

#### Commands
[Översikt kommandon](https://dev.bukkit.org/projects/cannons/pages/commands)

All commands should start with **`/cannons`** 

`build`  
This command gives you a short introduction how to build a cannon.

`fire`  
Gives info on how to fire a cannon.

`dismantle`  
Allows the owner of a cannon to deconstruct the cannon. The player will receive a deconstruction refund.

`rename <OLD_NAME> <NEW_NAME>`  
When you build a new cannon the plugin will use the next free name for the cannon. Since 'Cannon11' does not look nice you have the possibility to change the name.

`info`  
Very simple command that gives you the name and design of a cannon. Type in the command and right click on the cannon to get the information.

`list`  
Since the amount of cannons can be limited for one player it might be interesting to know where these cannons are.

`whitelist add <NAME>`  
Allows the owner of the cannon to add players to the whitelist of a cannon. Just use the command and click on the cannon.

`whitelist remove <NAME>`  
Allows the owner of the cannon to remove players from the whitelist of a cannon. Just use the command and click on the cannon.

`reset`  
You built too many cannons and no idea where they are? This command will remove all your cannons from the database.

#### Projektiler
| Type | Block |
|---|---|
| Canister shot | `GRAVEL BLOCK` |
| Cannonball | `COBBLESTONE BLOCK` |
| Heavy cannonball | `STONE BLOCK` |
| Hardened cannonball | `DIAMOND BLOCK` |
| Teleporter projectile | `ENDER PEARLK` |
| Fireworks | `FIREWORK ROCKET` |
| Clusterbomb | `TNT BLOCK` |

</br>
</br>

[[Back to top]](#index)

***

### ChestSort
Sorterar automatiskt items i kistor och inventory.

#### Hotkeys
| Key | Action |
|---|---|
| **Left-Click a container** | Sorts the clicked container (chest, barrel, shulker box, etc.) |
| **Left-Click outside inventory** | Puts all matching stuff (except hotbar) into the chest, barrel etc. |
| **Double-Left-Click outside inventory** | Puts all items (except hotbar) into the chest, barrel etc. |
| **Right-Click outside inventory** | Puts matching items from the chest, barrel etc. into your inventory |
| **Double-Right-Click outside inventory** | Empties the whole chest, barrel etc. into your inventory |

#### Commands
`/sort`  
Toggle automatic chest sorting.

`/sort hotkeys`  
Open the hotkeys GUI to enable/disable hotkeys per player.

`/invsort toggle`
Toggle automatic inventory sorting

</br>
</br>

[[Back to top]](#index)

***

### Coins
Valutaplugin. Valutan kan användas för att köpa items, använda vissa plugins m.m.  

#### Commands
`/withdraw <amount>`  
Withdraw some currency into physical coins

`/balance`  
See your current balance

`/pay <player> <amount>`  
Send currency to player

</br>
</br>

[[Back to top]](#index)

***

### LockettePro
**OBS! Att låsa ett objekt kostar ingame valuta (20 GP)**  
Lås dörrar, kistor m.m.  
[Mer info](https://www.spigotmc.org/resources/lockettepro-for-1-14-1-15-1-16.74354/)

#### Tutorial
For players, just hold a sign in your hand, then right click a chest or any lockable block.  
If you want to lock a door, you may put a sign on the block above or below the door too.  

You may also `SHIFT+RIGHT CLICK` the block to prevent it get automatically locked, or you can write `[Private]` text manually on signs as well.

**Share the chest with another user:**  
After claiming the chest, you can add another user on the sign. First, right click the sign, then enter `/lock 3 <user name>`  

**Share the chest with everyone:**  
Same as above, you just use `[Everyone]` in the username.

**Add another sign:**  
If one sign is not enough, you may hold a sign and right click on another surface.  
It will snap on the surface and become a `[More User]` sign automatically.  
Placing the sign while holding `SHIFT` will bypass the sign creation.

**Timer with doors:**  
If you add a line `[timer:<int>]` to a door lock, the door will automatically close after `<int>` seconds.

#### Commands
`/lock <line number [1-4]> <text>`  
Edit line number on selected lock sign

</br>
</br>

[[Back to top]](#index)

***

### MobRepellent
Förhindra att mobs spawnar i ett område utan att spamma hundratals facklor.

#### Tutorial
First, using five blocks, construct a shape that looks like a plus sign (+) parallel with the ground.  
Next, place the remaining two blocks directly above the block in the center of the plus sign.  

See these:

**Base**  
![Mob repellent base](./img/mobrepellent1.png "Mob repellent base")

**Completed structure**  
![Completed Mob repellent](./img/mobrepellent2.png "Completed Mob repellent")

To remove an active mob repellent just destroy one of the blocks in the structure.

#### Types
| Type | Block | Radius |
|---|---|---|
| Small | `Iron Block` | 30 blocks |
| Medium | `Gold Block` | 50 blocks |
| Large | `Diamond Block` | 100 blocks |  

</br>
</br>

[[Back to top]](#index)

***

### MoveCraft
Plugin för att bygga fordon av block.  
[Mer info](https://github.com/APDevTeam/Movecraft/wiki)

#### Tutorial
[Video](https://www.youtube.com/watch?v=SSP-qyrVfy4)

Här kommer en quick rundown. Vill ni ha mer info så rekommenderar jag att kika på några tutorialvideos.

Börja med att bygga ditt skepp, var noga med att ha tillräckligt av de block som krävs för skeppstypen.  
Placera en skylt på skeppet med texten för den skeppstyp du försöker bygga, t.ex. `Airskiff`.  
Högerklicka på skylten. Har du gjort rätt så får du ett successmeddelande.  
Placera nu en skylt med `[Helm]`. Denna skylt kommer att fungera som roder. Högerklickar du på denna så ska skeppet rotera 90 grader åt gången.  
Placera en skylt med `Cruise: OFF` på skeppet. Högerklickar du på denna så rör sig skeppet automatiskt mot samma riktning som skylten är placerad.  
Sist placerar du en skylt med texten `Release`. Klicka på denna om du vill göra ändringar på ditt skepp.  
Högerklicka på skylten med din skepstyp igen. Detta lägger till dina senaste ändringar till skeppet.  

Vissa skeppstyper kräver bränsle. Placera ett `Furnace Block` på skeppet och fyll denna med `Coal` eller dylikt.

För att manuellt styra skeppet håller du i en `Stick` och högerklickar i den riktning du vill åka.

#### Types
| Type | Min. blocks | Max blocks | Req. blocks | Req. fuel |
|---|---|---|---|---|
| Airskiff | 50 | 500 | `Wool Block` 20%, `Redstone Block` 20% | Yes |
| Airship | 1000 | 5000 | `Wool Block` 20%, `Redstone Block` 0.1% | Yes |
| BigAirship | 5000 | 20000 | `Wool Block` 20%, `Redstone Block` 0.1% | Yes |
| Elevator | 10 | 1000 |  | No |
| Turret | 20 | 1000 |  | No |
| Ship | 50 | 10000 | `Plank Blocks` or `Wooden Slabs` 25%, build on water | No |

</br>
</br>

[[Back to top]](#index)

***

### MythicMobs
Lägger till extra mobs, bl.a. rare- och bossmobs med unika skills och loot.  
That's it ¯\\\_(ツ)\_/¯

</br>
</br>

[[Back to top]](#index)

***

### QuickShop
Skapa och använd shops för att köpa/sälja items.

#### Commands
[Översikt kommandon](https://github.com/Ghost-chu/QuickShop-Reremake/wiki/Commands)

All commands should start with `/qs`

`price <amount>`  
Change the price of your shop that you're looking at.

`find <string>`  
Use to find the nearest shop that begins with `<string>`  
E.g. `/qs find dia` will find the nearest diamond shop.

`create <price>`  
Create a shop out of the chest you're looking at, stocked with the item you're holding.

#### Tutorial
1. Place a chest.
2. Hold the item you want to buy/sell.
3. Look at the chest and enter the command `/qs create <price>`.
4. Your shop should now be created. Open the chest and add the items you want to sell to stock your shop, leave it empty if you're buying.
5. Right click the sign to see the options for your shop.
6. Click the options to change them. Do this by opening chat (default T).
7. Interact with a shop by left clicking the sign.

</br>
</br>

[[Back to top]](#index)

***

### SmoothSleep
Snabbar upp tiden beroende på hur många spelare som sover.  
Går att använda under natten eller under ett åskoväder.

</br>
</br>

[[Back to top]](#index)

***

### UserLogin
Autentiseringsplugin för användare.

Första gången en ny spelare ansluter till servern så måste de registrera sig.  
Detta görs genom kommandot `/register <password> <password>`.  
Nästa gång de ansluter så loggar de in genom kommandot `/login <password>`.

**Obs! Välj ett lösenord du kommer ihåg. Det är en pain in the ass att behöva återställa ditt lösenord.**

#### Commands
`/register <password> <password>`  
Register an account.

`/login <password>`  
Log-in to your account.

</br>
</br>

[[Back to top]](#index)

***