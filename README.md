# AddonCarSounds

Want to add add-on car sounds in a single resource? Tired of having dozens of unorganized folders/resources for your add-on car sounds? You can use this example resource as a starting point for organizing your engine sounds (and other native audio) into a single resource.

For this, I used:

https://www.gta5-mods.com/vehicles/annis-roxanne-add-on-tuning-sounds-liveries
https://www.gta5-mods.com/vehicles/maibatsu-sunrise-r-add-on-tuning-liveries-sounds

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

As far as I can tell you cannot glob the data_files for audio. Do not change the format of the files, use it exactly how I've put them and the same naming conventions.

# How do add audio to your add-on cars

Open the vehicles.meta of the car you want

Find the audioNameHash line and add the filename as it is written in the original file name (match if lower or uppercase):
```
      <audioNameHash>roxanne</audioNameHash>
```

Make sure this is ensured before your Add-on Car resource in the server.cfg

for example

```
ensure AddonCarSounds
ensure AddonCars
```

# Credits

- Thank you dexvo for clarifying/testing globbing in the fxmanifest.lua with regards to the data_file format.
