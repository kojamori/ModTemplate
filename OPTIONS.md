# Template Options (CLI)

Ignore these options if you are using an IDE to create a new project, as the IDE will provide a GUI for you to fill in these options.

## Essential Options

These are the required options for creating a new SFS mod project using this template.
They won't necessarily prevent the project from being created, but these will cause issues if not specified.

- `-n` or `-m`: The name of the project and mod. This is also used as the root namespace and assembly name if not specified otherwise. (Default: `""`)
- `-au`, `--param:author <param:author>`: The author of the mod. This is used in the mod's metadata and is displayed in the game. (Default: `""`)

## Most Common Options

- `-n`, `--name <name>`: The name of the project and mod.
- `-m`, `--modNameId <modNameId>`: The unique identifier for the mod (`Mod.ModNameID`). This should not contain spaces or special characters, otherwise you may need to manually fix broken namespace or identifier usage. If left empty, the project name will be used as the ModNameID. (Default: Falls back to `--name`)
- `-mo`, `--modDisplayName <modDisplayName>`: The display name for the mod, shown to players in the in-game mod list. If left empty, the Mod Name ID will be used as the display name. (Default: Falls back to `--modNameId`)
- `-au`, `--param:author <param:author>`: The author of the mod. This is used in the mod's metadata and is displayed in the game. (Default: `""`)
- `-p:m`, `--modVersion <modVersion>`: The version of the mod. (Default: `1.0.0`)
- `-p:mo`, `--modDescription <modDescription>`: A brief description of the mod. This is displayed in the in-game mod list. (Default: `""`)
- `-mi`, `--minimumGameVersion <minimumGameVersion>`: The minimum game version required for the mod to work. Note that this is purely informational and does not affect the mod's actual compatibility with the game. (Default: `1.6.00.16`)
- `-li`, `--licenseType <MIT|LGPL (v3)|...>`: The open-source license type for the mod. This is used in the mod's metadata. (Default: `MIT`)
  - License options:
  - `MIT`: MIT License
  - `LGPL (v3)`: GNU Lesser General Public License v3
  - `GPL (v3)`: GNU General Public License v3
  - `AGPL (v3)`: GNU Affero General Public License v3
  - `apache2.0`: Apache License 2.0
  - `mozilla2.0`: Mozilla Public License 2.0
  - `unlicense`: The Unlicense
  - `none`: No license, all rights reserved
- `-ha`, `--harmony <harmony>`: Whether to include Harmony boilerplate in the mod. Harmony is a library for patching .NET methods at runtime, allowing mods to modify the behavior of the game without modifying its source code. (Default: `true`)
- `-p:a`, `--autoCopyMod`: Whether to automatically copy built mods into the SFS mods folder, such as the Spaceflight Simulator Game/Mods/modNameId/ directory on build. (Default: `false`)

## Other Options

- `-as`, `--assemblyName <assemblyName>`: The assembly name for the generated project. If left empty, the Mod Name ID will be used as the assembly name. (Default: Falls back to `--modNameId` or `--name`)
- `-r`, `--rootNamespace <rootNamespace>`: The root namespace of the assembly. Defaults to the ModNameID if left empty. (Default: Falls back to `--modNameId` or `--name`)
- `-c`, `--copyrightHolder <copyrightHolder>`: The copyright holder for the mod. If left empty, the author will be used. (Default: Falls back to `--param:author`)
- `-g`, `--git`: Whether to initialize a local Git repository in the generated project folder. (Default: `true`)
- `-re`, `--readMeDescription <readMeDescription>`: The description in the mod's README. Defaults to the mod description if left empty. (Default: Falls back to `--modDescription`)
- `-im`, `--implicitManagedReferences <implicitManagedReferences>`: Whether to implicitly include all managed DLLs as references. If set to false, only Assembly-CSharp.dll, UnityEngine.dll, 0Harmony.dll and UnityEngine.CoreModule.dll will be included as references. This can reduce naming conflicts. (Default: `true`)
- `-s`, `--socials`: Whether to include a social media section in the README. (Default: `true`)
- `-di`, `--discordLink <discordLink>`: The Discord invite link for the mod's server. This is displayed in the in-game mod list. (Default: `""`)

## Deprecated Options

- `-up`, `--updateBoilerplate <updateBoilerplate>`: Whether to include the boilerplate code for automatic updating using Neptune-Sky's UITools' IUpdatable interface. Details at https://github.com/cucumber-sp/UITools. (Default: `false`)
  - See [here](FEATURES.MD#mod-updating-boilerplate-via-uitools-broken) to know why this is deprecated.
