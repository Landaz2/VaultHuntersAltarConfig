# Vault Hunters Altar Recipe Config Datapack
Minecraft-Datapack for the Vault Hunters Modpack by [Iskallia](https://github.com/Iskallia), allowing the user to change the Vault Crystal Altar Recipes.

As the public [Modpack on Curse](https://www.curseforge.com/minecraft/modpacks/vault-hunters-official-modpack) / [Mod Repository on Git](https://github.com/Iskallia/Vault-public) did not recieve an update in the last months, here is a temporary fix through a datapack to allow the player to alter the item requirements to infuse Vault Rocks in to Crystals. Currently this is not possible through the vault config files, as the recipes are hard-coded within the mod rather than pulled from the config files. This might get fixed in the future, making this package obsolete.

# Installation
Download the folder "vault_altar_recipe_change" and put it within the saves/(world)/datapacks/ folder within your save world, either directly as a folder or bundled up as a .zip file (see the [Minecraftwiki](https://minecraft.fandom.com/wiki/Data_Pack)). Change the content of the file "altar.json" to your preferences (see the Configuration below), save and done!

To make sure that everything works correctly, open up the world or type `/reload` (with enabled cheats) if the world was already loaded, and then `/datapack list`. Skip through the list to search for `[file\vault_altar_recipe_change (world)]` that is most likely at the bottom of the list. If it is indeed listed, the datapack works correctly!

Now, the next Vault Rock that you put on the Vault Altar will pull the required items from this pack rather than the default ones.

# Configuration
The only file (besides the pack_meta) in this pack is the "loot-table" of the Vault Altar, `altar.json`, which is used to decide what items are needed to infuse a Vault Rock. You can open it with a notepad (or even better, notepad++) to change it. 
The Vault Altar gets the recipe out of four groups of items, "rolling" once on each group. You can identify each group by the following bits of code:
```
        "rolls": {
          "min": 1,
          "max": 1
        },
        "entries": [
```
Within each group, several "entries" are listed, each representing one item. The "weight" is the likelyhood of an item to be pulled, with higher numbers representing a higher chance (in relative to all the other items). The "count" specifies how much of an item is needed, by rolling a random number between the "min" and "max" values.
You can change these values and even delete whole items as you see fit. For instance, reducing the counts by one magnitude (delete one 0 at every entry) makes the early game less grindy until you have the means to automate items. Just make sure that you do not mess up the brackets {} in the file, otherwise it will break.
