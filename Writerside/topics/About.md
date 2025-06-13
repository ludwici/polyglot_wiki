# About

Minecraft has a handy feature to support mods in different languages. However, there are a few problems that this mod should solve.

## Case 1

**Problem:**  
The author released a mod, and the community started sending the author translations in other languages. However, for some reason the author does not make changes to the mod. The only solution is to manually add your translation to the jar file, hoping that the author of the mod will someday approve the translation. However, if any update comes out on the mod, all your hard work will be overwritten.

**Solution:**  
The Polyglot mod allows you to move your translations to another location. A folder will be created in the root folder of your build where you can store your translations.

This way, you no longer need to edit the jar file, and you don't have to worry about your translation being overwritten after a mod update. Your translation is completely independent.

## Case 2

**Problem:**  
For some reason, the author decided not to use the functionality created for text translation and hardcoded the text, and it will not be possible to translate it by translation files.

**Solution:**  
At the current stage Polyglot allows to translate such text from item tooltips. You need to add a line of the following format to the translation file.