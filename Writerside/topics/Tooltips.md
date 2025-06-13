# Tooltips

At the current stage Polyglot allows to translate such text from item tooltips. You need to add a line of the following format to the translation file.

`"item.dungeons_and_combat.molten_blazing_sword.polyglot.desc1": "§7Hit Effect:_&_§7Хит эффект:"`  
Where `item.dungeons_and_combat.molten_blazing_sword` is the item's identifier  
`polyglot.desc1` - the identifier that specifies what exactly we will be translating.  
`§7Hit Effect:` is the text to be found in the tooltip.  
`§7Хит эффект:` - my translation  
`_&_` - a separator to separate the original text from the replacement.

What is `desc1` and can there be `desc2` and `desc3`?  
The word `desc` means that this is the data for the tooltip. If you want to translate multiple lines in one subject, you just increase the value by one:

```json
{
    "mykey.polyglot.desc1": "orig1_&_replace1",
    "mykey.polyglot.desc2": "orig2_&_replace2",
    "mykey.polyglot.desc3": "orig2_&_replace2"
}
```

But if you break the sequence, like this:

```json
{
    "mykey.polyglot.desc1": "orig1_&_replace1",
    "mykey.polyglot.desc3": "orig3_&_replace3",
    "mykey.polyglot.desc4": "orig4_&_replace4"
}
```

Then the translation will end with desc1.  
**Important:**  
The text we want to replace must be 100% the same as it actually is. If there are spaces at the beginning of the line, they should be inserted as well.  
**Example:**  
`"item.dungeons_and_combat.molten_blazing_sword.polyglot.desc2": " §9Fire_&_ §9Огонь"`

In order for you to get the source of the tooltip, you can hover over the item and press the P button. Information in this format will be written to the log file:

[//]: # ([![image.png]&#40;https://i.postimg.cc/4ynj9rhv/image.png&#41;]&#40;https://postimg.cc/ctyDqkh6&#41;)

```log
[04:54:17] [Render thread/INFO]: ---Polyglot: [item.dungeons_and_combat.silver_dagger]---
[04:54:17] [Render thread/INFO]: |Silver Dagger
[04:54:17] [Render thread/INFO]: |§7Hit Effect:
[04:54:17] [Render thread/INFO]: | §9Strength against the Udead type
[04:54:17] [Render thread/INFO]: |
[04:54:17] [Render thread/INFO]: |Когда в ведущей руке:
[04:54:17] [Render thread/INFO]: | Урон: 5.3
[04:54:17] [Render thread/INFO]: | Скорость атаки: 2.5
[04:54:17] [Render thread/INFO]: |dungeons_and_combat:silver_dagger
[04:54:17] [Render thread/INFO]: |NBT: 1 тег(ов)
[04:54:17] [Render thread/INFO]: ---
[04:54:18] [Render thread/INFO]: ---Polyglot: [item.dungeons_and_combat.blessed_gold_fist]---
[04:54:18] [Render thread/INFO]: |§eBlessed Gold Fist
[04:54:18] [Render thread/INFO]: |§7Ability:
[04:54:18] [Render thread/INFO]: | §9Haste V for 3 seconds if it's daytime
[04:54:18] [Render thread/INFO]: |
[04:54:18] [Render thread/INFO]: |Когда в ведущей руке:
[04:54:18] [Render thread/INFO]: | Урон: 7
[04:54:18] [Render thread/INFO]: | Скорость атаки: 3
[04:54:18] [Render thread/INFO]: |dungeons_and_combat:blessed_gold_fist
[04:54:18] [Render thread/INFO]: |NBT: 1 тег(ов)
[04:54:18] [Render thread/INFO]: ---
```

You can easily find this information in the logs using the keyword Polyglot and see the item's id and its tooltip text. I have purposely made each line start with the | symbol so that you can see the spaces at the beginning of the line.