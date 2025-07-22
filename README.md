# MinecraftShared
My personal modded Minecraft Java clientside modpack for making playing the game more enjoyable.

**Do note that some mods aren't allowed on multiplayer servers & their use is considered cheating**, such as Meteor Client or Journeymap. Disable in PrismLauncher before joining.

## Setup
### Importing mods
`mods/` includes the modpack (mrpack) for [PrismLauncher](https://prismlauncher.org/).

Import it by selecting `Add Instance` -> `Import` -> `Browse` -> Select the `mrpack` file -> `OK`. This will download all included mods and the modloader.


### Linking config
All files under `InstanceSharedContent/` are to be symbolically linked into the instance `minecraft` folder. You can find the `minecraft` folder by selecting the instance in PrismLauncher, and then pressing `Folder`.

This can be done graphically in KDE's Dolphon file manager. Select all the contents of `InstanceSharedContent/` and drag them to the instance's folder and select `link`.

On Unix-like systems, the command `ln -s` can be used to symlink files from the CLI.


## Why symlinks?
Symlinks were chosen to have an external git repo to store all relevant configuration AND share between multiple instances without needing to re-copy every time something changes.

However, this does mean that upgrading versions can break older configs. If you are changing versions often or wish to not share config files between instances, consider copying all files instead.

## Gitignore
Gitignore files are included throughout the repo mainly to prevent accidentally leaking sensitive data, such as accounts, coordinates, maps, proxies, and so on.

On your local machine, if a mod writes to one of the symlinked folders, it will be shared across instances but not added to git history.