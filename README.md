# SFS Code Mod Template

A .NET Framework 4.8 template for creating DLL mods for the video game Spaceflight Simulator (SFS).

Some features include:

- Mod information customisation, e.g. ID, display name, author, etc.
- Automatic resolution of SFS installation path + references to game DLLs
- Automatic mod copying to SFS mods folder
- Harmony boilerplate
- Git repo initialisation + .gitignore
- Open source license selection

See [here](FEATURES.md) for more information on the features of this template.

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

### CLI Options

See [here](OPTIONS.md) for all CLI options.

# Social Media

## Forums Post

https://sfsforum.com/index.php?threads/code-mod-net-project-template.20090/

## SFS Modding Guide

https://kojamori.github.io/SFS-Modding-Guide/

## Discord

https://discord.gg/QHEmcehAe9

# License

See [LICENSE](LICENSE).
