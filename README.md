# kolfix

Provides shortcuts for setting commonly used [KoLmafia](https://github.com/kolmafia/kolmafia/) preferences. Useful for users who have had their preferences recently lost.

## Currently supported things:

__Updated via `auto` (these properties can be automatically inferred from the game):__

 * Crafting Discoveries/Recipes Learned (notably [Cookbookbat](https://kol.coldfront.net/thekolwiki/index.php/Cookbookbat) recipes)
 * [Combat Lover's Locket](https://kol.coldfront.net/thekolwiki/index.php/Combat_lover%27s_locket) - only if used up completely today (adds zeroes to the property if necessary)
 * Puzzle Champ from [Witchess](https://kol.coldfront.net/thekolwiki/index.php/Your_Witchess_Set)
 * Quests including any [Protonic ghost](https://kol.coldfront.net/thekolwiki/index.php/Protonic_accelerator_pack) location
 * [Source Terminal](https://kol.coldfront.net/thekolwiki/index.php/Source_Terminal) - some properties can't be read if you've used all the resources today
 * Sweat from [Designer Sweatpants](https://kol.coldfront.net/thekolwiki/index.php/Designer_sweatpants)

__Requires Individual Setting or `maxAll` (if a maximum exists):__

 * [\[glitch season reward name\]](https://kol.coldfront.net/thekolwiki/index.php/Glitch_season_reward_name) implementations
 * Calculate the Universe from the [Manual of Numberology](https://kol.coldfront.net/thekolwiki/index.php/Manual_of_Numberology)
 * [Gingerbread City](https://kol.coldfront.net/thekolwiki/index.php/Civic_Planning_Office) permanent unlock and all upgrades
 * Rack 'em up at [A Shark's Chum](https://kol.coldfront.net/thekolwiki/index.php/A_Shark's_Chum) - your permanent pool skill (as shown in the quest log at start of ascension) is derived from: $\lfloor2\sqrt{RackEmUps}\rfloor$
 * [Tunnel of L.O.V.E.](https://kol.coldfront.net/thekolwiki/index.php/The_Tunnel_of_L.O.V.E.) permanent unlock

__Daily Flag Fixes (persist until rollover or ascension):__

 * [Combat Lover's Locket](https://kol.coldfront.net/thekolwiki/index.php/Combat_lover%27s_locket) can be forcefully set to fill in zeroes for monsters reminisced today (KoLmafia can't tell how many you've used today if less than all three)
 * [June Cleaver](https://kol.coldfront.net/thekolwiki/index.php/June_cleaver)
 * [Kramco Sausage-o-Matic™](https://kol.coldfront.net/thekolwiki/index.php/Kramco_Sausage-o-Matic%E2%84%A2) - tells KoLmafia your last sausage goblin was encountered in the impossibly far flung future
 * [Mime army shotglass](https://kol.coldfront.net/thekolwiki/index.php/Mime_army_shotglass)

__LIfetime Flag Fixes (persist until ascension):__

* Legendary [Cookbookbat](https://kol.coldfront.net/thekolwiki/index.php/Cookbookbat) pizzas eaten

## Installation

To install, copy and paste the following into the KoLmafia Graphical CLI aka GCLI:

```
git checkout https://github.com/s-k-z/kolfix.git release
```

## Usage

__For a full list of options in KoLmafia__:
```
kolfix
```

__Examples__:

Set today's June Cleaver counters to safe values, for other scripts to continue automating with it (also resets on rollover/ascension):
```
kolfix cleaver
```

Check any properties that can be automatically updated, set permanent pool skill and manual of numberology to the maximum, and mark gingerbread city and tunnel of love as owned and fully upgraded:
```
kolfix auto maxAll
```

Set the quantity of manuals of numberology used to 3, and rack 'em up count to 10:
```
kolfix numberology=3 pool=10
```

To set the number of [glitch season reward name] implementations, either fight the %monster% today and record the big meat drop (same value as hp and mp restored) or search your most recent session log for this value. Calculate: 

`X = today's %monster% meat drop / (5 x [glitch season reward names] owned)`

for example: `100 = 1000 meat / (5 x 2 [glitch season reward names])`
```
kolfix glitch=100
```