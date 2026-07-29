# SFS Code Mod Template

A dotnet template for creating SFS code mods easily and quickly, no more writing boilerplate yourself.

# Installation

## NuGet Package

https://www.nuget.org/packages/kojamori.SFS.Templates.CodeMod/1.0.0

```cmd
dotnet new install kojamori.SFS.Templates.CodeMod@1.0.0
```

# Usage

## Example setup

```cmd
dotnet new sfsmod -n BestSFSMod -p:a kojamori --modDisplayName "Best SFS Mod"
```

# Options

## Most Common Mod Options

- `-n`, `--name <name>`: The name of the project and mod.
- `-m`, `--modNameId <modNameId>`: The unique identifier for the mod (`Mod.ModNameID`). (Default: Falls back to `--name`)
- `-mo`, `--modDisplayName <modDisplayName>`: The user-friendly display name shown in-game. (Default: Falls back to `--modNameId`)
- `-p:a`, `--param:author <param:author>`: The author's name. (Default: `""`)
- `-p:m`, `--modVersion <modVersion>`: The current version of the mod. (Default: `1.0.0`)
- `-p:mo`, `--modDescription <modDescription>`: A short summary explaining what the mod does. (Default: `""`)
- `-mi`, `--minimumGameVersion <minimumGameVersion>`: The minimum game version required to run the mod. (Default: `1.6.00.18`)
- `-li`, `--licenseType <MIT|LGPL (v3)|...>`: The open-source license type for the mod code. (Default: `MIT`)
- `-h`, `--harmony <harmony>`: Whether to include Harmony patching boilerplate code. (Default: `true`)

## All Options

- `-as`, `--assemblyName <assemblyName>`: The assembly name for the compiled mod. (Default: Falls back to `--modNameId` or `--name`)
- `-au`, `--autoCopyMod`: Automatically copies the mod to `Spaceflight Simulator Game/Mods/modNameId/` directory on build. (Default: `false`)
- `-r`, `--rootNamespace <rootNamespace>`: The root namespace for the C# project. (Default: Falls back to `--modNameId` or `--name`)
- `-m`, `--modNameId <modNameId>`: The `Mod.ModNameID`. (Default: Falls back to `--name`)
- `-mo`, `--modDisplayName <modDisplayName>`: The user-friendly display name of the mod shown in-game. (Default: Falls back to `--modNameId`)
- `-p:a`, `--param:author <param:author>`: The author's name. (Default: `""`)
- `-mi`, `--minimumGameVersion <minimumGameVersion>`: The minimum game version required to run this mod. (Default: `1.6.00.18`)
- `-p:m`, `--modVersion <modVersion>`: The version of the mod. (Default: `1.0.0`)
- `-p:mo`, `--modDescription <modDescription>`: A short description of what the mod does. (Default: `""`)
- `-up`, `--updateLink <updateLink>`: A URL where users can check for mod updates. (Default: `""`)
- `-li`, `--licenseType <MIT|LGPL (v3)|...>`: The open-source license type for the mod code. (Default: `MIT`)
  - License options:
  - `MIT`: MIT License
  - `LGPL (v3)`: GNU Lesser General Public License v3
  - `GPL (v3)`: GNU General Public License v3
  - `AGPL (v3)`: GNU Affero General Public License v3
  - `apache2.0`: Apache License 2.0
  - `mozilla2.0`: Mozilla Public License 2.0
  - `unlicense`: The Unlicense
- `-c`, `--copyrightHolder <copyrightHolder>`: The copyright holder for the license. (Default: Falls back to `--param:author`)
- `-gi`, `--git`: Whether to initialise a local Git repository upon creation. (Default: `true`)
- `-di`, `--discordLink <discordLink>`: A link to the mod's or author's Discord community. (Default: `""`)
- `-re`, `--readMeDescription <readMeDescription>`: Description text for the README file, under the first H1. (Default: Falls back to `--modDescription`)
- `-h`, `--harmony <harmony>`: Whether to include Harmony patching boilerplate code. (Default: `true`)

# Social Media

## Discord

https://discord.gg/QHEmcehAe9

# License

See [LICENSE](LICENSE).
