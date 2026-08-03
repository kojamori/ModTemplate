# SFS Code Mod Template

A .NET Framework 4.8 template for creating DLL mods for the video game Spaceflight Simulator (SFS).

This template has the ability to automatically resolve the SFS installation path on Windows. Automatic resolution for MacOS and Linux is also supported but not tested. If the automatic resolution fails, you can manually set the SFS installation path in the project's `.csproj` file by changing the `SFSPath` value.

## Automatic Mod Copying to SFS Mods Folder

One of the features of this template is that MSBuild can copy the build DLL into the SFS mods folder after building the mod successfully. You can enable/disable this by changing the `AutoCopyMod` value in the project's `.csproj` from `True/False`.

You can set "Automatic Mod Copying" (`--autoCopyMod`, `-p:a` in the CLI) to `true` when creating the project with the template to enable this behaviour, as **it is disabled by default.**

## Implicit References

This template also has an option to use implicit references for all of the managed DLLs, which means you don't have to manually add them as references in your project. You can enable/disable this by changing the `ImplicitManagedReferences` value in the project's `.csproj` from `True/False`, and instead you get only essential references including:

- `Assembly-CSharp.dll`
- `UnityEngine.dll`
- `UnityEngine.CoreModule.dll`
- `0Harmony.dll`.

You can set "Implicit Managed References" (`--implicitManagedReferences`, `im` in the CLI) to `false` when creating the project with the template to disable this behaviour, as it **is enabled by default.**

# Requirements

- .NET SDK 6.0 and newer
- .NET Framework 4.8 (pre-installed on Windows 10 and 11 operating systems)
- SFS installed via Steam

# Installation

## .NET 7.0 and newer (most common)

Run the following command to install the template from [NuGet](https://www.nuget.org/packages/kojamori.SFS.Templates.CodeMod):

```dotnetcli
dotnet new install kojamori.SFS.Templates.CodeMod
```

## .NET 6.0 (older syntax)

```dotnetcli
dotnet new --install kojamori.SFS.Templates.CodeMod
```

## Updating

Run the following command to update the template from NuGet:

```dotnetcli
dotnet new update
```

# Usage

## IDE Usage

### Visual Studio

When using Visual Studio, you can also use the "Create a new project" dialog and search for "SFS Code Mod Template" to create a new SFS mod project, as seen in the screenshots below.
![Screenshot](https://raw.githubusercontent.com/kojamori/SFS-Code-Mod-Template/refs/heads/main/assets/vs_usage1.png)
![Screenshot](https://raw.githubusercontent.com/kojamori/SFS-Code-Mod-Template/refs/heads/main/assets/vs_usage2.png)

### JetBrains Rider

When using JetBrains Rider, you can also use the "New Solution" dialog and select the "SFS Code Mod Template" on the bottom-left side, below "Custom Templates" to create a new SFS mod project, as seen in the screenshot below.
![Screenshot](https://raw.githubusercontent.com/kojamori/SFS-Code-Mod-Template/refs/heads/main/assets/rider_usage.png)

## Command Line Usage

Syntax:

```cmd
dotnet new sfsmod [options] [template options]
```

Example usage:

```cmd
dotnet new sfsmod -n BestSFSMod -au kojamori --modDisplayName "Best SFS Mod"
```

# Template Options (CLI)

Ignore these options if you are using an IDE to create a new project, as the IDE will provide a GUI for you to fill in these options.

## Essential Options

These are the required options for creating a new SFS mod project using this template.
They won't necessarily prevent the project from being created, but these will cause issues if not specified.

- `-n` or `-m`: The name of the project and mod. This is also used as the root namespace and assembly name if not specified otherwise. (Default: `""`)
- `-au`, `--param:author <param:author>`: The author's name. (Default: `""`)

## Most Common Options

- `-n`, `--name <name>`: The name of the project and mod.
- `-m`, `--modNameId <modNameId>`: The unique identifier for the mod (`Mod.ModNameID`). (Default: Falls back to `--name`)
  - This should not contain spaces or special characters, otherwise you'll have to manually change broken strings like the root namespace in the generated project, as a namespace cannot contain spaces or special characters.
- `-mo`, `--modDisplayName <modDisplayName>`: The user-friendly display name shown in-game. (Default: Falls back to `--modNameId`)
- `-au`, `--param:author <param:author>`: The author's name. (Default: `""`)
- `-p:m`, `--modVersion <modVersion>`: The current version of the mod. (Default: `1.0.0`)
- `-p:mo`, `--modDescription <modDescription>`: A short summary explaining what the mod does. (Default: `""`)
- `-mi`, `--minimumGameVersion <minimumGameVersion>`: The minimum game version required to run the mod. (Default: `1.6.00.16`)
- `-li`, `--licenseType <MIT|LGPL (v3)|...>`: The open-source license type for the mod code. (Default: `MIT`)
  - License options:
  - `MIT`: MIT License
  - `LGPL (v3)`: GNU Lesser General Public License v3
  - `GPL (v3)`: GNU General Public License v3
  - `AGPL (v3)`: GNU Affero General Public License v3
  - `apache2.0`: Apache License 2.0
  - `mozilla2.0`: Mozilla Public License 2.0
  - `unlicense`: The Unlicense
  - `none`: No license, all rights reserved
- `-ha`, `--harmony <harmony>`: Whether to include Harmony patching boilerplate code. (Default: `true`)
- `-p:a`, `--autoCopyMod`: Automatically copies the mod to `Spaceflight Simulator Game/Mods/modNameId/` directory on build. (Default: `false`)

## Other Options

- `-as`, `--assemblyName <assemblyName>`: The assembly name for the compiled mod. (Default: Falls back to `--modNameId` or `--name`)
- `-r`, `--rootNamespace <rootNamespace>`: The root namespace for the C# project. (Default: Falls back to `--modNameId` or `--name`)
- `-up`, `--updateBoilerplate <updateBoilerplate>`: Whether to include the boilerplate code for automatic updating. (Default: `false`)
  - Automatic updating using Neptune-Sky's UITools' IUpdatable interface. Details at https://github.com/cucumber-sp/UITools.
- `-c`, `--copyrightHolder <copyrightHolder>`: The copyright holder for the license. (Default: Falls back to `--param:author`)
- `-g`, `--git`: Whether to initialise a local Git repository upon creation. (Default: `true`)
- `-di`, `--discordLink <discordLink>`: A link to the mod's or author's Discord community. (Default: `""`)
- `-re`, `--readMeDescription <readMeDescription>`: Description text for the README file, under the first H1. (Default: Falls back to `--modDescription`)
- `-im`, `--implicitManagedReferences <implicitManagedReferences>`: Whether to include implicit managed references. (Default: `true`)

# Social Media

## SFS Modding Guide

https://kojamori.github.io/SFS-Modding-Guide/

## Discord

https://discord.gg/QHEmcehAe9

# License

See [LICENSE](LICENSE).
