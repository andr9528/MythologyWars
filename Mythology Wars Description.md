# Game Title: Mythology Wars
## General Overview
The game is a *Real Time Strategy Game* inspired in many aspects by Age of Mythology.

This game handles *Ages* differently, by building **Temples to the Gods** that the player wishes to worship. This **Temple to the Gods** idea is inspired by Age of Empire: Asian Dynasty's way of advancing in ages, for the Asian civilizations, by building Wonders. 

The difference from both inspiration sources, is that there is no limit in how many the player chose to worship, only penalties or simple requirements. Different Gods Dislikes or Likes other gods, yielding stronger or weaker benefits from their rewards, depending on the other gods that the player is worshiping. 

It is important to protect the temples, as technologies and units are unlocked by owning a set minimum of temples, and as such, are a prime target for enemies. This is also a big difference from the inspiration sources, as you thereby can lose the possibility to build certain units, whereas in the other games, as soon as a age has been reached, units are unlocked until the end of the scenario.

Gods that can be worshiped are split into two types, **Major** and **Minor** gods. From the start of a game the player is able to worship one Major god. After this they need to worship an increasing amount of Minor gods, following the formula below, to allow more worship towards Major ones. The amount needed always round down. 

 - Minor Gods Worshiped to allow worshiping the next Major God
    `1,5 * Major Gods Worshiped + 1`

In Age of Mythology when starting a scenario, the player would chose a Major god, but in this game, the player simply has to chose which civilization they wish to be. 

## Resources
The game has a handful of resources that the player has to manage. These resources are as follows:

 - Food
 - Wood
 - Stone
 - Gold
 - Population
 - Favor

### Food
There is a number of ways to get food. How fast and efficient the generation of food is, depends on where it is gathered from. In the following list they are ranked from fastest to slowest. Different Relics might alter the order of these for a player, but with no relics, this is the order that counts.

 - From Hunted Wild Animals
 - From Herded Friendly Animals
 - From Fishing
 - From Farming
 - From Passive generation from Relics

Food is always part of the cost, when the players wants to train units, and as such is a very important part of the economy. As Food can be gotten from Fishing, Farming and relics it is possible to get infinite of it. 

Wild and Friendly animals will as long as two or more live, slowly multiply, as such these are also infinite sources of food. This however does require a lot more manually managing to maintain the needed numbers to continue multiplying, and are therefore not something that is recommended to use all game long.

### Wood
Wood is gathered by chopping trees. If three trees stand close by one another, they will grow a new one every minute of game time. As such Wood is a Semi-Infinite resource. It is only Semi, because given enough workers, the amount of trees will decline. Some god powers, can alter how fast trees grow, but as a default, it is one tree per three trees tightly grouped together

Wood is used to build buildings together with stone and sometimes gold and favor. Some amount of wood is also needed to train many types of human soldiers and artillery. The training of mythological monster might also cost wood, but it is uncommon.

#### Trees
All trees are not equal, meaning some have more wood in them than others. The longer time a tree has lived the more wood it will contain, up to a maximum of three times its starting wood. The starting wood depends on the tree species, which is dependent on where in the world the map takes place. If a tree has been felled by a Village, or any other way, then it will stop increasing the wood contained within, along with not counting towards spawning more trees. How fast the wood contained in a tree grows follows the formula below.

 - Amount of Wood in Tree
    `Starting Wood * (1 + 0,075) ^ Minutes Since the Tree Spawned`
 
Trees do not block unit pathing, instead units passing through trees will simply be slowed slightly. Units passing through trees will also have a reduced Line of Sight, and archers arrows or siege weapon fire, might strike the trees instead of their target, reducing their accuracy. All of this can be altered, if a player is worshiping a God that does so, but as a default, this is the rules that apply to trees.

By default trees block placement of buildings. This however can be altered, like the other limitations, depending on the gods that are worshiped. If a god allow placement on trees, then the worker will chop the trees in the way, before building the building. They will not gather the resources from the trees, but the trees will be removed, to make room for the building. Due to this, building on trees are slightly slower, but is possible in the right circumstances, if space is running low.

### Stone
Stone is gathered by quarrying from a Stone Quarry. Stone Quarries commonly spawns around mountainous terrain, but can spawn anywhere on a map. Stone Quarries come in three sizes; Small, Medium and Large. How much each Quarry hold, is dependent on the amount of players in the map. 

 - Small Quarry
  `3000 * (1 + 0.08) ^ Amount of Players + 80 * Amount of Players`
 - Medium Quarry
  `4000 * (1 + 0.10) ^ Amount of Players + 100 * Amount of Players`
 - Large Quarry
 `5000 * (1 + 0.12) ^ Amount of Players + 120 * Amount of Players`

Stone is a limited resource, meaning after all has been collected from the map, the only other source is by buying it from the Market, which is a very costly way of getting stone.

Stone is mostly used to build buildings along with wood, but is also used in the training of artillery.

### Gold
Gold can be gotten from a few sources. The most common way is to mine it, from Gold Mines scattered on the map. Gold Mines spawn slightly more commonly close to mountainous terrain, much like stone, but each mine holds a lower amount of gold compared to Stone Quarries. Much like Stone Quarries, Gold Mines also come in the same sizes; Small, Medium and Large, scaling in gold quantity with the amount of players in the game.

- Small Mine
  `1500 * (1 + 0.08) ^ Amount of Players + 80 * Amount of Players`
 - Medium Mine
  `2000 * (1 + 0.10) ^ Amount of Players + 100 * Amount of Players`
 - Large Mine
 `2500 * (1 + 0.12) ^ Amount of Players + 120 * Amount of Players`

Another source of gold, is from Caravans running between a players Market and a Town Center, owned by the player or an Ally. The amount of gold gained when the caravan returns, scale with the distance between the Market and Town Center, that is being traded with, plus a 50% bonus, if its an ally Town Center.

 - Caravan Gold (without bonus)
     `30 * Ln(Meters Traveled by the Caravan)`
  - Caravan Gold (with bonus)
    `(30 * Ln(Meters Traveled by the Caravan)) * 1.5`

### Population
Population is gained by building certain buildings. It is needed to house any human units that is being trained, or has been trained. Most mythological monster also require Population, but not all.

Population is a fixed value, meaning if you have buildings to support 20 units, units build will only fill up to the limit. Should a unit die, it will free up the used population.

If somehow a player manages to have more units than their cap, they will be penalized, by reducing the effectiveness of gathering all other resources. Because of this, it can be valuable for players wishing to hurt others, to destroy buildings that supply the enemy with population, to in turn hurt the economy.

### Favor
The last resource is Favor, which is also the most unique of the resources, as each Civilization has their own way of generating it. As such how it gets produced will be described under each civilization instead of here.

How much Favor a player can keep stored isn't infinite, unlike Food, Wood, Stone and Gold. The Favor capacity scales with the amount of Major and Minor Gods worshiped, along with a starting amount. The following equation determines how much Favor can be stored.

 - Favor Capacity
    `100 + 100 * Major Gods Worshiped + 50 * Minor Gods Worshiped`

## Temple to the Gods
Instead of advancing to different ages, the player will have to build Temples to the Gods that the player wish to worship. 

Depending on the God worshiped by the temple, different mythological monsters are going to become accessible to the player, to use as part of their army.

The Gods also allow the player to research powerful unique technologies that scales with how many disliked or liked other gods that are worshiped, along with relics stored in the Temple. The Temple can store up to three relics, each providing their benefit along with improving the technologies supplied by the Temples Patron. The effectiveness of the technologies follow the formula below.

 - Technologies Effectiveness
    `100% + 25% * Liked Other Worshiped Gods - 25% * Disliked Other Worshiped Gods + 25% * Relics Stored in Temple`

The Temples also functions as a drop off point for resources gathered by the players villagers, if the god worshiped, is one focused on economics.

### Temple Defenses
The Temples aren't completely defenseless on their own, having a couple of ways that they can defend them self, depending on actions done by the player or other gods worshiped. 

First of, they allow Archers to garrison and shot from within. Temples to Major gods allow 12 archers, whereas Temples to Minor gods allows 8 archers. Archers garrisoned within benefit from their ordinary upgrades, but are safe from retaliation, as they are stationed within the temples walls. If archers garrisoned within have special attacks, they will use them, with a slightly increased cooldown, to compensate for that fact that they can do so without risk.

As a second way of defending them self, the temples will slowly train an amount, the formula shown below this section, of the unlocked mythological monster, that are uncontrollable, to patrol and guard the temple. The monsters will will attack anybody who attacks Temples within their vicinity. Because the monsters will help other temples monsters, placing them close to one another can be beneficial. Each monster trained to defend the temple takes 120 seconds, but can be reduced by storing relics in the temple, along with any relic effect that reduces time to train mythological monster. The formula for this section is as follows.

 - Amount of Monsters:
    `8 + 2 * Liked Other Worshiped Gods - 2 *  Disliked Other Worshiped Gods`

 - Training Time for Monsters:
    `120 * (1-0,25) ^ Amount of Relics Stored in Temple`
    
The third way temples defend them self, is highly dependent on what god the temple is too. Some gods are keen on keeping the players temples and city safe, and will call down their god power to aid in the defense of the temples and city. Some gods will supply extra mythological monster to your other temples from their temple, when they reach their defense capacity. amount of monsters follow the formula below.

 - Amount of Extra Monsters:
    `2 + 1 * Liked Other Worshiped Gods - 1 *  Disliked Other Worshiped Gods`

## Civilizations
The game contains the known civilizations from Age of Mythology Extended Edition: Tale of the Dragon, but also contains additionally mythologies not existing in Age of Mythology. The Civilizations in the game is as follow:

 - Greek
 - Egyptian
 - Norse
 - Atlantean
 - Chinese
 - Japanese
 - Indian
 - Mayan
 - Aztec

### Gods Details
Each god, for the different Civilizations has a number of attributes linked to them. Among these attributes are which section of your Civilization that they target, being Offensive, Defensive or Economic capabilities. They all target a Primary and Secondary capability. Gods also have status as to whether they are a Minor or Major Gods.

God powers supplied by gods, comes in three tiers; Aura, Passive and Active. If a god gives an Active god power they will also give other two tiers, and if a god gives a Passive god power they will also give an Aura.

Aura god powers, are constant effects around specified areas of the maps. These possible areas include but are not limited to
 - Natural terrain
 - Player buildings
 - Player units
As a Aura god power is a Constant effect, they have a lower general impact.

Passive god powers, are effect that can trigger when certain events happen in the game. These events can include, but are not limited to:
 - Player buildings being attacked
 - Player building being destroyed
 - Player buildings deals damage
 - Player entering combat
 - Player attempting to exit combat
	 - i.e retreating from enemies
 - Player units takes damage
 - Player units deal damage
 - Player unit dies
Effects from Passive god powers are more potent then those from Aura effects, but still weaker than Active god powers.

Active god powers, are effects that the player actively uses on an area of the map. Some active god powers, have a global reach, but most only target a section of the map. Almost all active god powers require line of sight to cast. All active god powers can be used any number of times, with the limitation that there is a cooldown, between uses. How long the cooldown is, depends on how powerful the effect it has. Only Major gods is able to supply the player with Active god powers, and as such, almost all major gods does so.

All the different tiers of god powers are in general centralized around the same effect, in varying degrees of intensity. The Active god powers will always be focused on the gods primary capability, but the Passive and Aura tiers, are not guaranteed to target the primary capability. 

The intensity of all god powers, including all tiers, scales with the amount of other liked or disliked worshiped gods. As such active god powers can, with the right worshiped gods, become game ending. Some gods will apply additional effects to other liked gods, god powers.

### Generic Buildings
Civilization all have a version of the generic buildings, but may also have buildings unique to the specific civilization. Each building, unique or not, has a set of requirement, before they can be build. These requirements include:

 - Resource cost of the Building (Food, Wood, Stone, Gold, Favor)
 - Minimum Worshiped gods - Value of zero means from start of game.
	 - Minimum Worshiped Major gods 
	 - Minimum Worshiped Minor gods
- Specific Worshiped God
	- Not all buildings has this requirement

Some Civilization might have a more specialized version of a generic building, with additional properties. Unless specified otherwise, all civilization have all generic buildings. How much each building can be improved by technologies varies from civilization to civilization. 

#### Shrine
Shrines are a building that the player can build any number of, which can train unlocked mythological monster, and hold up to two relic.
 
To build a Shrine a player has to worship at least one god. 
Building it cost:
 - Stone: 
 - Wood: 
 - Favor: 

### Generic Units
Much like buildings all Civilizations have a version of the generic units, but again they might have a more specialized version, which will then be specified in the civilizations units section. Again, just like buildings there are requirement to train units, which is as follows:

 - Resource cost of the Unit (Food, Wood, Stone, Gold, Favor)
 - Minimum Worshiped gods - Value of zero means from start of game.
	 - Minimum Worshiped Major gods 
	 - Minimum Worshiped Minor gods
- Specific Worshiped God
	- Not all Units has this requirement

### Greek

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Egyptian

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Norse

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Atlantean

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Chinese

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Japanese

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Indian
#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Mayan

#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units

### Aztec
#### Gods

#### Favor Generation

#### Specific Buildings

#### Specific Units


> Written with [StackEdit](https://stackedit.io/).
