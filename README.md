# Dyson sphere translation plugin!

[Licence: Project is under CC Attribution 4.0](../main/LICENSE)

## This is very work in progress - expect bugs and issues!
### Features
 - Adds possibility to add custom languages (text only)
 - Adds (currently hidden) French lanugage

## Installation
1. Download and Install [BepInEx](https://github.com/BepInEx/BepInEx/releases)
2. Download [mod files](https://github.com/Muchaszewski/DSP_TranslationMod/releases)
3. Extract zip file
4. Paste DLLs under `Dyson Sphere Program\BepInEx\plugins\DSPTranslationPlugin`
5. Add translations to `Dyson Sphere Program\BepInEx\plugins\DSPTranslationPlugin\Translation` as a folder. You can find [translations here](https://github.com/Muchaszewski/DSP_Translations)
6. Select new translation in Menu of the Game
7. Enjoy
(Note: Restart is not required for full effect ;) )

![InGameTranslation](../main/.readme/InGameTranslation.png "In Game Translation")

## How to add new translations
1. Create folder under `Dyson Sphere Program\BepInEx\plugins\DSPTranslationPlugin\Translation` with the name of your translation eg: `Polish`

![TranslationFolder](../main/.readme/TranslationFolder.png "Translation Folder")

2. Run game once - New file settings and translations files will be created.
3. Translate

### Translation file structure:
```
{
  "TranslationTable": [
    {
      "IsValid": true,                          # Does translation exists in the game
      "Name": "点击鼠标建造",                    # Name used by the game for translation (READ ONLY)
      "ID": 1,                                  # Id of the translation (READ ONLY)
      "Original": "Click to build",             # Translation in English
      "Translation": "Kliknij, aby zbudować"    # Your translation here
    },
    (...)
    ]
}
```

### Settings file structure:
```
{
  "Version": "0.1.0.0",                             # Plugin version
  "GameVersion": "0.6.15.5678",                     # Game version
  "LanguageDisplayName": "Polish",                  # Language display name in the game
  "CreateAndUpdateFromPlainTextDumpUnsafe": true    # Should create and import dump file (more below)
}
```

### Dump file:
Simpler file structure where only Translation value is provided.
Each new translation is separated by 5 dashes `-----` this can speed up the translation process. 
Can cause error if ever game decide to change IDs or will add new ones, with JSON format there should be no such issue.
#### IMPORTANT! Disable dump file import when sending for production!
```
Kliknij, aby zbudować
-----
Nie można tutaj budować
-----
Brak przedmiotu
-----
(...)
```

# Roadmap
 - Refactor code and add documentation
 - Add support for in images that can be translated (and game logo)
 - Add support for adjusting content size of in game UI to fit new text
 - Add `*.po` file (in addition to json for easier translations)
 - Create [Nexus](https://www.nexusmods.com/) page for DSP and upload mod there
 - Add https://crowdl.io/ support

# Special Thanks to
[BepInEx](https://github.com/BepInEx/BepInEx/releases) - for mod support

Modified hard fork of [SimpleJSON](https://github.com/Bunny83/SimpleJSON) - for simple json parser
