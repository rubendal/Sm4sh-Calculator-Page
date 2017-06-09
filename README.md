## Sm4sh Calculator
Web based Smash 4 knockback calculator

### Recent Changes
* Finally fixed - Vertical KO indicator
* Added - Paralysis time formula
* Changed - Result table design
* Added - Launch rate (0.9 included)
* Added - Set weight to 100 flag for moves that make the opponent have 100 weight like paralyzers and Finishing Touch
* Added - Parameter editing (for modders and researchers)
* Changed - Using new LSI formula obtained with new discoveries
* Changed - LSI is now calculated with DI
* Added - Hit Advantage
* Added - Hitstun cancel calculation process
* Added - URL Sharing

### KH API and HTTPS
To access KuroganeHammer's API it is required to navigate the webpage with http instead of https (unless you deactivate mixed content blocking on your web browser since the API doesn't support https) for move list, switching the url to http will solve this issue

### How to use it
Just input your data, the calculator will update the results when you change something

If the API is not available or having issues you can fill move related data (Base damage, Angle, BKB, KBG) using [KuroganeHammer frame data repository](http://kuroganehammer.com/Smash4)

### What does it calculate
* Modifiers like Monado Arts and Deep Breathing
* Rage
* Aura
* Charged Smash attacks multiplier
* Countered damage
* Hitlag (Attacker and Target)
* Knockback modifiers
* Stale-move negation
* Sakurai Angle
* DI angle
* Knockback Horizontal and Vertical components
* Hitstun
* Hitstun cancel frames
* Determine if the move can jab lock
* Shield stun
* Shield Hitlag
* Shield Advantage
* Hit Advantage
* Luma knockback
* When Reeling/Untechable spin animation could happen
* Launch speed
* Gravity launch speed boost
* LSI
* Max distance when hitstun ends

#### Launch Visualizer
Note: Work in progress, this is not a combo calculator, stage layout collision detection might give weird results and bounced trajectories are not accurate, hurtboxes not included so KO percents are not accurate

Visualize launch trajectory, position per hitstun frame and distance launched in a graph and display stage layout with some collision detection

* Each marker represents each frame in hitstun
* Line color represents vertical momentum
* Yellow markers represents frames that hitstun can be cancelled by using an airdodge
* Green markers represents frames that hitstun can be cancelled by using an aerial
* Give target position when hit using x,y coordinates
* Move angle can be inverted horizontally to visualize launching opponents to the left
* X-axis can represent a surface to show traction and bouncing effects when no stage is selected
* Add legal stage layout with platforms and blast zones with physics (Collision, traction along surfaces, bounce off a surface angle calculation)

Depending on the character launched you would need to increase the X and Y coordinates of the opponent hit, depending on their hit animation, for example most of the time on Puff you should add +4 to Y while on Dedede +2 on Y, meanwhile Cloud doesn't need this increase for an accurate result

## Move Search
http://rubendal.github.io/Sm4sh-Calculator/movesearch.html

Search for moves that match certain conditions using filters

Filter moves by:
* Name/Character/Type
* Hitbox startup frame
* Active hitbox frame
* FAF
* Landing lag
* Autocancel frame
* Base damage
* Angle
* BKB/WBKB
* KBG

Read wiki page for more details: https://github.com/rubendal/Sm4sh-Calculator/wiki/Move-Search

## Percentage Calculator
http://rubendal.github.io/Sm4sh-Calculator/percentcalc.html

Get target percent required to obtain certain knockback, on WBKB moves calculate the minimum rage to reach specified knockback

## TSV Generator
http://rubendal.github.io/Sm4sh-Calculator/tsvgen.html

Generate TSV files containing character, damage, knockback and distance launched data

Use these generated data tables in another applications (R, Excel, and others) to create graphs or filter stuff

Read wiki page for more details: https://github.com/rubendal/Sm4sh-Calculator/wiki/TSV-Generator

## Script Viewer
http://rubendal.github.io/Sm4sh-Calculator/scripts.html

View character scripts that contain hitbox/throw data

All scripts were scrapped using Sammi Husky's Sm4sh Tools (SALT and FITD) and stored in json files with a flag for those that contain hitboxes

## Script Search
http://rubendal.github.io/Sm4sh-Calculator/scriptsearch.html

Search all character game.bin scripts that match certain regular expression, can use a negative regular expression to make easier expressions and filter by script Name

Usually useful if you want to research certain hitboxes or events with certain parameters like SDI, trip chance or unknown events found in all character scripts

Some examples:

* `Clang=0x1.*Rebound=0x0` (Moves that can clank but cannot rebound)
* `ShieldDamage=[1-9][0-9]*` (Hitboxes that deal shield damage)
* `SDI=0,` (Hitboxes that cannot be SDI'd)
* `unk_853CD75E` (Search scripts that contain hitboxes that ignore weight)
* `Damage=[1-9][0-9]*.*Flinchless=0x1` (Windboxes that deal damage)
* `WKB=[1-9][0-9]*.*Rehit=[1-9][0-9]*` (WBKB hitboxes that have rehit rate)
* `Effect=0x14` (Hitboxes that paralyze)
* `Reflectable=0x0, Absorbable=0x1` (Hitboxes that cannot be reflected but can be absorbed)

## Param Viewer
http://rubendal.github.io/Sm4sh-Calculator/params.html

See all characters fighter_param_vl files parameters online, groups before 13 have tags for known stuff, you can check Meshima's [params spreadsheet](https://docs.google.com/spreadsheets/d/1FgOsGYfTD4nQo4jFGJ22nz5baU1xihT5lreNinY5nNQ/edit#gid=305485435) to check special moves and other stuff (groups 13 and higher) for known values for each character

## KO calculator
http://rubendal.github.io/Sm4sh-Calculator/kocalc.html

Calculates opponent's KO percentages on inputted position on a stage, it can also calculate best DI angle the opponent can use to survive however this calculation is a heavy process so it could freeze the page for a moment or even get a popup that the page isn't responding

## Issues and Feedback
You can [open an Issue here](https://github.com/rubendal/Sm4sh-Calculator-Web/issues) or DM me on [Twitter](https://twitter.com/Ruben_dal) your issues and feedback

## Credits
* [@KuroganeHammer](https://twitter.com/KuroganeHammer) [frame data repository](http://kuroganehammer.com/Smash4)
* [FrannHammer (KuroganeHammer API)](https://github.com/Frannsoft/FrannHammer)
* [ssbwiki.com](http://www.ssbwiki.com)
* [Meshima's](https://twitter.com/Meshima_) [params spreadsheet](https://docs.google.com/spreadsheets/d/1FgOsGYfTD4nQo4jFGJ22nz5baU1xihT5lreNinY5nNQ/edit#gid=305485435) (and everyone contributing here)
* [Sammi Husky's](https://twitter.com/sammihusky) [Sm4sh Tools](https://github.com/Sammi-Husky/Sm4sh-Tools)