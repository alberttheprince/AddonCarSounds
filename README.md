# AddonCarSounds

Want to add add-on car sounds in a single resource? Tired of having dozens of unorganized folders/resources for your add-on car sounds? You can use this example resource as a starting point for organizing your engine sounds (and other native audio) into a single resource.

For this, I used:

https://www.gta5-mods.com/vehicles/annis-roxanne-add-on-tuning-sounds-liveries

As an example of how to set this up.

Please match the file structure as it is in the folder.

When adding new car add-on sounds, look to the original named data_file listings:

```
data_file 'AUDIO_GAMEDATA' 'audioconfig/roxanne_game.dat'
data_file 'AUDIO_SOUNDDATA' 'audioconfig/roxanne_sounds.dat'
data_file 'AUDIO_WAVEPACK' 'sfx/dlc_roxanne'
```

**These need to match the file names themselves, so don't use the name of the car, use the name of the audio files as you downloaded them.**

Replicate them for your new vehicle, for example for a made-up car addon audio called the issipissi with files named the same:

```
data_file 'AUDIO_GAMEDATA' 'audioconfig/issipissi_game.dat'
data_file 'AUDIO_SOUNDDATA' 'audioconfig/issipissi_sounds.dat'
data_file 'AUDIO_WAVEPACK' 'sfx/dlc_issipissi'
```

So your fxmanifest.lua should look like this:

```

author 'PrinceAlbert'
description 'Custom Car Audio'

files {
    '**/**/*.dat151.rel',
    '**/**/*.dat54.rel',
    '**/**/*.awc',
}

data_file 'AUDIO_GAMEDATA' 'audioconfig/roxanne_game.dat'
data_file 'AUDIO_SOUNDDATA' 'audioconfig/roxanne_sounds.dat'
data_file 'AUDIO_WAVEPACK' 'sfx/dlc_roxanne'
data_file 'AUDIO_GAMEDATA' 'audioconfig/issipissi_game.dat'
data_file 'AUDIO_SOUNDDATA' 'audioconfig/issipissi_sounds.dat'
data_file 'AUDIO_WAVEPACK' 'sfx/dlc_issipissi'
```

As far as I can tell you cannot glob the data_files for audio. You can then listen the files as I've listed. Do not change the format of the files, use it exactly how I've put them and the same naming conventions.

# Credits

- Thank you dexvo for clarifying/testing globbing in the fxmanifest.lua with regards to the data_file format.
